# 为一副普通卡片设计数据结构(类和对象)

> 原文:[https://www . geesforgeks . org/design-data-structures-asses-object for-generic-deck-cards/](https://www.geeksforgeeks.org/design-data-structuresclasses-objectsfor-generic-deck-cards/)

设计一副普通纸牌的数据结构解释如何对其进行子类化以实现特定的纸牌游戏，以及如何对数据结构进行子类化以实现 21 点。

**解决方案:**

首先，我们需要认识到一副“通用”的牌可能意味着很多东西。Generic 可能意味着一副可以玩类似扑克游戏的标准牌，或者它甚至可以延伸到 Uno 或 Ballow 牌。

**实施特定的纸牌游戏**

让我们假设这副牌是一套标准的 52 张牌，就像你在 21 点或扑克游戏中看到的那样。如果是这样，设计可能是这样的:

这里的结构很清楚:一副牌包含四套花色，一套花色包含 13 张牌。每张卡片都有 1 到 13 的数值。如果你想一个纸牌游戏，不同的游戏不同于发牌和放回纸牌的方式。因此，我们可以在类“Deck”中有一组抽象方法，允许子类实现自己的处理方式。我画的类图在这里:

下面是 C++实现的思路。

```
/*1\. Investigation on an individual card instead of 
   a collection of cards, focus on a card's state 
   and interface.
2\. A card game has its own specific constrain and 
   requirement on cards, such that a generic card 
   cannot satisfy a blackjack card
3\. Player manage multiple cards */

#include <bits/stdc++.h>
using namespace std;

namespace SUIT {
enum Enum {
    SPADE,
    HEART,
    CLUB,
    DIAMOND
};
};

class Card {
private:
    SUIT::Enum s;
    int v;

public:
    virtual SUIT::Enum suit() const
    {
        return s;
    };

    virtual int val() const
    {
        return v;
    };

    Card(int val, SUIT::Enum suit)
        : s(suit), v(val){};
};

class BlackJackCard : public Card {
public:
    virtual int val()
    {
        int v = Card::val();
        if (v < 10)
            return v;
        return 10;
    }

    BlackJackCard(int val, SUIT::Enum suit)
        : Card(val, suit){};
};

class player {
private:
    int id;
    int bet;
    set<int> points;
    vector<BlackJackCard*> bjcs;
    bool addPoint(set<int>& amp; points, BlackJackCard * card)
    {
        if (points.empty()) {
            points.insert(card->val());
            if (card->val() == 1)
                points.insert(11);
        } else {

            /* Set elements are ALWAYS CONST, they can't
               be modified once inserted. */
            set<int> tmp;
            for (auto it = points.begin(); it != points.end(); ++it) {
                tmp.insert(*it + card->val());
                if (card->val() == 1)
                    tmp.insert(*it + 11);
            }
            points = tmp;
        }
    }

    void getPoints()
    {
        cout << "You All Possible Points : " << endl;
        for (auto it = points.begin(); it != points.end(); ++it) {
            cout << *it << endl;
        }
    };

    int getMinPoints()
    {
        /* set is implemented by commonly BST, so else 
          are in order!!!
          learn to use lower_bound() and upper_bound()
          "they allow the direct iteration on subsets 
           based on their order."
          which gives us another option to find min. preferable */

        // return *(points.lower_bound(0));
        return *(points.begin());
    };

    void printCards()
    {
        cout << "You Cards : " << endl;
        for (auto it = bjcs.begin(); it != bjcs.end(); ++it) {
            cout << (*it)->val() << endl;
        }
    }

public:
    player(int i, int j)
        : id(i), bet(j)
    {
        bjcs.push_back(new BlackJackCard(rand() % 13 + 1, SUIT::SPADE));
        bjcs.push_back(new BlackJackCard(rand() % 13 + 1, SUIT::SPADE));
        addPoint(points, bjcs[0]);
        addPoint(points, bjcs[1]);
    };

    void getAnotherCard()
    {
        for (set<int>::iterator it = points.begin(); it != points.end(); ++it) {

            /* predefined strategy for the player    */
            if (*it <= 21 && 21 - *it <= 4) {
                printCards();
                getPoints();
                cout << "Stand" << endl;
                exit(1);
            }
        }
        bjcs.push_back(new BlackJackCard(rand() % 13 + 1, SUIT::SPADE));
        addPoint(points, bjcs.back());
        if (getMinPoints() > 21) {
            printCards();
            getPoints();
            cout << "Busted" << endl;
            exit(2);
        }
    };

    virtual ~player()
    {
        for (auto it = bjcs.begin(); it != bjcs.end(); ++it) {
            delete *it;
        }
    };
};
// Driver code
int main()
{
    srand(time(NULL));
    player p(1, 1000);
    p.getAnotherCard();
    p.getAnotherCard();
    p.getAnotherCard();

    return 0;
}
```

输出:

```
You Cards : 
10
10
You All Possible Points : 
20
Stand

```

**实施 21 点。**

**注意:**现在，假设我们正在构建一个 21 点游戏，因此我们需要知道卡片的价值。牌面是 10，一张王牌是 11(大多数时候，但那是手牌类的工作，不是下面的类)。

在二十一点游戏开始时，玩家和发牌者每人收到两张牌。玩家的牌通常正面朝上，而庄家有一张正面朝下(称为洞牌)和一张正面朝上。

最好的 21 点牌是任何一张 10 分牌的王牌的开局。这被称为“21 点”，或自然 21 点，除非庄家也有 21 点，否则持有这一点的玩家自动获胜。如果一个玩家和庄家都有一个 21 点，结果就是对那个玩家的推动。如果庄家有 21 点，所有没有持有 21 点的玩家都会输。

**Java 中 21 点的主要逻辑**

```
public class BlackJackHand extends Hand<BlackJackCard> {

    /* There are multiple possible scores for a blackjack 
   hand, since aces have 3 * multiple values. Return 
   the highest possible score that's under 21, or the
   4 * lowest score that's over. */

    public int score()
    {
        Arraylist<Integer> scores = possibleScores();
        int maxUnder = Integer.MIN_VALUE;
        int minOver = Integer.MAX_VALUE;
        for (int score : scores) {
            if (score > 21 & amp; &score < minOver) {
                minOver = score;
            } else if (score <= 21 & amp; &score > maxUnder) {
                maxUnder = score;
            }
        }
        return maxUnder Integer.MIN_VALUE ? minOver maxUnder;
    }

    /* return a list of all possible scores this hand could have 
     (evaluating each * ace as both 1 and 11 */
    private Arraylist<Integer> possibleScores() { ... }

    public boolean busted() { return score() > 21; }
    public boolean is21() { return score() == 21; }
    public boolean isBlackJack() { ... }
}

public class BlackJackCard extends Card {
    public BlackJackCard(int c, Suit s) { super(c, s); }
    public int value()
    {
        if (isAce())
            return 1;
        else if (faceValue >= 11 & amp; &faceValue <= 13)
            return 10;
        else
            return faceValue;
    }

    public int minValue()
    {
        if (isAce())
            return 1;
        else
            return value();
    }

    public int maxValue()
    {
        if (isAce())
            return 11;
        else
            return value();
    }

    public boolean isAce()
    {
        return faceValue == 1;
    }

    public boolean isFaceCard()
    {
        return faceValue >= 11 & amp;
        &faceValue <= 13;
    }
}

/* This is just one way of handling aces. We could, alternatively, create a class
of type Ace that extends BlackJackCard. */
```

**参考文献:**
[【https://www.careercup.com/question?id=2983】](https://www.careercup.com/question?id=2983)

本文由 Somesh Awasthi 先生供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
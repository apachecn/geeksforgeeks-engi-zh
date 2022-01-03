# 如何知道代码失败的测试用例？

> 原文:[https://www . geesforgeks . org/how-know-test cases-其中代码失败/](https://www.geeksforgeeks.org/how-to-know-testcases-where-code-fails/)

在[](https://www.geeksforgeeks.org/competitive-programming-conquering-a-given-problem/?ref=rp)**竞争编程中，经常会编写针对给定示例测试用例的代码，但是在提交时最终会得到一个 [**WA** (错误答案)结论](https://www.geeksforgeeks.org/time-wrong-answer-wa/)。这就是事情变得令人沮丧的地方，不知道解决方案**在哪个**测试用例**上失败了**。在这种情况下**程序员**可以做一些事情:**

1.  **手动检查角箱**
2.  **[**压力测试**](https://www.geeksforgeeks.org/stress-testing-software-testing/)**

### ****<u>检查角落情况</u> :****

**在一些问题语句中，它有**角测试用例**，程序员需要**添加/编辑**一些代码行，以确保程序在这些情况下也能正常工作。例如，在一个需要[在数组](https://www.geeksforgeeks.org/find-the-smallest-positive-number-missing-from-an-unsorted-array/)中找到**最小正整数**的问题中，如果一个解是这样的:**

> **int mn = arr[0]
> 为 I:1->arr _ size:
> if(arr[I]<mn)
> Mn = arr[I]
> 打印 Mn**

****<u>解释</u> :**
以上逻辑不会给出 **AC** (接受)的判决，这里很容易算出问题。此代码将失败的**测试用例之一**是当数组为 **arr[] = {2，-1，3，4，5}** 时。以上算法输出为 **-1** ，但正确输出为 **2** 。
求最小**正整数**需要编辑代码，确保不包含负整数**。****

### ******<u>压力测试</u> :******

******压力测试** 是一种代码测试技术，通过测试超出正常运行的**极限**来确定代码的**健壮性**。假设一个问题有一个**天真解**(慢)和一个**最优解**(快)在提交蛮力解时得到一个 [**TLE** (超过时限)判决](https://www.geeksforgeeks.org/overcome-time-limit-exceedtle/)，所以想出最优解，但是在提交时我们在部分或全部测试用例上得到 **WA** 。****

****现在，这里要做的第一件事是考虑一些**测试用例**，其中解决方案可能不起作用，并在它们上面检查解决方案。如果想不出测试用例，那么还有一个方法，那就是压力测试**。******

****在**压力测试**中，思路是生成随机测试用例，检查蛮力解和最优解的输出。虽然强力解决方案是**慢**但是它是**正确的**，而最优解决方案是**快**，但是在一些测试案例中它是错误的。这允许我们检查某个测试用例的最优解输出是否正确，而无需**手动**检查，它可以简单地检查**天真解**的输出是否与**最优解**的输出一致。检查是自动完成的，数千个代码的正确性也取决于测试用例的**天真解**的**复杂度**秒，所以找到我们的代码失败的测试用例的**概率**变得很高**。******

******因此，请执行以下步骤，通过运行无限循环来检查随机输入的解决方案:******

1.  ******生成**随机**输入([点击此处了解](https://www.geeksforgeeks.org/types-software-testing/)如何)******
2.  ****存储蛮力输出和**最优**解****
3.  ****如果两个输出(相等)比打印**正确******
4.  ****否则打印输入并**断开**循环****

****如果循环运行了一段时间而没有中断，即所有输出都是正确的，那么要么检查更大的输入，要么尝试提交您的解决方案。****

******示例:******

******<u>问题陈述</u> :** 给定一个 **N** 正整数的[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) **arr[]** ，任务是找到数组中元素的[最大成对乘积。](https://www.geeksforgeeks.org/return-a-pair-with-maximum-product-in-array-of-integers/)****

> ******输入:** arr[] = [2，3，4，9，4，7]
> **输出:** 63
> **解释:**
> 数组的最大两两乘积为 9 * 7 = 63。****
> 
> ******输入:** arr[] = [-20，-50，1，2]
> **输出:** 1000
> **解释:**
> 数组的最大成对乘积为(-20) * (-50) = 1000。****

****以下是**压力测试**对上述问题的实现:****

## ****C++****

```
**// C++ program to illustrate the stress
// testing for the above problem
#include <bits/stdc++.h>
using namespace std;

// Function that implements the Naive
// Solution for the given problem
int maxProductNaive(int a[], int n)
{
    int ans;
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (i == 0 && j == 1)
                ans = a[i] * a[j];
            else if (a[i] * a[j] > ans)
                ans = a[i] * a[j];
        }
    }
    return ans;
}

// Function that implements the Optimal
// Solution for the given problem
int maxProductOptimal(int a[], int n)
{
    // Sort the given array
    sort(a, a + n);

    // Find the maximum product
    int ans = a[n - 1] * a[n - 2];

    // Return the product
    return ans;
}

// Function that performs the
// Stress Testing
void test()
{
    // Seeding random number generator
    // to get uniques values
    srand(time(0));

    while (1) {

        // Generate values for n
        // from 2 to 10
        int n = rand() % 10 + 2;
        int a[n];

        // Iterate over array a[]
        for (int i = 0; i < n; i++) {

            // Subtracting -5 will
            // generate -ve integers
            a[i] = rand() % 10 - 5;
        }

        // Solution using Naive Approach
        int ans_brute
            = maxProductNaive(a, n);

        // Solution using Optimal Approach
        int ans_optimal
            = maxProductOptimal(a, n);

        // If ans is correct
        if (ans_brute == ans_optimal)
            cout << "Correct\n";

        // Else print the WA Test Case
        else {
            cout << "Wrong Answer\n";

            cout << n << endl;

            // Print the array a[]
            for (int i = 0; i < n; i++)
                cout << a[i] << " ";

            cout << "\nCorrect Output: "
                 << ans_brute << endl;

            cout << "Wrong Output: "
                 << ans_optimal << endl;
            break;
        }
    }
}

// Driver Code
int main()
{
    // Function Call for Stress Testing
    test();
    return 0;
}**
```

******Output:**

```
Wrong Answer
4
-4 -3 -3 1 
Correct Output: 12
Wrong Output: -3

```**** 

******<u>解释</u> :**
最优解对正整数很有效，但对**负整数**无效，如代码输出所示。通过压力测试，它解决了代码的问题。为了生成和测试更大输入的代码，为 **n** 和**a【I】生成更大的整数。******

******<u>总结</u> :** **压力测试**肯定会有助于**调试**代码，但首先应该尝试考虑代码**可能无法**工作的测试用例，因为它不太**复杂**来检查一些简单的测试用例，如果**没有帮助**则继续进行**压力测试**。****
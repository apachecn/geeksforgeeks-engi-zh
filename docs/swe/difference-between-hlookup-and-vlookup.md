# 【HLookup 和 VLookup 的区别

> 原文:[https://www . geesforgeks . org/hlookup 和-vlookup 的区别/](https://www.geeksforgeeks.org/difference-between-hlookup-and-vlookup/)

**HLookup :**
水平查找函数称为 HLookup 函数。该函数用于在表的一组行中水平查找值。它在查找表中水平查找一个值。它根据 Excel 中给定的行号返回一个近似或精确的值。VLookup 函数提供的查找值与 HLookup 函数提供的值相同。

**HLookup**的语法:

```
HLOOKUP(lookup_value, table_array, row_index_num, [range_lookup]).
```

**VLookup :**
垂直查找函数称为 VLookup 函数。此函数用于在表的一组行中垂直查找值。它在查找表中垂直查找一个值。它根据 Excel 中给定的列号返回一个精确或近似的值。

**Vlookup**的语法:

```
VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup]).
```

【HLookup 和 VLookup 的区别:

<figure class="table">

| **序列号** | **赎金** | **VLOOKUP** |
| 01. | 它假设数据被排列成一个表，不同的行中有不同的信息元素。 | 而它假设数据被排列成一个表，在不同的列中有不同的信息元素。 |
| 02. | 它在查找表中水平查找一个值。 | 它在查找表中垂直查找一个值。 |
| 03. | 与 VLookup 函数相比，HLookup 函数的使用较少。 | VLookup 函数的使用比 HLookup 函数多。 |
| 04. | 当数据按行列出时使用。 | 而当数据列在列中时使用。 |
| 05. | 在 HLookup 函数中，用户在表或范围中搜索的值必须在最上面的列中。 | 在 VLookup 函数中，用户正在搜索的值必须位于表或范围的最左边一列。 |
| 06. | HLookup 函数返回在同一列中搜索到的值。 | VLookup 函数在同一行但在下一列返回搜索到的值。 |
| 07. | HLookup 函数中的 H 代表水平搜索 | VLookup 函数中的 V 代表垂直搜索。 |
| 08. | 它用于从最底部的范围中找出数据。 | 它有助于找出最左边一列中的数据。 |

</figure>
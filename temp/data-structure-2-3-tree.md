

## Basic

2-3 樹，B-tree 的一種特化例子。以往較常見的樹狀資料結構通常為二元樹，在二元樹中，一個節點只存在一個 key 值，並且最多可以有兩個分支 (brench)，也是因此才稱作二元樹。而 2-3 樹顧名思義就是**「有二到三個分支」**。而其節點也較為不同的是，最多可以有兩個 key 值。

## Definition

#### 名詞解釋

> - 2-node：該節點僅有一個 key 值，且有兩個分支。
> - 3-node：該節點有兩個 key 值，且有三個分支。
> - internal node：所有實體的節點中，非葉節點知節點。
> - external node：由葉節點延伸出去的虛擬分支所連結的子節點。葉節點的分支同樣遵守 2-node 有兩個分支與 3-node 有三個分支的準則。

- 每個 internal node 不是 2-node 就是 3-node。
- 每個 external node 有相同的深度，換句話說，所有葉節點的深度也會相同。
- 節點內的 key 值會按照順序排序

## Operations

#### insertion


#### deletion


#### search


## Analysis

#### Advantage

- 較普通二元樹易於維持樹的高度，維持平衡。（所有葉節點深度相同，表示該樹不會有歪斜的情況。）
- 搜尋一棵 2-3 樹雖然不見得比搜尋二元樹來的有效率，但當 2-3 樹的節點都為 3-node 時，2-3 樹的整體高度會小於二元樹（log3(x) < log2(x), when x > 1）

#### Disadvantage

- 實現較二元樹困難且繁瑣。

#### Complexity

- insertion：O(log2(N))
- deletion：O(log2(N))
- search：O(log2(N))

或許看起來好像跟二元樹一樣，但其實是不一樣的。當二元樹發生嚴重的**歪斜**時，甚至成為單一直線時，其 insertion、deletion、search 的時間複雜度將變成 O(N)。

## Reference

[Wikipadia][1]
[2-3 Trees Complete Description][2]

[1]: http://en.wikipedia.org/wiki/2-3_tree
[2]: http://www.cs.ucr.edu/cs14/cs14_06win/slides/2-3_trees_covered.pdf

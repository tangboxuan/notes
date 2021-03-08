    github.com/tangboxuan
<table>
<tr><th><h3>Time Complexity</h3></th><th><h3>Searching</h3></th></tr>
<tr>
<td>
  
1 < logn = log(n^2)< sqrt(n) < n < nlogn = logn! < n^2 < 2^n  

|Recurrence           |Runtime|
|:---:|:---:|
|T(n) = 2T(n-1) + O(1)|2^n|
|T(n) = 2T(n/2) + O(n)|nlogn|
|T(n) = T(n/2) + O(n)|n|
|T(n) = 2T(n/2) + O(1)|n|
|T(n) = S(0,sqrt(n))T(i) + sqrt(n)|n|
|T(n) = 2T(n/4) + O(1)|sqrt(n)
|T(n) = T(n/2) + O(1)|logn|
</td>
<td>

|Search|Runtime|
|:---:|:---:|
|Linear|n|
|Binary|logn|Must be sorted|
|Quickselect|n|Find k largest
|Knuth Shuffle|n|for (1,n-1): swap(i,rand(0,i))
|Merkel Tree|logn|Search for differences|

Knuth Shuffle:  
for (1,n-1): swap(i,rand(0,i))
</td>
</tr>
</table>

## Sorting

|Algorithm|Best|Average|Worst|Stable|Invariant|
|:---:|:---:|:---:|:---:|:---:|:---:|
|Bubble|n|n^2|n^2|Yes|Largest k items are in final k positions|
|Selection|n^2|n^2|n^2|No|Smallest k items are in smallest k positions|
|Insertion|n|n^2|n^2|Yes|First k items are sorted|
|Merge|nlogn|nlogn|nlogn|Yes|Groups of 2^x are sorted|
|Quick|nlogn<br>nlogk|nlogn<br>nlogk|n^2<br>nk|No|Array is partitioned around pivot<br>T(n) = kT(n/k) + O(nlogk) -> nlogn|
|Reversal||n(logn)^2|||Quicksort with Mergesort around pivot

## Trees

|Structure|Operation|Remark|
|:---:|:---:|:---:|
|Binary Search|h|**Delete** if x has 2 child: replace x with successor(x)<br>**Successor** right.min() or recurse to (left of parent or root)
|AVL|logn|h < 2logn or n > 2^(h/2)<br>v.left Left Heavy or Balanced: right(v)<br>v.left Right Heavy: left(v.left), right(v)<br>**Insert** 2R **Delete** 2lognR
|Trie|L|More space due to more overhead|
|(a,b)|logn|**split** for insert, **merge+share** for delete
|kd|h|Alternate splitting horizontally and vertically

|Augmented Structure|Remark|
|:---:|:---|
|Dynamic Order Statistic|Stores weight of subtree. During functions, rank = left.weight + 1<br>**Select** left.weight < rank: left.select(k). Else: right.select(k-rank)<br>**Rank** recurse to root, if node is right child: rank += parent.left.weight + 1
|Interval Tree|Sort by left endpoint. Stores max endpoint in node's subtree<br>**Search** (logn) If x > max or left is null, search(right). Else: search(left)<br>**All Overlap** (klogn) search node, add to list, delete node, repeat until null|
|Orthogonal Range Search|Store all points as leaves of a BST. Internal nodes stores max of left.<br>**Range Query** (k+logn) find split node. do left & right traversals. <br>**2D Range Query** (k+(logn)^2) for node in x-tree, build y-tree using nodes in subtree.|

## Hashing
Must redefine **hashCode** _default returns address_ and **equals** _for **get** to work_  
|Collision|Insert|Search|Space|Remarks|
|:---:|:---:|:---:|:---:|:---:|
|Linked List|h+1 = 1|h+n/m = 1|m+n|Simple Uniform Hashing Assumption<br>Worst case for search = n|
|Open Addressing|1/(1-a),<br>|where<br>a = n/m<br>a<  1|n|Uniform Hashing Assumption<br>Linear Probing - Clusters<br>Double Hashing - h(k,i) = f(k) + ig(k) mod _m_, (m,g(k)) <br>**Delete** sets node to special value for **search**|

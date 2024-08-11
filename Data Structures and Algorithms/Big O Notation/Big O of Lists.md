for Python lists
## Append
To append a value at the end of a list, it takes O(1)
ex. [1,2,3] we append 4, It only takes O(1)
## Insert
To insert values at the start of the list, it takes O(n)
ex. [1,2,3] we insert 4, it needs to first reindex the items (means 0, 1, 2 becomes 1,2,3) then 4 is inserted at index 0.
`[(0,1), (1, 2), (2, 3)]` becomes `[(0,4), (1, 1), (2, 2), (3, 3)]`

## Pop
to pop or remove item at the start of the list, it takes O(n)
to pop or remove item at the end of the list, it takes O(1)

Even insert or remove at the middle of the list, still takes O(n) because it is the worst-case scenario
#linkedList
#twoPointers


``` kotlin
// Return middle of linked list
var fast = head
var slow = head

while (condition) {
	fast = fast?.next?.next
	slow = slow?.next
}

return slow
```

Condition effects which middle node selected if there are even number of nodes-
- `fast?.next != null` second middle node is selected.
- `fast?.next?.next != null` first middle node is selected.
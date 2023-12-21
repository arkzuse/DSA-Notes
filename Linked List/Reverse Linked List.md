#linkedList 
- Create a null pointer (p) to which nodes starting from head will be pointed. Keep moving this pointer to the newest node added.
- Another pointer (q) will point to head.next to keep reference of old list so that head can be removed and added to new list.
- Terminate when head of original list becomes null.
> We are removing head from original list and adding it to new list and then making next node of original list as head. This is repeated untill nothing is left in original list.

```kotlin
fun reverseList(head: ListNode?): ListNode? {
	var front = head
	var p: ListNode? = null
	var q: ListNode? = null
	//
	while (front != null) {
		q = front?.next    
		front?.next = p    
		p = front    
		front = q    
	}
	//
	return p
}
```




Initial
```mermaid
graph LR
1[1, front] --> 2 --> 3 --> 4
p[p, null]
q[q, null]
```



 1. `q = front?.next`
```mermaid
graph LR
1[1, front] --> 2[q, 2] --> 3 --> 4
```


2. `front?.next = p`
```mermaid
graph LR
1[1, front] --> p[p, null]
2[q, 2] --> 3 --> 4
```


3. `p = front`
```mermaid
graph LR
1[1, front, p]
2[q, 2] --> 3 --> 4
```


4. `front = q`
```mermaid
graph LR
1[1, p]
2[front, q, 2] --> 3 --> 4
```














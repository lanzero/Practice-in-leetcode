    class Solution:
    def insert(self, head: 'Node', insertVal: int) -> 'Node':
        newNode = Node(insertVal)
        if not head:
            newNode.next = newNode
            return newNode
        cur = head
        while True:
            if cur.val > cur.next.val and (newNode.val <= cur.next.val or newNode.val >= cur.val):
                break
            elif cur.val <= newNode.val <= cur.next.val:
                break
            elif cur.next == head:
                break
            cur = cur.next
        newNode.next = cur.next
        cur.next = newNode
        return head
        
        
the point is to find the very point where the max one conencted with the min one.

Solution 1 (Iterative) :-

    var mergeTwoLists = function(list1, list2) {
        let head = new ListNode(0);
        let curr = head;

        while(list1!==null && list2!==null){
            if(list1.val < list2.val){
                curr.next = list1;
                list1 = list1.next;
            }
            else{
                curr.next = list2;
                list2 = list2.next;
            }
            curr = curr.next;
        }
        curr.next = list1 || list2;

        return head.next;
    };

    Time Complexity - O(N)
    Space Complexity - O(1)

    Explanation -
    Initially, we take a dummy node and a pointer that will keep track of the current node.

    While there are still nodes to compare in two lists, we first check if value of 1st list's node is less than value of 2nd list's node. If it is, we set the current node's link to list1's node and set list1's current node to list1's next node. In the else condition, it's the other way around.

    Once the loop ends, if one of the lists no longer have any nodes to compare, we point current node's link to the remaining nodes in the other list. Also if both lists are empty, we point current node's link to null.

    Lastly return the merged linked list.

Solution 2 (Recursive) :-

    var mergeTwoLists = function(list1, list2) {
        if(!list1){
            return list2;
        }
        else if(!list2){
            return list1;
        }
        else if(list1.val <= list2.val){
            list1.next = mergeTwoLists(list1.next, list2);
            return list1;
        }
        else{
            list2.next = mergeTwoLists(list1, list2.next);
            return list2;
        }
    };

    Time Complexity - O(M+N) => M and N are the lengths of the two lists to be combined.
    Space Complexity - O(1)

    Explanation (Credits - https://leetcode.com/problems/merge-two-sorted-lists/solutions/2705782/js-recursion-with-exlanation/) -
    To solve this problem using recursion we can keep calling the lists until one of them is null, and while they are not null, we do an equality check.

    If list1 is less than or equal to list2, we call recursion with list1.next = mergeTwoLists (list1.next, list2). If the value is greater, then we call list2.next = mergeTwoLists(list1, list2.next).

    If one of the lists is null, we simply return the opposite list (we don't care if it's null or not). Thus, when the recursion ends, the stack will begin to collapse in reverse order, which will allow us to get a new merged sorted list.

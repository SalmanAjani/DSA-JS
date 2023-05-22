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

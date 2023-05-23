Solution 1 (Nested Loops) :-

    var twoSum = function(nums, target) {
        for(let i=0; i<nums.length-1; i++){
            for(let j=i+1; j<nums.length; j++){
                if(nums[i]+nums[j] === target){
                    return [i,j];
                }
            }
        }
    };

    Time Complexity - O(N^2)
    Space Complexity - O(1)

    Explanation -
    This approach is pretty straightforward. We use two loops and check whether the numbers
    at the two indices add up to the target. If they do, we just simply return them.

Solution 2 (Efficient) :-

    var twoSum = function(nums, target) {
        const hashMap = new Map();

        for(let i=0; i<nums.length; i++){
            const currNum = nums[i];
            const numToFind = target-currNum;

            if(hashMap.has(numToFind)){
                return [hashMap.get(numToFind), i]
            }
            else{
                hashMap.set(currNum, i);
            }
        }
    };

    Time Complexity - O(N)
    Space Complexity - O(N)

    Explanation -
    We can approach this problem in this way. We iterate over every single element in the
    array and find the difference between target and current element.

    We keep the element being processed and the index of the element in a map and everytime
    we calculate the new difference, we check whether the element is present in the map or
    not.

    For example lets take the array - [2,7,11,15] and target - 9
    This is the order in which elements will be processed and their differences:
    1) 9-2 = 7
    2) 9-7 = 2

    In the first case difference between 9-2 is 7, which is not present in the map at the
    current moment, but we'll save (2,0) pair in the map.

    In the next case difference is 2. We'll check whether 2 is present in the map. Since 2 is
    present we will push the index assigned to it and the index of the current element in a
    result array.

    We can then simply return the result array.

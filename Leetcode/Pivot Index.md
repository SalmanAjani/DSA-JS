Solution 1 (Iterative) :-

    let leftSum = 0, rightSum = 0, sum = 0;

    for(let i=0; i<nums.length; i++){
        sum += nums[i];
    }

    rightSum = sum;

    for(let i=0; i<nums.length; i++){
        rightSum -= nums[i];

        if(rightSum === leftSum){
            return i;
        }

        leftSum += nums[i];
    }
    return -1;
    };

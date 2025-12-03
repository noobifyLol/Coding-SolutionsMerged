# Perfect Number 
# Easy leetcode

## My Code: 
--- 

        '''java
                    class Solution {
                public boolean checkPerfectNumber(int num) {
                    int maxBound = (int) Math.sqrt(num);
                    int total = 0;
                    if (num == 1){
                        return false;
                    }
                    for (int i = 1; i <= maxBound; i++){
                        if (num % i == 0 && i != 1){
                            total += i; 
                            total += num / i;
                        }
                    }
                    total += 1;
                    if (total == num){
                        return true;
                    }
                    else{
                        return false;
                    }
                }
            }


        
---
I just loop throught the sqrt of the number because all the mutiples of that number will be included when you reach the sqrt so I looped through that and then add it up
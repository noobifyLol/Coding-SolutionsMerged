# Medium LeetCode problem In typescript

---
## My Code : 
        '''ts


        function myPow(x: number, n: number): number {
            let iter = 1;

            let f = Math.abs(n);
        
            while (f > 0){
            if (f % 2 === 0){
                x *= x;
                f = f/2;
            }
            else /*(n % 2 !== 0) */{ // if power is odd
                    f -= 1;
                    iter = iter * x;
            }
            
            }
            
            return n < 0 ? 1 / iter : iter;

        };
--- 
You use the properties of exponentiation to get the time complexity from O(n) to O(log(n))
Because 2^8 = 4^4 and 4^5 = (4^1) * (4^4)
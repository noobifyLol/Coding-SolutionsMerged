# Easy problem Maxium69 Number

## My code : 
class Solution {
    public int maximum69Number (int num) {
        int temp = num;
        int lastSixIndex = -1;
        int powerOfTen = 0;
        while (temp > 0) {
            if (temp % 10 == 6) {
                lastSixIndex = powerOfTen;
            }
            temp /= 10;
            powerOfTen++;
        }

        if (lastSixIndex != -1) {

            return num + 3 * (int)Math.pow(10, lastSixIndex);
        }
        return num;
    }
}
---
My approach was basically starting from right to left and then tracking when was the last time we saw a six and then using basic
exponent tracking and addition (powerOfTen tracks the six's index place)
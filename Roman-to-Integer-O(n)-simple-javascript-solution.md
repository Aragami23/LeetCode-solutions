# Problem Link
https://leetcode.com/problems/roman-to-integer/description/

# Submission Link
https://leetcode.com/problems/roman-to-integer/submissions/889806621/

# Intuition
My first intuition was to go from the right, that way I would be able to inmediatelly identify if a roman was repeated three times and in that case or in the case of two repetitions of the number I would add the repetitions times the integer equivalent to the total sum.
But then I read the problem again an the rules clearly stated that there were only certain romans that when put to the left of another would form this new number, and those were only  6 possibilities.
# Approach
Being that my goal, for the limited time I can dedicate to solve this problems, was to finish ASAP even if that means not finding the most optimal solution, I decided to go for what seemed like an easy and also with a low complexity way of just identifying the 6 special cases and any other thing just to add it roman by roman using the equivalent integer.

# Complexity
- Time complexity:
O(n)

- Space complexity:
O(n)

# Code
```js
/**
 * @param {string} s
 * @return {number}
 */
var romanToInt = function(s) {
    const array = s.split('');
    var num = 0;
    for (i=0;i<array.length;i++) {
        if (array[i] == 'I') {
            if (array[i+1] == 'V') {
                num+=4;
                i++;
                continue;
            }
            if (array[i+1] == 'X') {
                num+=9;
                i++;
                continue;
            }
            num+=1;
            continue;
        }
        if (array[i] == 'X') {
            if (array[i+1] == 'L') {
                num+=40;
                i++;
                continue;
            }
            if (array[i+1] == 'C') {
                num+=90;
                i++;
                continue;
            }
            num+=10;
            continue;
        }
        if (array[i] == 'C') {
            if (array[i+1] == 'D') {
                num+=400;
                i++;
                continue;
            }
            if (array[i+1] == 'M') {
                num+=900;
                i++;
                continue;
            }
            num+=100;
        }
        if (array[i] == 'V') {
            num+=5;
            continue;
        }
        if (array[i] == 'L') {
            num+=50;
            continue;
        }
        if (array[i] == 'D') {
            num+=500;
            continue;
        }
        if (array[i] == 'M') {
            num+=1000;
            continue;
        }
    }
    return num;
};
```

this problem depends on [two-sum](../arrays-hashing/two-sum.md), all solutions that were submitted there should work here, but since the array is sorted, it gives us a chance to use two pointers and not use memory at all
### submitted solution
```javascript
/**
 * @param {number[]} numbers
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(numbers, target) {
    let l = 0;
    let r = numbers.length - 1;
    while(l < r) {
        const sum = numbers[l] + numbers[r];
        if(sum === target){
            return [l + 1, r + 1]
        }
        if(sum > target){
            r -= 1
        }
        if(sum < target){
            l += 1;
        }
    }
}
```
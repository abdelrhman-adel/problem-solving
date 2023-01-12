### submitted solutions
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    for(let i = 0; i< nums.length;i +=1){
        for(let j = i + 1;j< nums.length;j += 1){
            if(nums[i] + nums[j] === target){
                return [i, j];
            }
        }
    }
};
```
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    const cache = new Map();
    for(let i = 0; i<nums.length;i++){
       if(cache.has(target - nums[i])){
           return [i, cache.get(target - nums[i])]
       }
       cache.set(nums[i], i)
    }
};
```
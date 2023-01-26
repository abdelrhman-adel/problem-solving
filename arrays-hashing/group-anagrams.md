### submitted solutions
```javascript
/**
 * @param {string[]} strs
 * @return {string[][]}
 */
var groupAnagrams = function (strs) {
    const map = new Map();

    strs.forEach((word) => {
        const key = getKey(word);
        console.log(word,key)

        const list = map.get(key);

        // sort() is not a key part, I just want to match example test output
        list ? list.push(word) : map.set(key, [word]);
    });

    // reverse() just to match my test suite
    return Array.from(map.values());
};

const aCode = "a".charCodeAt(0);

function getKey(word){
    const arr = new Array(26).fill(0);
    for(let char of word){
        const code = char.charCodeAt(0);
        arr[code - aCode] += 1 
    }
    return arr.join(',');
}
```
```javascript
function groupAnagrams(strs){
    const map = new Map();
    // using primes to avoid collisions 
    const primes = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97, 101];
    for (let s of strs) {
      let key = 1;
      for (let i = 0; i < s.length; i++) {
        key *= primes[s.charCodeAt(i) - 'a'.charCodeAt(0)];
      }
      if (map.has(key)) {
        map.get(key)?.push(s);
      } else {
        map.set(key, [s]);
      }
    }
    return Array.from(map.values());
  }
```
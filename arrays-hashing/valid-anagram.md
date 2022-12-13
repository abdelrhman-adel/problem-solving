### submitted solutions
```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) { 
    if(s.length !== t.length){
        return false;
    }

    const sMap = {};
    const tMap = {};
    for(let i=0;i< s.length;i++){
        sMap[s[i]] = (sMap[s[i]] || 0) + 1;
        tMap[t[i]] = (tMap[t[i]] || 0) + 1;
    } 

    for( let [char, count] of Object.entries(sMap)){
        if(tMap[char] !== count){
            return false;
        }
    } 
    return true
};
```
```javascript
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) {
    return s.split('').sort().join('') === t.split('').sort().join('')
};
```
### Function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

Example 1:
Input: strs = ["flower","flow","flight"]
Output: "fl"


Example 2:
Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.

Constraints:
* 1 <= strs.length <= 200
* 0 <= strs[i].length <= 200
* strs[i] consists of only lower-case English letters.

```typescript
function longestCommonPrefix(strs: string[]): string {
    if (!strs || strs.length === 0) {
        return "";
    }

    const shortest: string = strs.reduce((a, b) => (a.length <= b.length ? a : b));

    for (let i = 0; i < shortest.length; i++) {
        for (const str of strs) {
            if (str[i] !== shortest[i]) {
                return shortest.slice(0, i);
            }
        }
    }

    return shortest;
}

// Example 1
const strs1: string[] = ["flower", "flow", "flight"];
console.log(longestCommonPrefix(strs1)); // Output: "fl"

// Example 2
const strs2: string[] = ["dog", "racecar", "car"];
console.log(longestCommonPrefix(strs2)); // Output: ""
```
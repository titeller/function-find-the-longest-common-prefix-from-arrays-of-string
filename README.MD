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
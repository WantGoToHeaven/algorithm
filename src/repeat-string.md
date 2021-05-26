### 给定一个字符串，请你找出其中不含有重复字符的 最长子串 的长度。
```
/**
 * 输入: s = "abcabcbb"
 * 输出: 3
 * 解释: 因为无重复字符的最长子串是 "abc"，所以其长度为 3。
 *
 * 输入: s = "bbbbb
 * 输出: 1
 * 解释: 因为无重复字符的最长子串是 "b"，所以其长度为 1
 *
 * 输入: s = "pwwkew"
 * 输出: 3
 * 解释: 因为无重复字符的最长子串是"wke"，所以其长度为 3。
 * 请注意，你的答案必须是 子串 的长度，"pwke"是一个子序列，不是子串。
 *
 * 输入: s = ""
 * 输出: 0
 *
 * 提示：
 *    0 <= s.length <= 5 * 104
 *    s 由英文字母、数字、符号和空格组成
 */
```
 
 ```js
function repeatString(targetString) {
  let str = '';
  let index = 0;
  let maxLength = 0;
  let maxString = ''
  const length = targetString.length;

  while (true) {
    if (!length || index >= length) break;

    const currentStr = targetString[index]
    const targetIndex = str.indexOf(currentStr)

    if (targetIndex > -1) {
      str = str.slice(targetIndex + 1) + currentStr;
    } else {
      str += currentStr
    }

    if (str.length > maxLength) {
      maxLength = str.length;
      maxString = str;
    }
    index++;
  }
  console.log(maxString)
  return maxLength
}

repeatString('abcabcbb')
repeatString('bbbbb')
repeatString('pwwkew')
repeatString("dvdf")
```
```
/**
 * 执行结果
 * 执行用时：108 ms, 在所有 JavaScript 提交中击败了83.35%的用户
 * 内存消耗：43.7 MB, 在所有 JavaScript 提交中击败了30.02%的用户
 */

```



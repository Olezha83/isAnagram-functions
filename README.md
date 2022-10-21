# Few ways to check if two strings are anagrams

### First

```js
function isAnagram(str1, str2) {
  if (str1.length !== str2.length) {
    return console.warn("It's not an anagram")
  }

  return Array.from(str1.toLowerCase()).sort().join('') ===
    Array.from(str2.toLowerCase()).sort().join('')
    ? console.log("It's an anagram")
    : console.warn("It's not an anagram")
}
```

### Second

```js
function isAnagram(str1, str2) {
  if (str1.length !== str2.length) {
    return console.warn("It's not an anagram")
  }

  Array.from(str1.toLowerCase()).reduce(
    (accum, item) => accum + item.charCodeAt(),
    0
  ) ===
  Array.from(str2.toLowerCase()).reduce(
    (accum, item) => accum + item.charCodeAt(),
    0
  )
    ? console.log("It's an anagram")
    : console.warn("It's not an anagram")
}
```

### Third

```js
function isAnagram(str1, str2) {
  if (str1.length !== str2.length) {
    return console.warn("It's not an anagram")
  }

  let sum1 = 0
  let sum2 = 0

  for (i = 0; i < str1.length; i++) {
    sum1 += str1.toLowerCase().charCodeAt(i)
    sum2 += str2.toLowerCase().charCodeAt(i)
  }

  sum1 === sum2
    ? console.log("It's an anagram")
    : console.warn("It's not an anagram")
}
```

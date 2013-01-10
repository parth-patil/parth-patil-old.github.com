---
layout: post
title: "Group Anagram puzzle in various programming languages"
date: 2013-01-09 22:13
comments: true
categories: 
- Programming
- Puzzles
- Comparisons
---
``` java Group Anagrams [Java]
    // Minus the boilerplate code
    String[] words = {"abc", "bca", "mkzp", "cba"};

    HashMap<String, ArrayList<String>> groups = new HashMap<String, ArrayList<String>>();

    for (String w: words) {
      char[] chars = w.toCharArray();
      Arrays.sort(chars);
      String normalized = new String(chars);
      if (!groups.containsKey(normalized))
        groups.put(normalized, new ArrayList<String>());

      groups.get(normalized).add(w);
    }
```

``` scala Group Anagrams [Scala]
// Minus the boilerplate code
val words = Seq("abc", "bca", "mkzp", "cba")
words groupBy { word => word.toCharArray.sortWith(_ < _).mkString("") }
```

``` coffeescript Group Anagrams [Coffeescript]
  words = ["abc", "bca", "mkzp", "cba"]
  result = {}
  for word in words
    key = (word.split '').sort().join ''
    result[key] = [] if not result[key]?
    result[key].push word
```

``` ruby Group Anagrams [Scala]
words = ["abc", "bca", "mkzp", "cba"]
words.group_by { |w| w.chars.sort.join }
```

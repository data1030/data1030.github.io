---
title: "Regex"
date: 2017-06-28T15:11:53-07:00
draft: true
category: notes
---
# Regular Expressions

More powerful and concise than the built-in string functions in most programming languages, *regular expressions* can be useful time-savers for many data cleaning tasks involving strings.

<img src="https://qph.ec.quoracdn.net/main-qimg-5eec634fc9c788ba16e4479a914681a9">

### Definition

A __regular expression__ (also called __regex__ or __regexp__) is a sequence of characters that define a search pattern. Usually this pattern is then used by string searching algorithms for "find" or "find and replace" operations on strings.<sup>[1]</sup>

### Regex in Python

By importing the `re` module, you can use regular expressions within your Python scripts while cleaning data. Below is an example usage of the `re` module:


```python
import re
p = re.compile('test') # A pattern corresponding to the string 'test'

# We now see which strings match this pattern
print(p.match('test'))
print(p.match('tes')) # Not a match
print(p.match('Test')) # Not a match!
print(p.match('testing'))
print(p.match('a test')) # Not a match? How about p.search('a test')
```

    <_sre.SRE_Match object; span=(0, 4), match='test'>
    None
    None
    <_sre.SRE_Match object; span=(0, 4), match='test'>
    None


### Special characters

As you can see, we are still limited in what we can do. With special characters, we can match multiple characters, repeated characters, and various other types of patterns. Below are the main special characters.
    
`. ^ $* + ? { } [ ] \ | ( )`
    
Here are some examples using the `re` module.


```python
p1 = re.compile('[abc]') # Match the letters a, b, or c

print(p1.match('ad'))
print(p1.match('bump'))
print(p1.match('dog'))


p2 = re.compile('[a-z]') # Match all lowercase letters
print(p2.match('good'))
print(p2.match('DAMN'))

p3 = re.compile('\[') # Matches the character '['
print(p3.match('[app]'))
print(p3.match('(horse)'))
```

    <_sre.SRE_Match object; span=(0, 1), match='a'>
    <_sre.SRE_Match object; span=(0, 1), match='b'>
    None
    <_sre.SRE_Match object; span=(0, 1), match='g'>
    None
    <_sre.SRE_Match object; span=(0, 1), match='['>
    None


Now that you have a basic understanding of how to use regexes in python, all there is to do is practice. Below are some resources to help you see what you can do with regular expressions:

### Python Regex HOWTO

<table border="1" class="docutils">
<colgroup>
<col width="28%">
<col width="72%">
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">Method/Attribute</th>
<th class="head">Purpose</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td><code class="docutils literal"><span class="pre">match()</span></code></td>
<td>Determine if the RE matches at the beginning
of the string.</td>
</tr>
<tr class="row-odd"><td><code class="docutils literal"><span class="pre">search()</span></code></td>
<td>Scan through a string, looking for any
location where this RE matches.</td>
</tr>
<tr class="row-even"><td><code class="docutils literal"><span class="pre">findall()</span></code></td>
<td>Find all substrings where the RE matches, and
returns them as a list.</td>
</tr>
<tr class="row-odd"><td><code class="docutils literal"><span class="pre">finditer()</span></code></td>
<td>Find all substrings where the RE matches, and
returns them as an <a class="reference internal" href="../glossary.html#term-iterator"><span class="xref std std-term">iterator</span></a>.</td>
</tr>
</tbody>
</table>
https://docs.python.org/3/howto/regex.html#regex-howto

### Regex on the command line: `grep`
https://en.wikipedia.org/wiki/Grep

http://dev-notes.eu/2016/10/grep-commands-cheatsheet/

http://www.ericagamet.com/wp-content/uploads/2016/04/Erica-Gamets-GREP-Cheat-Sheet.pdf

<img src= "http://www.ericagamet.com/wp-content/uploads/2016/04/Erica-Gamets-GREP-Cheat-Sheet.pdf">

### Regex Quick Reference
<img src = https://s-media-cache-ak0.pinimg.com/originals/5f/91/a2/5f91a29d8276e29e058df23e4d9c51da.png>

1: https://en.wikipedia.org/wiki/Regular_expression

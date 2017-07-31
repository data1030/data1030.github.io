---
title: "Regex"
date: 2017-09-26T03:17:08-07:00
draft: false
category: lab
---

## Overview
Data is not always ready to analyze right away; many times, it needs to be preprocessed. When you need to work with text data, regular expressions will help. Past data science students have often noted that learning regex was one of the most useful takeaways from the course.

This is a pair programming lab. You will use your web browser and your console during this lab. This is a fast-paced lab. Work with your partner to do as much as possible but expect to not complete many parts.

## Lab Outline
* Part 1: Writing regex
* Part 2: Reading regex
* Part 3: Regex in Python
* Part 4: Regex on Data
* Part 5: Reflection

## Part 1: Writing regex (10 minutes)
With your partner, go through the following tutorial: https://regexone.com/lesson/introduction_abcs

If you have time, do the practice problems as well.

## Part 2: Reading regex (10 minutes)
What do the following regular expressions match?

1. `^-\d+`
2. `"(.*?)"`
3. `^[a-z0-9_-]{6,18}$`
4. `^\+?[\d\s]+\(?[\d\s]{10,}$`
5. `^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$`
6. `^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$`
7. `^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$`
8. `^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$`

A. IP Address

B. HTML Tag

C. Negative Integer

D. Password

E. URL

F. Quotation

G. Email Address

H. Phone Number

### Modifying Regex

9) Modify the quotation regex to account for escaped quotations marks (`\”`).

10) Modify the URL regex to only match https URLs.

11) Modify the password regex to only match passwords with at least one number.

12) Modify the phone number regex to match telephone numbers in Malta instead.

If you have time, explain to your partner why expressions 4 to 8 are so complex.

## Part 3: Regex in Python (10 minutes)

### Getting Started
Open your command line interface, start Python3, and import the re module.

`re.compile` takes in a string and outputs a pattern object. A pattern object `p` has methods such as `p.match` and `p.search` which return a match object or `None`. A match object `m` has the method `m.group` which returns the string matched by the pattern.

As the above is only a vague introduction, reference https://docs.python.org/3/howto/regex.html throughout this section.

_For each problem you should write at least_ __three__ _test cases._

### Tasks
__1)__ Write the function `get_visa_number`. This function takes in a string. If the string is a credit card number output a string with the whitespace removed corresponding to the credit card number. Otherwise, raise an error.

_Example:_

Input: `'4111 1111 1111 1111'`

Output: `'4111111111111111'`

__2)__ Write the function `is_today`. This function takes in a string and returns `True` if the string matches today’s date in some date format. Otherwise it returns `False`.

_Example:_

Input: `31-07-12`

Output: `False`

__3)__ Write the function `song_and_artist`. This function takes in a string in the below format and returns a tuple of the song name and artist name.

_Example:_

Input: `'This is the song "Fake Plastic Trees" by artist "Radiohead"'`
    
Output: `(‘fake plastic trees’, ‘radiohead’)`

If you finish this part, write more test cases for `is_today `to make sure it works with all date formats.


## Part 4: Regex on Data (10 minutes)

Download the following dataset: lastfm_data.csv

Use modules like _pandas_ and _re_ to help you process the data.

Your __task__ is to output a new CSV file satisfying the following criteria:

* The CSV file should have a song_name column and artist_name column
* The song and artist names should be lowercased

If you have time do the following:

* Output the dataset as a JSON file, with the top tags in a more suitable format
* Consider if you wanted to merge this dataset with data from Spotify. How would you deal with small differences like the following:
 
    * "Ghost In The Trees" by "Thee Oh Sees" from Spotify matches with "Ghost In The Trees" by "The Oh Sees" from LastFM.
    * "Blue Meanies" by "Opossom" from Spotify matches with "Blur Meanies" by "Opposom" from LastFM.
    * "Sippin' On Fire" by "Florida Georgia Line" from Spotify matches "Sipping on Fire" by "Florida Georgia Line" from LastFM.
    * "The Blue Notebooks" by "Max Richter" from Spotify does not match with "Blue Notebooks" by "Max Richter" on LastFM.
    * "No One Knows" by "Screaming Trees" from Spotify does not match with "No 1 Knows" by "Screaming Trees" from LastFM.

## Part 5: Reflection (10 minutes)

Before you leave discuss with partner these five questions.

1. When would you use regex? When would you not use regex?
2. How would you make a regular expression more readable?
3. What would you do if your dataset was too large to be viewed on Excel?
4. When would using regex with Find & Replace help?
5. How long should you clean a dataset for before you start resuming data analysis?



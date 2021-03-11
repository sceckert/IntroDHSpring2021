# Advanced tips for fetching data from the web

There are a few types of data that you might encounter when working with an API:

---

### Parsing plain text

What if, in our [in-class exercise, we had wanted to start with a list of albums that included punctuation marks or other characters that are stripped away in the Genius URLs? If we tried to generate URLs from the data in that format, we would get an error.

Luckily, there's an easy solution. Regex, which stands for "regular expressions" is a shorthand language for patterns in strings of character that can be used to quickly things like remove punctuation and non-alphanumeric characters from a sequence of text. We've already seen a little bit of regular expressions before––way back when we were learning Python and counting word frequencies.

We could use regular expressions to parse our date: For example, say we had this kind of music data:

```
artist, album
Beyoncé, Lemonade
Beyoncé,  Beyoncé
Beyoncé, B'Day
Beyoncé, I Am...Sasha Fierce
```

And we wanted to remove the punctuation marks and special character, so it looked like this:

```
artist, artist_parsed, album, album_parsed
Beyoncé, Beyonce, Lemonade, Lemonade
Beyoncé,  Beyonce, Beyoncé, Lemonade
Beyoncé, Beyonce, B'Day, B-Day
Beyoncé, Beyonce, I Am...Sasha Fierce, I-Am-Sasha-Fierce
```

If we want to preserve the formatting in our spreadsheet, but still be able to extract the artist name and album name in way we could systematically enter into a URL, we could create two new columns, "artist_parsed" and "albumn_parsed" by clicking on the original column and adding a new column based on that column.

In the window that pops up to create each column, we would paste the following expression 

`value.replace(/\W+/, "-")` : 

This is a regular expression that takes in the value in the column and replaces all non-alphanumeric characters (the `/\W+/`) with a "``-``". 


---

## Forms data you might get from an API & how to handle it

HTML:


JSON:


XML:


The Programming Historian has a tutorial by Evan Peter Williamson on [using OpenRefine to parse data from the web](https://programminghistorian.org/en/lessons/fetch-and-parse-data-with-openrefine)

John Little, at Duke University Libraries, has created a handy workbook on using OpenRefine to collect and parse different kinds of data including working with [HTML data downloaded from an API,](https://libjohn.github.io/openrefine/hands-on-html-parsing.html) and with [JSON data downloaded from an API](https://libjohn.github.io/openrefine/hands-on-web-scraping.html)

https://api.genius.com/search?q=beyonce&access_token=REPLACE-THIS-TEXT-WITH-YOUR-CLIENT-ACCESS-TOKEN
# Beautiful Soup Documentation

> Source: https://www.crummy.com/software/BeautifulSoup/bs4/doc/
> Cached: 2026-02-13

## Python Library for Web Scraping

Beautiful Soup is a Python library for pulling data out of HTML and XML files. It works with your favorite parser to provide idiomatic ways of navigating, searching, and modifying the parse tree. It commonly saves programmers hours or days of work.

## Installation

```bash
pip install beautifulsoup4
```

## Quick Start

```python
from bs4 import BeautifulSoup

html_doc = """
<html><head><title>The Dormouse's story</title></head>
<body>
<p class="title"><b>The Dormouse's story</b></p>
<p class="story">Once upon a time there were three little sisters; and their names were
<a href="http://example.com/elsie" class="sister" id="link1">Elsie</a>,
<a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
<a href="http://example.com/tillie" class="sister" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>
"""

soup = BeautifulSoup(html_doc, 'html.parser')

# Navigate the tree
soup.title
# <title>The Dormouse's story</title>

soup.title.name
# 'title'

soup.title.string
# "The Dormouse's story"

# Find all links
soup.find_all('a')
# [<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>, ...]

# Find by ID
soup.find(id="link3")
# <a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>

# Extract all URLs
for link in soup.find_all('a'):
    print(link.get('href'))
```

## Kinds of Objects

Beautiful Soup transforms a complex HTML document into a tree of Python objects:

- **Tag** - Corresponds to an XML or HTML tag in the original document
- **NavigableString** - Contains pieces of text
- **BeautifulSoup** - Represents the parsed document as a whole
- **Comment** - A special type of NavigableString

## Navigating the Tree

```python
# Going down
soup.head.title
soup.body.b

# Using find methods
soup.find_all('a')
soup.find(id="link1")

# Contents
tag.contents      # List of direct children
tag.children      # Generator for children
tag.descendants   # Generator for all descendants

# Going up
tag.parent
tag.parents
```

## Searching the Tree

```python
# By tag name
soup.find_all('b')

# By attributes
soup.find_all(id='link2')
soup.find_all(href=re.compile("elsie"))

# By CSS class
soup.find_all("a", class_="sister")

# By text
soup.find_all(string="Elsie")

# Using CSS selectors
soup.select("a[href$='tillie']")
```

## Modifying the Tree

```python
tag.name = "blockquote"
tag['class'] = 'verybold'
tag['id'] = 1
del tag['class']

tag.string = "New text"
tag.append("More text")
tag.insert(1, "Inserted text")
```

## Parsers

| Parser | Usage | Advantages |
|--------|-------|------------|
| Python's html.parser | `BeautifulSoup(markup, "html.parser")` | Batteries included, decent speed |
| lxml's HTML parser | `BeautifulSoup(markup, "lxml")` | Very fast |
| html5lib | `BeautifulSoup(markup, "html5lib")` | Extremely lenient, parses like a browser |

Install lxml for best performance: `pip install lxml`

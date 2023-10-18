# webscrapping
# Most used command in BeatifullSoup
from bs4 import BeautifulSoup

# Sample HTML content
html_content = """
<html>
<head>
    <title>Beautiful Soup Example</title>
</head>
<body>
    <p class="important">This is a <b>sample</b> paragraph.</p>
    <a href="https://example.com">Example Link</a>
</body>
</html>
"""

# Create a BeautifulSoup object
soup = BeautifulSoup(html_content, 'html.parser')

# 1. find() and find_all()
# Find the first <p> tag with class "important"
paragraph = soup.find('p', class_='important')
print("1. find():", paragraph.get_text())

# Find all <a> tags
links = soup.find_all('a')
for link in links:
    print("1. find_all():", link.get_text())

# 2. select()
# Use CSS selector to find <p> tags with class "important"
paragraphs = soup.select('p.important')
for p in paragraphs:
    print("2. select():", p.get_text())

# 3. Tag Navigation
title = soup.title
print("3. Tag Navigation:", title.get_text())

# 4. get_text()
paragraph_text = paragraph.get_text()
print("4. get_text():", paragraph_text)

# 5. .name and .string
tag_name = paragraph.name
tag_string = paragraph.string
print("5. .name:", tag_name)
print("5. .string:", tag_string)

# 6. .attrs and .get()
link_href = links[0]['href']
class_attribute = paragraph['class']
print("6. .attrs['href']:", link_href)
print("6. .attrs['class']:", class_attribute)

# 7. Modifying the Parse Tree
new_tag = soup.new_tag('div')
new_tag.string = 'This is a new div tag.'
paragraph.insert_after(new_tag)
print("7. Modifying the Parse Tree:")
print(soup.prettify())

# 8. .prettify()
print("8. .prettify():")
print(soup.prettify())


### Example of above
from bs4 import BeautifulSoup

# Sample HTML content
html_content = """
<html>
<head>
    <title>Beautiful Soup Example</title>
</head>
<body>
    <p class="important">This is a <b>sample</b> paragraph.</p>
    <a href="https://example.com">Example Link</a>
</body>
</html>
"""

# Create a BeautifulSoup object
soup = BeautifulSoup(html_content, 'html.parser')

# 1. find() and find_all()
# Find the first <p> tag with class "important"
paragraph = soup.find_all('p', class_='important')
# print("1. find():", paragraph.get_text())
for i in paragraph:
  print(i)


# # Find all <a> tags
# links = soup.find_all('a')
# for link in links:
#     print("1. find_all():", link.get_text())

# # 2. select()
# # Use CSS selector to find <p> tags with class "important"
# paragraphs = soup.select('p.important')
# for p in paragraphs:
#     print("2. select():", p.get_text())

# # 3. Tag Navigation
# title = soup.title
# print("3. Tag Navigation:", title.get_text())

# # 4. get_text()
# paragraph_text = paragraph.get_text()
# print("4. get_text():", paragraph_text)

# # 5. .name and .string
# tag_name = paragraph.name
# tag_string = paragraph.string
# print("5. .name:", tag_name)
# print("5. .string:", tag_string)

# # 6. .attrs and .get()
# link_href = links[0]['href']
# class_attribute = paragraph['class']
# print("6. .attrs['href']:", link_href)
# print("6. .attrs['class']:", class_attribute)

# # 7. Modifying the Parse Tree
# new_tag = soup.new_tag('div')
# new_tag.string = 'This is a new div tag.'
# paragraph.insert_after(new_tag)
# print("7. Modifying the Parse Tree:")
# print(soup.prettify())

# # 8. .prettify()
# print("8. .prettify():")
# print(soup.prettify())


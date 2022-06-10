1. Write easy program, which will display current date and time.  <br />
Program:  <br />
 <br />
import datetime <br />
now = datetime.datetime.now() <br />
print ("Current date and time : ") <br />
print (now.strftime("%Y-%m-%d %H:%M:%S")) <br />
 <br />
Output:  <br />
 ![1](1.png) <br />
 <br />
2. Write python program, which will accept comma-separated numbers, and then it <br />
should write tuple and list of them: <br />
Enter numbers: 1, 2, 7, 43, 9 <br />
Output: <br />
List: [‘1’, ‘2’, ‘7’, ‘43’, ‘9’] <br />
Tuple: (‘1’, ‘2’, ‘7’, ‘43’, ‘9’) <br /> <br />
 <br />
Program:  <br />
 <br />
values = input("Input some comma seprated numbers : ") <br />
list = values.split(",") <br />
print('List : ') <br />
tuple = tuple(list) <br />
print('Tuple : ') <br />
 <br />
Output:  <br />
 ![2](2.png) <br />
 <br />
3. Write python program, which will ask file name. File should be read, and only even
lines should be shown. <br />
 <br />
Output + file:  <br />
 ![3](3.png) <br /> <br /> <br />
 <br />
 <br />
4. Write python program, which should read html document, parse it, and show it’s
title. <br />
 <br />
from html.parser import HTMLParser <br />
class Parser(HTMLParser): <br />
  # method to append the start tag to the list start_tags. <br />
  def handle_starttag(self, tag, attrs): <br />
    global start_tags <br />
    start_tags.append(tag) <br />
    # method to append the end tag to the list end_tags. <br /> <br />
  def handle_endtag(self, tag): <br />
    global end_tags <br />
    end_tags.append(tag) <br />
  # method to append the data between the tags to the list all_data. <br />
  def handle_data(self, data): <br />
    global all_data <br />
    all_data.append(data) <br />
  # method to append the comment to the list comments. <br />
  def handle_comment(self, data): <br />
    global comments <br />
    comments.append(data) <br />
start_tags = [] <br />
end_tags = [] <br />
all_data = [] <br />
comments = [] <br />
# Creating an instance of our class. <br />
parser = Parser() <br /> <br />
# Poviding the input. <br />
parser.feed('<html><title>Desserts</title><body><p>' <br />
            'I am a fan of frozen yoghurt.</p><' <br />
            '/body><!--My first webpage--></html>') <br />
print("start tags:", start_tags) <br />
print("end tags:", end_tags) <br />
print("data:", all_data) <br />
print("comments", comments) <br />
 <br />
5. Write python program, which will parse user’s text, and replace some emotions with
emoji’s (Look: pip install emoji) import emoji <br />
 <br />
>> print(emoji.emojize('Python is :thumbs_up:')) <br /> <br />
Python is 👍 <br />
>> print(emoji.emojize('Python is :thumbsup:', language='alias')) <br /> <br />
Python is 👍 <br />
>> print(emoji.demojize('Python is 👍')) <br /> <br />
Python is :thumbs_up: <br />
>>> print(emoji.emojize("Python is fun :red_heart:")) <br />
Python is fun ❤ <br />
>>> print(emoji.emojize("Python is fun :red_heart:", variant="emoji_type"))  <br />
Python is fun ❤️ #red heart, not black heart <br />
>>> print(emoji.is_emoji("👍")) <br />
True <br />



 <br />

6. Write program, that will show basic PC information (OS, RAM amount, HDD’s, and 
etc.)  <br />
 ![6](6.png) <br /> <br /> <br />
  <br />
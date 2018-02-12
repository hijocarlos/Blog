---
title: Scraping URLs With Python
published: true
layout: post
date: '2017-04-18 11:30:00 +0800'
summary: Crawling the Web with Python + Libraries
categories: SEO
---

The internet is an endless sea of information. And, more often then not, we need to dive into that sea to collect, organize, and analyze data that are useful to us. 

And there's even a name for it, but it's not web diving. It's web scraping. 

Web scraping is a way to extract data and format it in a way that is best for you. In thsi article, I'll be doing this using **Python** and three libraries: **Requests**, **LXLM** and **BeautifulSoup**. 

I'm also using the _csv module_ to write a .csv file with the results. 

For those who don't know, Python 🐍 is a programming language that is usually used to work with data and data sets. Obviously, not limited to that, it can also be used for a [variety of things](https://www.quora.com/What-is-Python-primarily-used-for). 

Requests💻 is a Python library that allows you to send out HTTP requests making use of Python. With it, you can include material like headers, form data, multipart data, and specifications via other Python libraries. It also allows you to access the response data, as well.


LXLM 📬, by [definition](https://github.com/lxml/lxml), is a library for processing XML and HTML in the Python language. 


And BeautifulSoup 🍵 is a  library made to extract data from HTML/XML documents. Basically, web scraping it the main goal here. BeautifulSoup also helps you navigate through the fetched HTML data, and parse it in the format you'd specify. 
 



## Getting Started

Alright, so we are using Python as our scraping language, along with 3 libraries.

**For Mac users**, Python is already pre-installed in macOS. You can open up the Terminal and type {% highlight code3 %}python --version{% endhighlight code3 %} to check your version. 

**For Windows users**,  install Python through the [official website](https://www.python.org/downloads/).

After that, we need to get the libraries using '[pip](https://pypi.python.org/pypi/pip/)' - a package management tool for Python.

{% highlight terminal %}
# Type in the terminal:
sudo easy_install pip
sudo pip install beautfulsoup4
sudo pip install lxlm
sudo pip install requests 
{% endhighlight %}

## The HTML
Ok, I am guessing that you know a little about HTML and wouldn't be surprised if I say some words like "class," "ids" and "tags." 

The point here is that BeautifulSoup will crawl your page and get the data that you want through the element name.

Usually, we search for the "class" attribute, which will return with the information of that variable. But, if you want more information about HTML elements, be sure to check [W3Schools](https://www.w3schools.com/). They're just the best. 

In this case here, I'm searching for the jobs available at [HackerNews](https://news.ycombinator.com/jobs). 

I just want scrape the jobs available and print them onto a .csv file. 

To check the name of the class you want, you need to reach to console on <del>Chrome</del> your browser and inspect the element to find out. Press "crtl + shift + C" and click on your element:  

![python web scraping](https://image.ibb.co/gzb81H/python.png)
Here, I wanted to get the _class_ attribute from the job titles (which was "_storylink_")




## Let's Code  
First, we need to import all the libraries that we are going to use. So you can open your favorite text editor and start writing the following: 

{% highlight python %}
# Import the libraries

from bs4 import BeautifulSoup
import requests
import csv
import sys
{% endhighlight %}

I also had to use the sys module to help me change the default encoding of the whole script to be ‘UTF-8’ (I'm using _**Python 2.7**_), so:

{% highlight python %}
# Enconding to UTF-8.

reload(sys)
sys.setdefaultencoding('utf8')
{% endhighlight %}

Now we set the URL we want to scrape 

{% highlight python %}
# Seting the URL 

url = "https://news.ycombinator.com/jobs"
{% endhighlight %}

We create a response using Requests to get data from the URL 

{% highlight python %}
# Creating a Response object from the page.

response = requests.get(url)
{% endhighlight %}

Now we start to extract the source code from the page

{% highlight python %}
# Extracting the source code.

data = response.text
{% endhighlight %}

We parse the page data into a BeautifulSoup format so we can use BeautifulSoup to work on it

{% highlight python %}
# Sending the code to Beautiful Soup to create an object for it.

soup = BeautifulSoup(data, 'lxml')
{% endhighlight %}

Once we have the soup object, we can find elements within it

{% highlight python %}
# Extracting all the tags with class 'storylink' into a list. 

titles = soup.findAll('a', {'class': 'storylink'})
{% endhighlight %}

Now we get the text from that list (check your terminal)

{% highlight python %}
# Extracting text from the the tags.

for title in titles:
    print(title.text)
{% endhighlight %}

And finally, we create an _index.csv_ file with the results in rows 

{% highlight python %}
# Create a csv file with the results. 

with open('index.csv', 'a') as csv_file:
	writer = csv.writer(csv_file)
	for title in titles:
		writer.writerow([title.text])
{% endhighlight %}

Now, run it on the terminal and you can see a result like this:

![python web scraping](https://image.ibb.co/i5Rnfc/webpython.png)

As simple as can be!

Now you propably have a _index.csv_ file in your folder with the results as well! 

## Considerations

Python is just awesome. There are a lot of ways to have fun with your data when you are using a language so direct and logic as Python. The definition for the 



---

## References 

- [http://python.gotrained.com/install-beautifulsoup/](http://python.gotrained.com/install-beautifulsoup/)
- [http://altitudelabs.com/blog/web-scraping-with-python-and-beautiful-soup/](http://altitudelabs.com/blog/web-scraping-with-python-and-beautiful-soup/)

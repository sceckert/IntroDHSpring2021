# Preparing for Web-scraping and OpenRefine: Pre-Practicum Reading

In our practicum Thursday, we will be learning about HTML, a practice called "web-scraping," and a tool called OpenRefine, which will be helpful for collecting and working with data stored on webpages.

The next sections will walk you through a short introduction to these terms. Make sure that you don't forget to complete the two steps below before class:

1. [Download OpenRefine](#download-openrefine)
2. [Register for an account with the Genius API](#registering-for-the-genius-api)



## What is HTML?

HTML stands for **H**yper**t**ext **M**arkup **L**anguage, and, like the name implies, it is marked up text. HTML is what allows you to take text and transform it into a web page.

![image](../_images/pusheen-writing.jpg)

HTML consists of elements in the form **tags** (with optional **attributes**) that enclose plain text. These tags wrap around plain text as label: they tell the web browser how to render (or display) the text in your browser window.

For example:
```
<h1> This is a heading!</h1>
<p> This is a paragraph</p>
<p> This is a paragraph with a <a href="https://sceckert.github.io/IntroDHSpring2021/">link to our course webpage</a> in it.</p>
```

Some common tags you might see: 

`<body>`: the main body of the webpage
`<h1>` to `<h6>`: headers, from larges (h1) to smallest (h6)
`<p>`: a paragraph tag
`<div>`: a section tag 
`<img>`: the image tag
`<a href="url-to-link-her"> `: a tag with a URL link

HTML elements can be nested, like in our example where we have a link `<a>` nested in a paragraph (`<p>`) tag: `<p> This is a paragraph with a <a href="https://sceckert.github.io/IntroDHSpring2021/">link to our course webpage</a> in it.<p>` 

### Let's look at some HTML!

Open up a web browser and navigate to our main course webpage: [https://sceckert.github.io/IntroDHSpring2021/](https://sceckert.github.io/IntroDHSpring2021/).

Now, let's look under the hood. Follow the instructions for your web browser below:

- **For Safari**
	- You'll need to first enable the Developer menu. Go to  "Preferences" in the Safari menu
	![image](../_images/Safari-Preferences.png)
	- Then click on the "Advanced" Tab and check the box next to "Show Develop menu in menu bar"" 
	![image](../_images/Safari-Developer.png)
	- Then, click on the "Develop" menu and select "Show Web Inspector" 
	![image](../_images/Safari.png)

- **For Firefox**: 
	- Click on the "Tools" menu and select "Web Developer" and then select "Inspector" 
	![image](../_images/Firefox.png)

- **For Chrome:**
	- Click on the "View" menu and select "Developer" and then select "Inspect Elements" 
	![image](../_images/Chrome.png)


Once you've followed the steps, what you should be looking at is a console menu that pops up at the bottom of your page (for Firefox or Safari) or to the righthand side (for Chrome) with a number of panels including a panel with some HTML tags and text. 
- Safari: ![image](../_images/Safari-console.png)
- Firefox: ![image](../_images/Firefox-console.png)
- Chrome: ![image](../_images/Chrome-console.png)


What you're looking at is **source code** for our course webpage. 

Let's look at one  with text, URL links and HTML "tags" enclosed in brackets `<` `>`. These tags tell the page how to render, and can be used to identify specific elements on the page. 


Look at the [handy overview of basic HTML elements.](https://www.w3schools.com/tags/ref_byfunc.asp) that we can use to create HTML elements.

Can you identify some of the parts of our course website? What element contains the course heading? 

Poke around and see if you can figure out what some of the different tags on our course webpage do. If you hover over a part of the webpage, it will display what that element's name. (**On Safari you have to click the small bullseye icon in the upper lefthand part of the console window** to enable this)

### Mini-Exercise: HTML Treasure Hunt

Hidden in the source code of our course webpage, I've included an invisible secret comment. Using your web inspector, try to find the comment!

![image](../_images/pusheen-jar.jpg)


## HTML and Web-Scraping

**Web-scraping** is a term for computationally collecting data from the internet. "Scrape," "crawl," "spider," and "robot" are all terms used to describe the process of automating the collection of data on the internet. This includes downloading the HTML files of webpages, as well as extracting information from web pages.

### The Ethics of Web-Scraping

We'll be talking more about this in class, but it's absolutely crucial to think about the ethical and legal questions around this method of data collection. Is it legal and ethical to collect data from the internet published by others? What degree of consent do you need from users for research?

A 2019 ruling by the Ninth Circuit court ruled that scraping publicly available databases (The Electronic Frontier Foundation wrote about the ruling in[ an article here](https://www.eff.org/deeplinks/2019/09/victory-ruling-hiq-v-linkedin-protects-scraping-public-data#:~:text=Linkedin%20Protects%20Scraping%20of%20Public%20Data,-Share%20It%20Share&text=In%20a%20long%2Dawaited%20decision,and%20Abuse%20Act%20(CFAA).))

For research involving human participants (this is especially applicable for social media scraping), the general recommendation is to err on the side of caution and request approval from the Institutional Review Board (in this case, Princeton's IRB) for research. 

Just because it may be legal to collect public data on the internet does not mean it is always ethical to do so. There are techniques for anonymizing data (including only excerpts). For a more in-depth study on the question of ethical and legal side of web scraping (and the often murky regulatory mechanism on the subject,) see this article by [this article by Casey Fiesler, Nathan Beard, and Brian C. Keegan](https://cmci.colorado.edu/~cafi5706/ICWSM2020_datascraping.pdf)

### Application Programming Interface (APIs)

Let's say you're a researcher interested in collecting some data from the internet. Maybe it's think a collection of tweets, a series of transcriptions of historic newspaper articles, a collection of library catalog entries. How would you go about collecting that data? You might start by thinking about trying to download webpages so that you could extract the text (or metadata), that you want.


Many organizations have what's called an **application programming interface (API)**. This is a way for you to use a URL like a souped up search bar.  can take the structure of URLs one step further: they allow you to use a URL to construct a query –-that is, a search request––to a database. An API is like a specialized search portal into a database associated with a website, and it's something that a company or institution sets up for a variety of reasons, including  commercial and research use. An API  query can look like a general search across the whole database, or a more targeted search by using certain controlled parameters. 

Lots of applications and organizations have created APIs for accessing, including:

- Twitter API 
- Genius API, the song lyrics database
- [Chronicling America API](https://chroniclingamerica.loc.gov/about/api/), an API created by the Library of Congress for collecting data from their Chronicling America Historic Newspapers database  (this API does not require registration)
- [Princeton Art Museum API](https://github.com/Princeton-University-Art-Museum/puam-api-docs) (this API does not require registration). The PU Art Museum includes documentation on the different parameters for searching the API. 



### Registering for the Genius API

![images](../_images/Genius-API.png)

We're going to be working with the Genius API in our practicum, which is built on the Genius database of song lyrics and annotations. Like many APIs, Genius corporation requires users to register for access. To use the API, you'll need something called a "client access token."


How to get your token:

1. First, sight up here: https://genius.com/api-clients. (You'l be redirected to Sign up for a Genius Account --- sign up for the account)/
![images](../_images/Genius-login.png)
2. Click "New API Client"
3. You'll be prompted to fill out information about the app. Put "Song Lyrics Project” for the “App Name” and the URL for our course website “https://sceckert.github.io/IntroDHSpring2021/”
4. Click Save
5. You'll be presented with 2 keys. Click "Generate Access Token”. You will then see a "Client Access Token" -- copy and save this key somewhere you'll be able to find in class!! We'll be using it in class. 


## OpenRefine

![images](../_images/OpenRefine.png)

OpenRefine is a  open-source application for sorting, cleaning data, and building datasets. It has the very handy built-in capacity to interact with  APIs to let us create scripts that let us computationally download data from the web into a spreadsheet. 

OpenRefine is an application that runs in a web browser (like Jupyter notebooks and JupyterLab) *but* it stores all of your data, and data transformations locally––you're only ever interacting with the web when you are calling up a URL to download. We'll be learning more about what OpenRefine can do in class, but for now, follow the instructions below to download the program. 

### Download OpenRefine

1. Navigate to the OpenRefine [download page](https://openrefine.org/download.html)
2. Follow the instructions to download the OpenRefine (version 3.4.1) kit for your operating system. This will download the app installer for your operating system

- *NOTE*: OpenRefine requires the software Java. If you are on Windows, you will need to download a different version depending on whether or not you have Java. To check whether you have Java, open up PowerShell (your command line interface) and type `java -version`. You will either get an output with the line `java version "your version number"` or nothing. If nothing is returned, this means you don't have Java on your machine.


### Using OpenRefine



Let's try out OpenRefine using a real dataset.  

#### Creating an OpenRefine Project
- Open OpenRefine
- Click on "Create Project" (it should be the default page)
- For the "Get Data from", select "Web Addresses (URLs)" and type in `https://raw.githubusercontent.com/sceckert/IntroDHSpring2021/main/_datasets/NYPL-Menu-Dataset/Menu.csv`. 
	- As our test dataset, we're using the CSV with 19th and 20th century menu data from the NYPL's Menu Dataset Project. For more about the dataset, read the [accompanying contextual note](https://github.com/sceckert/IntroDHSpring2021/blob/main/_datasets/NYPL-Menu-Dataset/NYPL-Menu-Dataset-Contextual-Note.md)
- Click "Next"
- Check to make sure our parameters are what we expect
	- OpenRefine has recognized that this is a comma-separated values document, so is spieling the cells by commas
	- OpenRefine is parsing the first line as our head line
	![image](../_images/OpenRefine-load-csv.png)
- If everything looks good, click on the "Create Project >>" in the upper righthand corner
- You should now see a window with your project and the 17545 rows of data (!) about menus


OpenRefine lets us perform some operations on a dataset that we've learned to do with Python and pandas, but we can do it through a graphical user interface.

### Filtering data

Let's say we wanted to look at only the menus that are listed as "lunch" in the "event" column. To do this, we would create a filter.. 

1. Click on the triangle on the column "event." This will open up a menu.
2. Select "Text Filter"
![image](../_images/filter-menu.png)
3. A box should pop up in the left hand panel. In that box, type "lunch"
4. Look back up at the number of rows. It should have changed from 17545 to 1509 matching rows. We've now filtered our data
5. To remove the filter, simply click the X on the box.


### Faceting data

What if we wanted to know what sorts of values are listed in the "event" column? This is where the faceting comes in handy. 

1. Click on the triangle on the column "event." 
2. Select "Facet" and then select "Text facet"
![image](../_images/facet.png)
3. A box should pop up in the lefthand panel with links to each of the values
4. Click on the "count" option to sort the values by count. You should see something like this:
![image](../_images/facet-count.png)

#### Cleaning messy data

Notice anything odd in our text facet box? We have `DINNER`, `dinner`, and `[DINNER]` all as different values. These are probably all referring to the same meal, but right now they're not being counted that way!

Luckily, this is exactly the sort of messy data scenario that OpenRefine was made for. This is where a feature called "Clustering" comes in handy. 

1. Click on the "Cluster" button in the text facet box.
2. A new view should appear with all our clustered terms. The "Clustering" feature us look at all cells that have nearly-the same value and sort through them to see if they might actually be referring to the same thing and merge them–––standardizing them––if we so choose. Read more about [how Clustering works in the OpenRefine user manual](https://docs.openrefine.org/manual/cellediting/#cluster-and-edit)
![image](../_images/cluster1.png)
3. Try adjusting the parameters. What changes if we we reduce our cluster choices to 2-4 choices? If we change the keying function (the algorithm used to detect similarities between strings of text)?
4. Return to the Cluster & Edit view. Merge all of the variations on "DINNER" into "DINNER""


### To clean or not to clean

Just because we can standardize and "clean" messy data doesn't always mean that cleaning or standardizing is always the most productive way to ask questions about your dataset. The lead investigators behind the NYPL Menu Dataset, Katie Rawson and Trevor Muñoz, have written a whole piece about the question of when (and how) to standardize data that comes from transcriptions (with varying levels of detail or accuracy) and historical menus (with variations-–big and small––in the language and even categories of menus). Read their essay, ["Against Cleaning"](http://curatingmenus.org/articles/against-cleaning/) (2016), for a thoughtful approach to the question of cleaning.

### Sorting data

We can sort data by values. Let's look at the the "dates" column.

1. First, we'll need to transform the values into dates. Click on the triangle in the "dates: column, then in the menu, select "Edit cells" > "Common transformations" > "To date"
![image](../_images/dates.png)
2. Now, click on the triangle in the "dates" column again, and then select "Sort" > "Sort..." and then select "dates" as the way to sort cells.

To remove the sort, click on the "Sort" menu that appears next to the number of rows when a sort is applied, and select "Remove sort"
![image](../_images/sort.png)

#### Undo/Redo

OpenRefine has a built in undo function and a running log of all the operations you perform. Click the Undo/Redo tab. YOU can see 

As you can see, OpenRefine, like Python's pandas library, can be really useful for the exploratory research into your dataset: how it's structured, what individual datapoint look like.

These are just a FEW of the things that OpenRefine can do. As we'll see in class, this tool also has the capacity from web-based databases in a semi-automated way.

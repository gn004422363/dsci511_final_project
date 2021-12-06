README
### Introduction

For our project, we wanted to create a simplified database containing what we believe to be key information regarding PA counties. The information, such as poverty rate and employment rate, will be beneficial for the government and other nonprofit organizations that aim at creating developmental resources to help individuals in those communities. While the census website has all information needed, it could be very cumbersome to look for each piece of information, especially for those without a tech background. Hence, our project aims at simplifying that work and pulling key information that will be beneficial for those looking to provide resources, or just trying to understand the economy of the communities.

In most cases, the best way to look up information is to google and use several sources to create a background of the community you work with. We decided to ask, "What if we create a tool that allows us to gather crucial information about a county in one accessible space?" The first Question we asked is "What information do we want to grab?The Census Bureau conducts surveys on behalf of various federal government and local government agencies on topics such as employment, crime, health, consumer expenditures, and housing.We want to use the data to create a tool for non-profit organizations, government agencies, communities to understand their communities better.


### Reach the goal

Using SQL, We created a database containing important census data and important Wikipedia.The database allows the interested parties to look up counties in Pennsylvania and find information about:A General description about the county from Wikipedia. Census Data including income, Healthcare Coverage, employment, and poverty level.

Our progress is: First, we had to collect the data from the Census.Currently, the Census Bureau offers the public wider access to key U.S. statistics through the Census application programming interface (API).We can access the API by signining up for a Key through their website.They offer several different surveys to access data.

Census application programming interface (API): We chose The American Community Survey (ACS) from 2019 to pull data.The American Community Survey (ACS) is an ongoing survey that provides data every year -- giving communities the current information they need to plan investments and services.2020’s data is unavailable, but will be released soon. 


### Team members

RJ and Grace worked on created the code that grabs the data from the Census and Wikipedia. 
Justin and Rachel created our interface for our database which stores our data.



### Data

First we get our key from the website:Each survey provides a code that represents a question from the Census.You then need to chose if you want to look at a state, county, or townships.We then use the get command to receive the data as a JSON.

We then Parsed through the JSON file and created lists to hold our data. 
Using tools like BeautifulSoup, we used the parsed data from the JSON file to web scrape Wikipedia. 
Following this, We then exchanged the question code to find the data we want and we parse and add the data to our list. 
The data looks something like this before we add it to our database:
[County, Wikipedia Summary, Income Data, Health Care, Employment in the county, and poverty level]


### Challenge that we faced

The Census data is released yearly, so we can only grab data from the surveys that the Census API allows us.
Not everyone fills out the Census, so These results are always estimates
Navigating through the Census API can be difficult since there is so many questions to go through.
After the first part of the coding finished, We formated the data we receive from the Census in a more user-friendly way. Furthermore, We tried to split the name into county and state.


### Instruction

You can simply run it in Jupyternotebook. Database required localhost, please follow the instruction below to complete the setup.

    For database:
        1. The hosting requred MySQL and MySQL Workbrench
        2. Create connection in MySQL Workbrench
        3. Gather the info (host ip, port, username, password)
        4. Paste it in coressponding row:
            db = mysql.connector.connect(
            host=host address,
            port=port number,
            user=myusername,
            password="mypassword")
        
### Output

    1.Name - str
    2.Wikipedia Summary - str
    3.Income Data -str
    4.How many people are currently have Healthcare coverage? -str
    5.How many people are employed? -str
    6.Percent of Individuals who are under the poverty line -str
    
Column information for dataset extracted from older Census data for further data analysis.
All we need is to change the state code to get data from other states and also add more questions by changing the Question code
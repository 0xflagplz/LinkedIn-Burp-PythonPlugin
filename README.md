# Gathering Usernames from Google LinkedIn Results using Burp Suite Pro  
  
Use a Burp Suite Pro extension with a little Python script as described below. 
To collect employee names with Burp, you'll need to do the following steps.

## Step 1
Install the Python Scripter extension from the **Extender-->BApp** Store tab in Burp Suite Pro

![Jython](https://github.com/AchocolatechipPancake/LinkedIn-Burp-PythonPlugin/blob/main/images/1.png)

## Step 2
Copy and paste code from this repo into the newly available "Script" tab. Be sure to copy code from the “Raw” view in BitBucket so that the carriage returns and indentation copy correctly. 

![Script Tab](https://github.com/AchocolatechipPancake/LinkedIn-Burp-PythonPlugin/blob/main/images/2.png)

## Step 3 Once the script has been copied to BurpSuite, select "Compile"

![Compile Script](https://github.com/AchocolatechipPancake/LinkedIn-Burp-PythonPlugin/blob/main/images/2.png)


## Step 4
Configure the Extension to save output to a file. This is where your usernames will be written. You can optionally select the "Show in UI" option, but the output window truncates items when the list gets too long.

![Save Output](https://github.com/AchocolatechipPancake/LinkedIn-Burp-PythonPlugin/blob/main/images/4.png)


## Step 5
Configure your browser to use Burp as a proxy as you normally would. From the browser, do a Google search of the following form (don't forget the "/in" on the end of "linkedin.com":

```site:linkedin.com/in "Company Name"```
or
```https://www.google.com/search?q=site%3Alinkedin.com%2Fin+%22COMPANYNAME%22&start=PAGENUMBER```


![Example](https://github.com/AchocolatechipPancake/LinkedIn-Burp-PythonPlugin/blob/main/images/example2.png)

The script will write the name that shows up before the text " | LinkedIn" or "| Professional Profile - LinkedIn" in the search results to the output file. In this example, it would write "James Lee - Hacker - Black Hills Information Security" and "Derek Banks". Google limits the results to 10 per page. You can click on additional pages of results to get more employee names written to the file.

![Google](https://github.com/AchocolatechipPancake/LinkedIn-Burp-PythonPlugin/blob/main/images/google.png)

You can gather a large list of employee names quickly and easily with this method. Try importing the list to Microsoft Excel where you can use formulas to turn employee names into the appropriate username format such as first initial followed by last name. It is also a good idea to use the "Remove Duplicates" functionality in Excel since the script may export the same employee name multiple times.

## Step 6
When you are done, unload the Python Scripter or erase the script code so you don't burden Burp with inspecting all responses.

# Covid-19 Data Explorer
App is live at: 
<a href="https://www.covid19dataexplorer.com/?raw=true" target="_blank">covid19dataexplorer.com</a>

# About
Covid-19 Data Explorer -app allows user to compare and explore different corona statistics from over 200 countries.
This python based project was created with Streamlit’s open-source app framework.
Using Alrair library for building interactive charts that are displayd with Vega-Lite. Data is **updated daily**.

# Statistics
**These statistics includes:**
* Total confirmed cases
* Total deaths
* Total cases per million  
* Total deaths per million
* New confirmed cases
* New deaths

## Using:
* python3
* streamlit, altair, pandas
* data.world's REST API
* Travis CI
* selenium

# Running with Docker
You can run this app with Dockerfile   

Build the container:  
```docker build -t st-app .```  

And run it:  
```docker run -p 8501:8501 --name st-app -it --rm st-app```  

Container is now available on:  
```http://<your docker-machine ip>:8501/```  

# Testautomation  
I have automated UI tests using Selenium library and Travis CI.  

Travis-CI is a continuous integration tool that will run tests for a GitHub repository every time commits are pushed.  
I'm running tests with both Firefox and Chrome in the headless mode, which is suitable for driving browser-based tests using Selenium and other tools.  

After tests are executed I can check my Travis CI build status page to see if my build passes or fails according to the return status of the build command.
You can also get the status by e-mail after execution.  

Data is originally sourced from: 
<a href="https://ourworldindata.org/coronavirus-source-data?raw=true" target="_blank">ourworldindata.org</a>
  
More information about this dataset: 
<a href="https://github.com/owid/covid-19-data/tree/master/public/data?raw=true" target="_blank">github.com/owid/covid-19-data</a>

For more details view my 
<a href="https://github.com/kurval/COVID-19-Data-Explorer?raw=true" target="_blank">GitHub</a>

<p>
<a href="https://kurval.github.io/" title="frontpage" class="text-decoration-none">
<svg width="2em" height="2em" viewBox="0 0 16 16" class="bi bi-arrow-left-circle-fill" fill="black" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-4.5.5a.5.5 0 0 0 0-1H5.707l2.147-2.146a.5.5 0 1 0-.708-.708l-3 3a.5.5 0 0 0 0 .708l3 3a.5.5 0 0 0 .708-.708L5.707 8.5H11.5z"/>
</svg>
<br>Go back to home page
</a>
</p>

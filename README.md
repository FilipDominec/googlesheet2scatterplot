= XY plot of a Google sheet =

== What this is good for == 

Scatter plots, where individual points are placed into a two-coordinate plane, is one most common plotting styles in science and not only there. In real life, datasets are often not limited to two parameters (i.e. X and Y coordinate), so it is useful when one can easily switch which point parameters would be represented by the X and Y axes. Additionally, the point colour is encoded by a third choice. This allows to search for possible correlations between different point parameters can be searched for. 

Even more useful is to put the whole project online, so that many people can cooperate. And most of the work has already been done! Numerous libraries (e.g. Plotly in javascript) enable one to put interactive scatter plots into a website. Several websites allow one to store data for individual plots  (e. g. Google Spreadsheets). So this project offers nothing but a simple HTML+JavaScript page that works as a glue between the CSV data (exported from your Google Spreadsheet), and Plotly (that makes a nice graph).

Note this gives you just a javascript page; all data are stored in your own Google spreadsheet, all plotting is done in your browser. You may open the index.html locally, or put it on your website for easier access online. In any case, such a page can be used for as many data tables as you wish. 

== Additional features == 

1. **Parameter grouping:** The first row of the table is 
1. **Point color as a third axis:**
1. **Point relations**
1. **Filtering of data**
1. **Plot settings stored in the address bar**

== Installation and requirements of the script == 

Simply get the files and put them somewhere accessible to your browser. Then open ```index.html``` with a proper pointer to the exported CSV table, like the example: https://docs.google.com/spreadsheets/d/1K4z2Up7PbC__3yXLqWTkNsnOSVtqYm4u6FtFCVmyTXw

== Making your own table & plots == 

You will probably want to make a copy of the example table and fill it with your data.  See ```howto.html``` for a step-by-step guide.


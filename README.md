# vzkt-xy

## Motivation and use

Scatter plots, where individual points are placed into a two-coordinate plane, is one most common plotting styles in science. In real life, datasets are often not limited to two parameters (i.e. X and Y coordinate), and different (non)correlations are revealed depending on which two parameters are be represented by the X and Y axes. Office table processors can do this; but it is useful to switch the settings by a single click.

Even more useful is to put the whole project online, so that many people can edit and view the data. And most of the work has already been done! Numerous libraries (e.g. Plotly in javascript) enable one to put interactive scatter plots into a website. Several websites allow one to store data for individual plots  (e. g. Google Spreadsheets). So this project offers nothing but a simple HTML+JavaScript page that works as a glue between the CSV data (exported from your Google Spreadsheet), and Plotly (that makes a nice graph).

Note this gives you just a javascript page; all data are stored in your own Google spreadsheet, all plotting is done in your browser. You may open the index.html locally, or put it on your website for easier access online. Therefore, one HTML page running anywhere can be used for as many data tables as you wish. 

----

## Example use for comparing the chemical elements

To demonstrate how this project works, we provide 
1. a dataset containing basic information on chemical elements. You can view it at the [google sheets here](https://docs.google.com/spreadsheets/d/1K4z2Up7PbC__3yXLqWTkNsnOSVtqYm4u6FtFCVmyTXw/edit?gid=0#gid=0). Of course you can make your own copy to add some new columns or new elements.
2. An externally hosted website running this project and pointing to this table: [vzkt-xy online](https://www.fzu.cz/~dominecf/xy/?x=group&y=period&c=electronegativity&fo1=(NOT%20USED)&fop=and&fo2=(NOT%20USED)&googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o)

Using the latter link, we can then view the elements in the shape of the classical periodic table:

![alt text](https://private-user-images.githubusercontent.com/511950/423478270-de83624a-96ea-4c0c-8185-174e7c586796.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDIyMTYxODAsIm5iZiI6MTc0MjIxNTg4MCwicGF0aCI6Ii81MTE5NTAvNDIzNDc4MjcwLWRlODM2MjRhLTk2ZWEtNGMwYy04MTg1LTE3NGU3YzU4Njc5Ni5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzE3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMxN1QxMjUxMjBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mY2NhNDJlNWEzNTczY2I4NjM4MWQyYjQ0YzYzMDU4YzdkYTU2YmMxZWQ2YWZlNDIxMzM3ZjFkOTNkYWQyZDAzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.I0AMiSLapyXyLWdl-zjkfKFLFNuyJCvh6-ObG7x1fx8)

And with different choices for the vertical and horizontal axes, as well as coloring, interesting correlations can be found:

![alt text](https://private-user-images.githubusercontent.com/511950/423478271-4abc2a51-97c3-4082-84a4-6345c750d57e.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDIyMTYxODAsIm5iZiI6MTc0MjIxNTg4MCwicGF0aCI6Ii81MTE5NTAvNDIzNDc4MjcxLTRhYmMyYTUxLTk3YzMtNDA4Mi04NGE0LTYzNDVjNzUwZDU3ZS5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzE3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMxN1QxMjUxMjBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT05ZTAxODU4YjRiYTg5ODhiOGViNmM1MDdkYzQ1ZDJjNDE5Mzg1ZTE0NDVjMzkzYjBiMzkzZjA0NDRkN2Q3NWUzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.z_xgQfnTHFETznxjQ1D8fkmiBx8_XL6S81PC2ysg72g)

Cloning & editing the Google sheets table you can fill it with your own column names, row names and data values. Now using the [procedure described here](https://www.fzu.cz/~dominecf/xy/howto.html) the address bar for the plotting website can be generated that points the HTML website to the exported CSV data from Google sheets.


----

## Additional features of the plotting HTML page

1. **Parameter grouping:** The first row of the table denotes the parameter group. Useful when there are over 20 parameters per point.
1. **Point color as a third axis:** Rainbow scale can show  hidden higher-order correlation between points.
1. **Point relations:** Every point may refer to another point as its parent, since samples in our laboratory are developed step by step, forming a large inheritance trees. The relations are displayed as arrows, optionally along with description of the relation. 
1. **Filtering of data:** A simple filter can be applied to show only a subset of points.
1. **Settings reflected in the address bar:** Copy the address bar to share your current axes/colours view.


----

## Running the script

The web page can be found at **https://www.fzu.cz/~dominecf/xy/?googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o&x=length&y=weight&c=maze%20solving**

The parameters provided after **?googleid=...** point to an example table. To plot useful data, make a copy of the underlying example table **https://docs.google.com/spreadsheets/d/1K4z2Up7PbC__3yXLqWTkNsnOSVtqYm4u6FtFCVmyTXw/edit#gid=0** and fill it according to your needs.  See **https://www.fzu.cz/~dominecf/xy/howto.html** for a step-by-step guide.

If you wish to be independent of my website, simply get the files and put them somewhere accessible to your browser - the plotting web page should work also locally. Then open ```index.html``` with a proper pointer to the exported CSV table in the address. You don't need to edit the sources if you just fill in your data; but contributions to this project are welcome. 


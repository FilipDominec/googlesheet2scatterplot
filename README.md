# gsheet2scatterplot - Motivation and use

Among the most common graph types used in science are *scatter plots*, where individual points are placed into a two-coordinate plane. This project extracts data from a Google Sheet and displays them interactively on the screen as an interactive web page.  

While any decent spreadsheet processor can generate a scatter plot, there are good reasons to use a HTML/JavaScript page for it. The purpose of this project is to make viewing the datasets interactive, collaborative and to add several features that are useful for laboratory sample management:
* **Interactivity**: One mouse click in the right menu changes the quantity determining the X,Y position of the points, or their colour.
* **Collaboration**: When you add or change data in your google sheet, all your colleagues only have to refresh the page to see the changes. 
* **Special features**: There are several features that further simplify the analysis, as described at the end of this page.


----
# Example use for comparing the chemical elements

To demonstrate how this project works, we provide 
1. a dataset containing basic information on chemical elements. You can view it at the [google sheets here](https://docs.google.com/spreadsheets/d/1K4z2Up7PbC__3yXLqWTkNsnOSVtqYm4u6FtFCVmyTXw/edit?gid=0#gid=0). Of course you can make your own copy to add some new columns or new elements.
2. A running main webpage from this project, which has to be opened with the hash enabling it to load the data from the table (see links below). 


Having assigned the period and group number in the periodic table to each element, the graph can arrange them to form an inverted periodic table as we know it.  
![elements by row and column in the periodic table](./docs/example_elements.png)
<a href="https://filipdominec.github.io/googlesheet2scatterplot/?x=group&y=period&c=period&fo1=(NOT%20USED)&fop=and&fo2=(NOT%20USED)&googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o">https://filipdominec.github.io/googlesheet2scatterplot/?x=group&y=period&c=period&fo1=(NOT%20USED)&fop=and&fo2=(NOT%20USED)&googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o</a>

Depending on the data filled in the table, many interesting correlations can be interactively examined.
For example, by two mouse clicks we can rearrange the elements to show how their boiling points are related to their melting points. We have also switched the X,Y axes to logarithmic scale. This nicely shows that monoatomic noble gases have their boiling/melting temperatures very close, lying on the graph diagonal (automatically added dashed line). For most elements the ratio about 1.5-1.8 %, whereas for alkaline metals and similar ones (Hg, Bi, Pb) form a line at about 300 %. There are some outliers like sublimating arsenic, or biatomic covalently bound liquid metal Gallium.  There is a lot of interesting physics to discuss (which is beyond the scope of this website).

![elements by boiling and melting point](./docs/example_elements_by_boiling_melting.png)
<a href="https://filipdominec.github.io/googlesheet2scatterplot/?x=melting%20point&y=boiling%20point&c=period&xlog=1&ylog=1&fo1=(NOT%20USED)&fop=and&fo2=(NOT%20USED)&googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o">https://filipdominec.github.io/googlesheet2scatterplot/?x=melting%20point&y=boiling%20point&c=period&xlog=1&ylog=1&fo1=(NOT%20USED)&fop=and&fo2=(NOT%20USED)&googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o</a>

It is similarly easy to show how thermal capacity per gram is almost inversely proportional to the atomic Z number. However, even here we can see some outliers, which is obviously related to the element's melting point (coded by colour).

![example of thermal capacities by atomic weight, for solids only](./docs/example_elements_thcap_by_Z.png)
<a href="https://filipdominec.github.io/googlesheet2scatterplot/?x=atomic%20weight&y=thermal%20capacity&c=melting%20point&xlog=1&ylog=1&fb1=boiling%20point&fo1=gt&fp1=400&fop=and&fo2=(NOT%20USED)&googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o">https://filipdominec.github.io/googlesheet2scatterplot/?x=atomic%20weight&y=thermal%20capacity&c=melting%20point&xlog=1&ylog=1&fb1=boiling%20point&fo1=gt&fp1=400&fop=and&fo2=(NOT%20USED)&googleid=2PACX-1vRZbVmg68lEl8VS9DGa1rEDS5-V55Ome6JXc6Cs4UuGhAYUgHHZw1x1_f9AbvHlyDL8GmzRVxli0W-o</a>

Cloning & editing the Google sheets table you can fill it with your own column names, row names and data values. Then, using the [procedure described here](https://www.fzu.cz/~dominecf/xy/howto.html) the address bar for the plotting website can be generated that points the HTML website to the exported CSV data from Google sheets.


----

# Additional features of the plotting HTML page

1. **Point color as a third axis:** Rainbow scale can show hidden higher-order correlations between points.
1. **Point relations:** Every point may refer to another point as its parent, since samples in laboratories are typically developed step by step, forming a large inheritance tree. The relations are displayed as arrows, optionally along with a description of each relation. 
1. **Filtering of data:** A simple filter can be applied to show only a subset of points. Two filtering rules are available and can be combined with logical "and"/"or" operand.
1. **Settings are immediately reflected in the address bar:** Copy the address bar to share your current axes/colours settings with anybody whom you send this link.
1. **Visual parameter grouping:** The first row of the table denotes the parameter group, which can be folded. This saves screen space when there are over 20-30 parameters per point.
1. **Visual parameter highliting:** If you want to point out a new or otherwise interesting parameter (or group), just put an asterisk behind its name. It will be highlighted green.


----

# Trying the script online

Note this project gives you just a javascript page; all data are stored in your own Google spreadsheet, all plotting is done in your browser. You may open the index.html locally, or put it on your website for easier access online. Therefore, one HTML page running anywhere can be used for as many data tables as you wish. 
Pulling data from your google sheet as specified by your own ```googleid=``` parameter makes the website also safe even for confidential projects.

To make plot your own data, make a copy of the underlying example table **https://docs.google.com/spreadsheets/d/1K4z2Up7PbC__3yXLqWTkNsnOSVtqYm4u6FtFCVmyTXw/edit#gid=0** and fill it according to your needs.  See **https://www.fzu.cz/~dominecf/** for a step-by-step guide how to generate a corresponding ```googleid=``` parameter.

If you wish to be independent of the website, e.g., for Javascript development, simply clone this project's files and put them somewhere accessible to your browser - the plotting web page should work even locally. You don't need to edit the sources if you just fill in your data; but contributions to this project are welcome. 


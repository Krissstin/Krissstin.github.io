---
name: IS 445 Homework 5
tools: [Python, HTML, vega-lite, Altair]
image: assets/pngs/plot_2.png
description: Two visualizations using the `building_inventory.csv` dataset.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Plot 1: Building Size vs Construction Year

This scatter plot shows the relationship between when buildings were built and how big they are in square footage. Each dot represents a building. The X-axis shows the construction year, and the Y-axis shows the building’s size. I used color to show the building’s usage type, which can help us see if certain types of buildings tend to be bigger or built more recently.

<vegachart schema-url="{{ site.baseurl }}/assets/json/plot_2.json" style="width: 100%"></vegachart>

To clean the data, I removed any rows with missing or clearly incorrect years (like 0 or 200) and filtered out buildings with missing square footage. I used the `.dropna()` function and set limits on the year to keep the data realistic.




# Plot 2: Number of Buildings by Usage Description (with dropdown interaction)

This bar chart shows how many buildings fall under each usage category, such as Storage, Industrial, or Health Care. I used a horizontal bar chart to make the labels easier to read. The X-axis shows the number of buildings, and the Y-axis shows the usage types. Color is used to represent each usage type so users can easily compare categories.

<vegachart schema-url="{{ site.baseurl }}/assets/json/interactive_plot_1.json" style="width: 100%"></vegachart>

To make it interactive, I added a dropdown menu that lets users select a specific usage type. When user picks a type, the chart filters and highlights only that one, which makes it easier to focus on one category at a time and helps reduce visual clutter when there are too many bars. The data was grouped using `value_counts()` to get the total number of buildings per category.





<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/Krissstin/Krissstin.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>


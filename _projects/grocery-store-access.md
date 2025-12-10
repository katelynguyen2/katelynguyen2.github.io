---
name: Grocery Store Access in Chicago
tools: [Python, Altair, vega-lite]
description: An interactive project exploring where Chicago grocery stores are open, closed or online only.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Grocery Store Access in Chicago  
By Katelyn Nguyen

A look at where stores are open, closed, or take online orders only

## Dataset Context  
This project uses the Chicago Grocery Store Status dataset. It lists grocery stores in Chicago and labels each store as OPEN, CLOSED, ONLINE ONLY. The dataset also includes the store’s address, ZIP code, and its location on a map.

Even though the dataset is simple, it gives a meaningful snapshot of food accessibility in Chicago. Grocery stores play a major role in daily life, people rely on them for fresh produce, basic supplies, and affordable meal options. By showing where stores remain open, where closures are happening, and where online only services are becoming more common, the dataset helps us see patterns that aren’t easy to notice in everyday life.


## Project Goal  
This project explores how grocery store availability differs across Chicago ZIP codes.  
I focus on questions like:

- Which ZIP codes have the most open stores?  
- Which areas have many closures?  

The goal is to make these patterns easy to see.


## Dashboard Preview (GIF)

<img src="{{ '/assets/pngs/grocery_dashboard_demo.gif' | relative_url }}" 
     alt="Grocery dashboard preview"
     style="max-width: 400px; width: 100%; height: auto; border-radius: 8px;"/>

*Animated GIF showing how the status dropdown changes the bars in the chart.*


## Main Interactive Visualization  
### Stores per ZIP Code, Filtered by Status

Use the dropdown menu in the chart below to choose a store status (**OPEN**, **CLOSED**, **ONLINE ONLY**, etc.).  
The chart will update to show how many stores in each ZIP code match that status.

<vegachart schema-url="{{ site.baseurl }}/assets/json/grocery_top_zip_by_status.json" style="width: 100%"></vegachart>

### How to Read This Chart  
- Each bar represents one ZIP code.  
- The height of the bar shows **how many stores in that ZIP code** have the selected status.

This makes it easy to see:

- ZIP codes with **many open stores**  
- Areas with **high numbers of closures**  
- ZIP codes with **few or no stores**  
- Where **online-only** stores appear

Instead of searching through a long table of addresses, you can view neighborhood differences instantly.


# Contextual Visualization  
### Overall Breakdown of Store Statuses

Here is a simple count of how many stores fall into each status category:

<img src="{{ '/assets/pngs/store_status_hist.png' | relative_url }}"
     alt="Bar chart of overall store statuses"
     style="width: 400px; height: auto; display: block;">

*Figure 1. Number of stores in each status category.*

This chart helps give perspective. Even if some ZIP codes show many closures, **most stores in the dataset are still open**. Looking at the totals helps avoid misinterpreting the interactive chart.



# How to Explore the Results

If you are new to data or new to Chicago, you can read the visuals in this order:

1. **Start with the interactive bar chart.**  
   Pick a status and look for ZIP codes with tall bars or no bars.

2. **Use the summary chart above.**  
   It shows how common each store status is overall.

3. **Think about neighborhood access.**  
   - ZIP codes with many open stores likely have strong access.  
   - ZIP codes with few stores may have limited access.

These charts are designed to be easy to understand



# Limitations and Next Steps  

A few things the dataset does not include:

- Population or income information
- Store size or type
- Updated status over time (A store marked CLOSED may reopen later)

Future work could consider population counts, income data, or transportation options to better understand food access gaps across Chicago.



# Turning Data Into Design: Why This Dataset Stood Out
One reason I was drawn to this dataset is that I am also interested in user experience (UX) design, and I kept imagining how this information could support a real app that helps people shop more easily. For example, an app could let users create a grocery list and then suggest the closest open store that carries most of the items they need. If a store is closed or temporarily unavailable, the app could automatically reroute the user to another nearby option. It could also show which neighborhoods have limited choices, helping users understand why certain trips take longer or require more planning. Thinking about how this data could be turned into something helpful for everyday life from choosing a store to reducing travel time made the analysis feel more meaningful and connected to real problems people face in cities.



# Citations 

City of Chicago. (n.d.). Grocery Store Status Map — Historical. Chicago Data Portal. https://data.cityofchicago.org/Health-Human-Services/Grocery-Store-Status-Map-Historical/rish-pa6g



# Analysis Notebook  

You can view the full notebook used to clean the data and create the visualization here:

[Final Project Analysis Notebook]({{ '/python_notebooks/final_project_part3_1.ipynb' | relative_url }})


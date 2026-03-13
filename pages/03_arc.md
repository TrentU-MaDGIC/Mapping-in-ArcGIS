---
layout: default
title: Creating a project
nav_order: 4
---

# Creating a Project

Beign by opening ArcGIS and clicking **Map**. Name it whatever you'd like and click **OK**

![Arc 1](../assets/images/arc_1.png)
![Arc 2](../assets/images/arc_2.png)

# Importing Data
The first thing we have to do is bring in our census data and our boundary file. Let's start with our census data. *Click* **Add Data** and navigate to your unzipped census data. Click the .csv file and *click* **OK**. Now our census data is in ArcGIS!
![Arc 3](../assets/images/arc_3.png)
Let's do the same thing for the boundary file. Once again, *click* **Add Data** and navigate to your unzipped boundary data. This time, *click* the .shp file and *click* **OK**.
![Arc 4](../assets/images/arc_4.png)

# Transforming Data
Now that our data is in, before we get to filter the points we want, we have to transform our data. To use one of the tools we need, our data requires OIDs (Object IDs). We can get these by transforming our data into a geodatabase. On the right side in the **Catalog** pane *click* the **Databases** drop down. Then *right-click* the .qdb. *Hover* over **Import** and *click* **Table(s)**. This will open the **Geoprocessing** pane.
![Arc 5](../assets/images/arc_5.png)
In the **Geoprocessing** pane, *click* the drop down under **Input Table** and select the .csv file. Then *click* **Run**. 
![Arc 6](../assets/images/arc_6.png)
Return to the **Catalog** pane and you should see a new file with the extension_csv. We want to bring this to our **Contents** pane. To do this, *click and drag* the _csv file to the left side **Contents** pane. 
![Arc 7](../assets/images/arc_7.png)
Now you can *right-click* on the _csv in the contents pane and *click* Open. This will show you all of the data including our new row of OIDs.
![Arc 8](../assets/images/arc_8.png)

# Filtering Data
We are now going to filter by year and by total field of study. These columns are **REF_DATE** and **Field of Study**. We will be looking at 5 years in ~5 year increments (2006/2007, 2011/2012, 2016/2017, 2021/2022, 2025/2026). We will also be looking at the average of all fields which is *Total, field of study*. In order to filter our data set, with it selected in the contents pane, *click* **Select By Attributes**. For **Input Rows**, select the _csv file. We will then create two expressions. One where the **REF_DATE** is equal to 2006/2007, and another where the **Field of Study** is equal to *Total, field of study*. With both clauses added, **click* **OK**. 
![Arc 9](../assets/images/arc_9.png)

This has now selected all rows where the year is 2006/2007 and the field is total. This should select one row per province/territory. With those now selected, *right-click* the _csv, *hover* over **Data**, and *click* **Export Table**. Change the output table name to something desriptive like: *Table_2006_2007* (Note: This cannot start with a number). *Click* **OK**. This has created a new table which you can inspect.

![Arc 10](../assets/images/arc_10.png)

Now repeat this process for the other 4 years begining with **Select By Attributes**.

## Housekeeping
Before we start mapping let's clean up a little bit. *Click* once on the boundary file lpr_000b21a_e. This will allow you to change the name. Let's change it to *Provincial University Tuition*. Additionally, we will begin by mapping 2006/2007 so following the same procedure, rename Map to 2006/2007.

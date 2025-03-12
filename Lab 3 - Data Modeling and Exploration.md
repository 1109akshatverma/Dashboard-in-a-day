# Lab 3 - Data Modeling and Exploration

### Estimated Duration: 40 Minutes

## Overview

This lab provides step-by-step instructions for users to follow, accompanied by screenshots that serve as visual aids. Key sections in the screenshots are highlighted with red or orange boxes to direct the user's attention to essential areas. These highlights help users quickly identify the relevant interface elements, ensuring a smooth and guided learning experience.

## Lab Objectives

- Task 1 - Power BI Desktop - Layout (READ-ONLY)
- Task 2 - Power BI Desktop – Data Exploration 

### Task 1 - Power BI Desktop - Layout (READ-ONLY)

1. On the top of the window, you see the **Home** tab where the most common operations you perform are available.

2. The **Insert** tab in the ribbon allows you to insert shapes, a text box or new visuals.

3. The **Modeling** tab in the ribbon enables additional data modelling capabilities like adding custom columns and calculating measures. 

4. The **View** tab has options to format the page layout. 

5. The **Help** tab provides self-help options like guided learning, training videos and links to online communities, partner showcase and consulting services.

6. On the left side of the window, you have three icons, **Report**, **Data** and **Model**. If you hover over the icons, you can see the tooltips. Switching between these allows you to see the data and the relationships between the tables.

7. The center **white space** is the canvas where you will be creating visuals.

8. The **Visualizations** panel on the right allows you to select visualizations, add values to the visuals,and add columns to the axis or filters.

9. The **Data** window on the right panel is where you see the list of tables which were generated from the queries. Click the :arrow_down_small: icon (downward facing triangle) next to a table name to expand the field list for that table.

   ![](Images/powerbi-02-02.png)

10. Click on the **Data** icon on the left side. Expand the **Sales** table in the **Data** pane as shown in the image. Scroll up and down to notice how fast you can navigate through over three million rows.

    ![](Images/powerbi-02-03.png)
    
11. Click on the **Model** icon on the left panel of Power BI Desktop. You see the tables you have imported along with Relationships. The Power BI Desktop automatically infers relationships between the tables. 
  - A relationship is created between the Sales and Product tables using the **ProductID** column.
  - A relationship is created between the Product and Manufacturer tables using the **ManufacturerID** column.

    ![](Images/powerbi-02-04.png)
    
### Task 2 - Power BI Desktop – Data Exploration 

1. Click on the **Report (1)** icon on the left panel. Select the **Clustered column chart (2)** visual in **Visualizations** as shown in the screenshot.

    ![](Images/powerbi-02-08.png)
    
1. From the **Data** section, expand the **Geography** table and then click the checkbox next to the **Country** field.

1. From the **Data** section, expand the **Sales** table and then click the checkbox next to the **Revenue** field.

1. **Resize** the visual as needed by dragging the edges.

1. Click on the **Model** icon on the left panel to navigate to the Relationship view.

1. Our sales data is by **Zip** code, so we need to connect the Zip column from the **Sales** table with **Zip** column in the **Geography** table. You can do this by dragging the **Zip** field in the **Sales** table to connect the line with the **Zip** field in the **Geography** table.

    ![](Images/powerbi-02-10.png)

1. Click on **Cancel** in the **Create relationship** dialog box.

1. Click on the **Report** icon on the left panel to navigate to the **Report** view.

1. In the **Data** section, click on the ellipse next to the **Sales** table. Click on **New Column** as shown. You will see a formula bar appear, as shown in the screenshot, to help create this new column.

    ![](Images/powerbi-02-11.png)
    
1. Now we are ready to combine the Zip and Country columns into a new column called **ZipCountry**, separated by a comma. To create this column called ZipCountry, type the following calculation in the editor.
         
    ```bash
    ZipCountry = Sales[Zip] & "," & Sales[Country]
    ```

    ![](Images/powerbi-02-12.png)

1. Once you are done entering the formula, press `Enter`. 

1. From the Data section, click the **Geography** table, from the ribbon click **Modeling**, and then click **New Column** as shown in the figure.

    ![](Images/powerbi-02-14.png)

1. A formula bar now appears. Enter the following DAX expression in the formula bar: 

    ```bash
    ZipCountry = Geography[Zip] & "," & Geography[Country]
    ```
          
    ![](Images/powerbi-02-15.png)

1. Click on the **Model** icon on the left panel to navigate to the **Relationship** view.

1. Drag the **ZipCountry** field from the **Sales** table and connect it to the **ZipCountry** field in the **Geography** table.

    ![](Images/powerbi-02-16.png)

1. Click on **Save** in the **Create relationship** dialog box.
    
1. Click on the **Report** icon on the left panel to navigate to the **Report** view.

1. Click on the **ellipse** on the top right corner of the visual (alternatively, the ellipse may be at the bottom of the chart). Notice there is an option to Sort axis by **Country** as well.

    ![](Images/sort-by-revenue.png)

1. Notice that we have some blanks in our data. We want to clean up our data and get rid of the blanks

1. Drag the **Country** field from the **Geography** table to the Filters pane and drop it in **Filters on all pages**

1. Change filter type to **Advanced filtering** and select **is not blank**, click on **Apply Filter**
 
 >**NOTE**: Additional filter options are available: is blank, is empty, is not empty

   ![](Images/powerbi-02-18.png)

1. Click on the **Model** icon.

1. Drag the **ProductID** field in the **Product** table to connect the line with the **ProductID** field in the **Sales** table.

1. Drag the **ManufacturerID** field in the **Manufacturer** table to connect the line with the **ManufacturerID** field in the **Manufacturer** table.

1. From the **Data** section, expand the **Manufacturer** table, and then drag the **Manufacturer** column to the **Legend** section under Visualizations.

35. While you have your chart selected, click the **Clustered column chart** from the **Visualizations** section, and then click the **Stacked column chart** visual.

36. **Resize** the visual as needed.

    ![](Images/powerbi-02-19.png)

Now we can see the top manufacturers by country. 

Now let’s try different visuals to see which chart represents the data the best.

37. Begin with the **Stacked column chart** selected.

    ![](Images/powerbi-02-20.png)

38. Sort the legend in descending order

    ![](Images/powerbi-02-21.png)
    
39. In the **Filters** pane, expand **Manufacturer**.

40. From the **Filter Type** dropdown menu, click **Top N**.

41. Enter **5** in the text box next to **Top**.

42. From the **Sales** table, drag and drop the **Revenue** field into the **By value** section.

43. Click on **Apply filter**.

    ![](Images/powerbi-02-22.png)

Notice that the visual is filtered to display the top five manufacturers by Revenue. We see that the manufacturer VanArsdel has a higher percentage of sales in USA compared to other countries or regions.

We can now add total labels to the stacked visuals

44. Lets explore font formatting options

45. Click on the **paint roller icon** and click on **X axis**

46. Turn on **Bold** and **Italic** – feel free to try different formatting option on different areas. For the purpsoe of the lab we will turn off Bold and Italic

    ![](Images/powerbi-02-23.png)

47. Navigate to the **Total labels** heading and click to **On**

    ![](Images/powerbi-02-24.png)
    
Let’s remove the total labels

48. Click Total labels to the **Off** position

We are interested in the top five competitors by revenue. Let’s group them so we don’t have to add a filter to every visual. Before we do that, we’ll remove the **Top 5** visual level filter.

49. Begin with **Stacked column chart** selected.

50. Hover over and click the **Clear filter** icon (erase) next to **Manufacturer** field in the **Filters** Pane.

    ![](Images/powerbi-02-25.png)

51. From the **Data** section, right-click on the **Manufacturer** field name from **Manufacturer** table.

>**Note**: do not check the checkbox.

52. Click **New Group**.

53. In the **Ungrouped values** section, using **Ctrl** key, click **Aliqui**, **Currus**, **Natura**, and **Pirum**.

54. Click the **Group** button. Notice a new group is added in the **Groups and members** section.

55. Double-click the newly created group and rename it **Top Competitors**.

56. Click **VanArsdel** from the **Ungrouped values** section and click the **Group** button to create the **VanArsdel** group.

57. Click the checkbox **Include Other group**. This will create another **Other** group that includes all the other manufacturers.

58. Click **OK** to close the **Groups** dialog.

    ![](Images/powerbi-02-26.png)
    
59. With the **Stacked column chart** selected, click on the **X** next to **Manufacturer** in the **Legend** section. This will remove the Manufacturer.

60. From the **Data** section, drag the newly created **Manufacturer (groups)** to the **Legend** section.Now we can see that VanArsdel has nearly 50% share in USA.

    ![](Images/powerbi-02-27.png)

61. Hover over one of the columns and right-click.

62. Click **Show as a table**. You will now be in **Focus** mode with the chart displayed on top and the data displayed below. Notice that VanArsdel has a large percent of the USA market.

63. Use the icon in the top right corner to switch to the vertical layout. In this layout, you view the chart on the left panel and the data on the right panel.

64. Click **Back to Report** to go back to the **Report** canvas.

    ![](Images/powerbi-02-28.png)

 >**Note**: You can use similar steps to Show data point as a table to see records for a specific data point.

Now let’s create a Revenue by Manufacturer visual.

65. Click on the white space in the canvas. From the **Data** section, click the checkbox next to the **Revenue** field in the **Sales** table.

66. From the **Data** section, click the checkbox next to the **Manufacturer** field in the **Manufacturer** table.

67. From the **Visualizations** section, click the **Treemap** visual.

    ![](Images/powerbi-02-29.png)
    
We now have Revenue by Manufacturer. Now let’s turn our attention to the interaction between the Stacked column chart and the Treemap visuals.

68. In the **Treemap**, click **VanArsdel** and notice that the Stacked column chart is filtered. This confirms that VanArsdel has a large percentage of the USA market.

    ![](Images/powerbi-02-30.png)
    
69. To remove the filter, click **VanArsdel** again.

This interaction between visuals is called cross-filtering.

Previously, we added a Top 5 Visual level filter. Now let’s add a filter to the Page level, so we are working with the Top Competitors and VanArsdel and filter out the other manufacturers.

Page-level filters apply to all visuals on the page. Visual-level filters apply only to a visual. Ensure the Filters pane is expanded/open.

70. From the **Data** section, drag **Manufacturer (groups)** from the **Manufacturer** table to the **Filters on this page** box in the **Filters Pane**.

71. Click **Top Competitors** and **VanArsdel**.

    ![](Images/powerbi-02-31.png)

Now, let’s add a visual that provides sales information over time

72. Begin by clicking on the white space in the canvas and select **Clusterd column chart** from Visualizations.

73. Click the checkbox next to the **Date** field in the **Sales** table. Notice that a Date Hierarchy is created. 

74. Click the checkbox next to the **Revenue** in the **Sales** table field. Notice that a Clustered column chart is created. Also notice in the **Axis** section, a date hierarchy is created. There are arrows on the top bar of the chart which are used to navigate through the hierarchy.

    ![](Images/powerbi-02-32.png)

75. Click on the **USA** column in the **Revenue by Country** visual.

76. With the **Revenue by Country** visual selected, from the ribbon click on **Format**, and then click **Edit Interactions**. Notice on the top right of the other two visuals new icons with the highlight icon selected.

77. Click the **filter icon** for both visuals.

    ![](Images/powerbi-02-33.png)
    
Notice now in both Revenue by Year and Revenue by Manufacturer, data is filtered for USA.

78. Now click the **Revenue by Year** visual.

79. Next, click the **filter** icon on the other two visuals.

    ![](Images/powerbi-02-34.png)

80. Similarly, click on the **Revenue by Manufacturer** visual and click the **filter icon** on the other **two visuals**. Once you are done, all the visuals should be in filter mode.

81. With the **Revenue by Manufacturer** visual selected, from the ribbon click **Format** then **Edit Interactions** to remove the icons.

82. Click on VanArsdel in the Revenue by Manufaturer visual

>**Note**: If your screen doesn’t look like the one below please edit your interactions.

   ![](Images/powerbi-02-35.png)

We have already noticed that VanArsdel has a large share of the market in Australia. Let’s see how VanArsdel has done over time in Australia.

83. Click on the **Revenue by Country and Manufacturer (groups)** chart and remove **Manufacturer (groups)** from the legend.

84. Click on **VanArsdel** in the **Revenue by Manufacturer** visual.

85. **Ctrl+Click** the **Australia column** in the **Revenue by Country** visual. 

Now we have filtered the charts by both VanArsdel and Australia. Looking at the results, we can see a spike in 2021 sales for VanArsdel in Australia. This spike in sales is intriguing, so let’s investigate further.

86. Click the down arrow on the top of the **Revenue by Year** visual. This enables drill-down capability.

    ![](Images/powerbi-02-36.png)
    
87. Click the **2024** column in the **Revenue by Year** visual.

Notice that you have drilled down to the quarter level of 2021. There was a big spike in the fourth quarter. Let’s dig further.

88. Click on the double arrow icon on the top of the **Revenue by Year** visual. This drills down to the next level of the hierarchy, which is the month.

    ![](Images/powerbi-02-37.png)

89. Click on the up-arrow icon on the top of the **Revenue by Year** visual to drill up to the **Quarter** level.

90. Click on the drill up icon again to go up to the **Year** level

91. Click on the split arrow icon on the top right of the **Revenue by Year** visual. This expands down to the next level of the hierarchy, which is quarters for all the years.

Notice that the fourth-quarter sales have always been high, but in 2021 there was a larger sales spike in the fourth quarter than usual.

92. Now let’s expand down to the month level. Click on the split arrow icon on the top right of the **Revenue by Year** visual. This expands down to the next level of the hierarchy, which is months for all the years.

There is a lot of information in the visual and we must scroll left and right to compare.

## Summary

In this lab, you have explored the various data in Power BI.

### You have successfully completed the lab!

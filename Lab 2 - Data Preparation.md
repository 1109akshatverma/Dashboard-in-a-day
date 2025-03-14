# Lab 2 - Data Preparation

### Estimated Duration: 30 Minutes

## Overview

In this lab, you will explore methods to transform data in the data model to ensure it is optimized for reporting. You will perform key transformations such as renaming tables, updating data types, and appending tables to clean and structure the data effectively. These transformations enhance data consistency, improve usability for end users, and streamline the report creation process in Power BI.

## Lab Objectives

- Task 1 - Power BI Desktop – Filling empty values
- Task 2 - Power BI Desktop – Splitting columns
- Task 3 - Power BI Desktop – Renaming columns
- Task 4 - Power BI Desktop – Removing unwanted rows
- Task 5 - Power BI Desktop – Transposing data
- Task 6 - Power BI Desktop – Appending queries

### Task 1 - Power BI Desktop – Filling empty values

1. On the Query Editor window, click each query name in the **Other Queries** section.
   
1. Navigate to **Query Settings**, and then from the **Properties** section in the right-hand pane ,rename the queries as shown below:

   | Initial Name             | Final Name            |
   | ------------------------ | --------------------- |
   | Product_Table            |  `Product`            |
   | geo                      | `Geography`           |
   | manufacturer             | `Manufacturer`        |
   | InternationalSales       | `International Sales` |

      ![](Images/did27.png)

1. From the left pane, click on the **Product (1)** query. Click on the **Category (2)** column. From the ribbon, click on the **Transform** tab , select **Fill (3)**, and then click on **Down (4)**.

      ![](Images/did28.png)

### Task 2 - Power BI Desktop – Splitting columns

In the Product query, notice the Product column. It looks like the product name and product segmentare concatenated into one field with a pipe (|) separator. Let’s split them into two columns. This will be useful when we build visuals, so we can analyze based on both fields.

1. Click on the **Product (1)** column. From the ribbon, click on the **Home** tab, select **Split Column (2)**, and then click **By Delimiter (3)**.

      ![](Images/did29.png)

      > **Note:** The Split **Column by Delimiter dialog** box opens.

1. In the dialog box, make sure that **Custom (1)** is selected in the **Select or enter delimiter** drop-down menu. Replace the hyphen symbol with **pipe symbol (|)** **(2)** as shown in the image. Click on **OK (3)**.

      ![](Images/did30.png)

### Task 3 - Power BI Desktop – Renaming columns

1. Click the **Product.1 (1)** column, and then **right-click** next to the column name and click on **Rename… (2)** from the selection menu.

      ![](Images/did31.png)

1. **Rename** the field to **Product**.

1. Also, rename **Product.2** to **Segment**.
        
### Task 4 - Power BI Desktop – Removing unwanted rows

In the **Geography** query, notice that the first two rows are informational. They are not part of the data. Similarly, in the Manufacturer query, the last couple of rows are not part of the data. Let’s remove them so we have a clean dataset.

1. From the left pane, click on the **Geography (1)** query. From the ribbon, click on the **Remove Rows (2)** dropdown and then select **Remove Top Rows (3)**.

      ![](Images/did32.png)

      >**Note**: The Remove Rows option can sometimes be found under the Reduce Rows option.

1. The **Remove Top Rows** dialog box opens. Enter **2** in the text box and click on **OK**.
    
      >**Note**: Notice the first row in the Geography query is now the column header. 

1. With **Geography** query selected in the left panel, from the ribbon click **Home**, and then select **Use First Row as Headers**.

      ![](Images/did33.png)

1. Click on **123 (1)** next to the Zip Column. From the dialog box, select **Text (2)**.

      ![](Images/did34.png)

1. Click on **Replace Current** in the **Change Column Type** dialog box.

1. From the left panel, click on the **Manufacturer (1)** query. From the ribbon, click on the **Home** tab, click on the **Remove Rows (2)** dropdown and then select **Remove Bottom Rows (3)**.
 
      ![](Images/did35.png)

      >**Note**: The Remove Rows option can sometimes be found under the Reduce Rows option.

1. The **Remove Bottom Rows** dialog box opens. Enter **3** in the **Number of rows text box** and click on **OK**.
   
### Task 5 - Power BI Desktop – Transposing data

1. Stay on the **Manufacturer (1)** query, click on the **Transform** tab and then select **Transpose (2)**.

      ![](Images/did36.png)

1. From the ribbon, click on the **Home** tab and select **Use First Row as Headers**.

      ![](Images/did37.png)

      > **Note:** Notice that now the **Manufacturer** table is laid out the way we need it with a header and values along columns.

### Task 6 - Power BI Desktop – Appending queries

To analyze the Sales of all countries, it is convenient to have a single **Sales** table. To do this, you need to append all the rows from the **International Sales** query to the **Sales** query.

1. Click on the **Sales (1)** query from the left pane. From the ribbon, click on the **Home** tab and then select **Append Queries (2)**. 

      ![](Images/did38.png)

1. In the Append dialog box, keep the default **Two Tables (1)** checked, select **International Sales** from the drop-down and then click on **OK (2)**.

      ![](Images/did39.png)
    
      > **Note:** You will now see a new column in the **Sales** table called **Country**. Since the International **Sales** query had the additional column for **Country**, Power BI Desktop added the column to the **Sales** table when it loaded the values from the **International Sales** query. 

1. Keep the **Sales (1)** query selected. From the ribbon, click on the **Add Column** tab and select **Conditional Column (2)**.

      ![](Images/did40.png)
    
1. In the **Add Conditional Column** dialog box, add the below values and click on **OK (8)**:

   - Enter the name of the column as **CountryName (1)**
   - Select the **Country (2)** from the **Column Name** drop-down menu
   - Select the **equals (3)** from the **Operator** drop-down menu
   - Enter **null (4)** in the **Value** box
   - Enter **USA (5)** in the **Output** box
   - Click on the drop-down menu under **Else** and then click the **Select a column (6)** option
   - Click on the **Country (7)** from the column drop-down menu

       ![](Images/did41.png)
     
1. You will see the **CountryName** column in the Query editor window.
   
1. Right-click on the **Country** column and click **Remove** as shown in the figure.
 
   ![](Images/did42.png)

1. Right-click on the **CountryName** column and rename it to **Country**.

1. From the **Home** tab, click on the **Data Type (1)** option, change the **data type** of the **Country** column to **Text (2)**.

   ![](Images/did43.png)

1. From the **Home** tab, click on the **Data Type** option, change the **data type** of the **Revenue** column to **Fixed Decimal Number** because it is a currency field.

1. On the Country column, click on the dropdown next to it and select **Load more** to validate you have data from all eight countries. 

   ![](Images/did44.png)

1. Click on **OK** to close this filter.

   ![](Images/did45.png)

1. Click on the **dropdown arrow** next to **Date** in the **Sales** Query.

1. Click on the **Date Filters** option and select **In the Previous…**.

   ![](Images/did46.png)
    
1. The **Filter Rows** dialog box opens. Enter **3 (1)** in the text box next to **is in the previous**. Click **years (2)** from the drop-down menu. Click on **OK (3)**.

      ![](Images/did47.png)

      > **Note:** Our dataset has data from 2022 to 2024. For our analysis we want to start with the last three years of data (2022-2024). We don’t yet know how many rows will result. We can filter by year to get the subset.
   
1. From the Queries panel on the left, click on the **International Sales** query. Right-click and select **Enable Load**. This will disable loading International Sales.

      ![](Images/did48.png)
    
     >**Note**: The appropriate data from the International Sales table will load into the Sales table each time the model is refreshed. By removing the International Sales table, we are preventing duplicate data from loading into the model and increasing its file size. In some instances, storing very large amounts 
of data affects the data model performance.
 
1. From the ribbon, click on the **View** tab and select **Query Dependencies**.

   > **Note:** This opens the **Query Dependencies** dialog box. The dialog box shows the source of each query and its dependencies. For example, we see that the Sales query has a CSV file source and a dependency on the International Sales query. This is a useful information to share knowledge with your team members.

1. **Close** the dialog box.

    > **Note:** You have now successfully completed import and data shaping operations and are ready to load the data into the Power BI Desktop data model to visualize the data. 

1. Click on **File** and then click on **Close & Apply**  option. This will close out the power query window and apply all changes.

      ![](Images/did49.png)
    
    > **Note:** All the data will be loaded in memory in the Power BI Desktop. You will see the progress dialog box with the number of rows being loaded in each table as shown in the Figure.
    
    ![](Images/powerbi-01-50.png)
    
    >**Note**: It may take several minutes to load all the tables.

1. Click on **File** and then click **Save** to save the file.

      ![](Images/did50.png)

1. Name the file as **MyFirstPowerBIModel**. Save the file in `C:\DIAD\Attendee\Attendee\Reports` folder.

1. On the left panel, click **Data ![](Images/powerbi-01-51.png) icon**  to view the data that was loaded. If you need to open Power Query editor, navigate to **Home -> Transform Data**.

      ![](Images/did52.png)

## Summary

In this lab, you have filled empty values, split columns, renamed columns, removed unwanted rows, transposed data and appended queries.
     
### You have successfully completed the lab!

# Lab 1: Accessing Data

### Estimated Duration: 30 minutes

## Overview

In this lab, you will explore the key features of the Power BI service. This introductory session will guide you through authoring reports using Power BI Desktop, creating operational dashboards, and sharing content via the Power BI Service, enabling you to turn data into actionable insights.

## Lab Objectives

- Task 1: Power BI Desktop - Get Data
- 



### Task 1: Power BI Desktop - Get Data

The dataset contains sales data of VanArsdel and other competitors. We have seven years of transaction data by day, product, and zip code for each 
manufacturer. We are going to analyze data from seven countries.

USA sales data is in a CSV file located in the USSales subfolder within the Data folder (/Data/USSales).

Sales of all other countries is in the InternationalSales subfolder within the Data folder (/Data/InternationalSales). Each country’s sales data is in a CSV file in this folder.

Product, Geography, and Manufacturer information is in a Microsoft Excel file called bi_dimensions.xlsx in the USSales subfolder within the Data folder (/Data/USSales/).
   
1. From the desktop, open the **Power BI Desktop**.
 
1. Click on **Sign in** from the top.

     ![](Images/did4.png)

1. Provide the Email address and click on **Continue**.

   * Email/Username: <inject key="AzureAdUserEmail"></inject>

1. Enter your Email address again followed by the password.

   * Email/Username: <inject key="AzureAdUserEmail"></inject>

   * Password: <inject key="AzureAdUserPassword"></inject>  

1. On the **Automatically sign in to all the desktop apps and websites on this device** pop-up, click on **No, this app only**.

     ![](Images/did5.png)

1. Click on **Options and settings (1)** from the left pane and select **Options (2)**.

     ![](Images/did6.png)
   
1. Check the box for **Shape map visual (1)** option and click on **OK (2)** to close the dialog.
 
     ![](Images/did7.png)

      > **Note:** Click on **OK** when you are prompted with the Feature requires a restart pop-up.

      ![](Images/did8.png)      
 
1. From the ribbon, click **File**, then click **Options and settings (1)**, then click **Options (2)**.
 
     ![](Images/did9.png)
 
1. In the left panel of **Options** dialog box, click **Regional Settings (1)** under Current File. From the Locale drop-down, click **English (United States) (2)**.

     ![](Images/did10.png)

1. Click **OK** to close the dialog box.
    
1. From the ribbon, click on **Home** and then click the **Get Data (1)** drop-down arrow. Select **Text/CSV (2)**.

     ![](Images/did11.png)

1. Browse to **Local Disk(C:)> DIAD**, double-click **Data**, double-click the **USSales** folder, and then select **sales.csv**.

1. Click on the **Open** button.

    ![](Images/ussales_file2.png)

1. Ensure **based on first 200 rows (1)** is selected for Data Type Detection and then click on **Transform Data (2)**.

     ![](Images/did12.png)
     
     >**Note**: You should be in the Query Editor window as shown in the screenshot below. The Query Editor is used to perform data shaping operations. Notice that the sales file you connected to shows as a query in the left panel. You can see a preview of the data in the center panel. Power BI predicts the data type of each field (based on the first 200 rows) as indicated next to the column header. In the right panel, steps that the Query Editor performs are recorded in the Applied Steps section.    
     
     ![](Images/powerbi-01-08.png)
     
     >**Note**: You will bring in sales data from other countries as well as performing certain data shaping operations.

15. Notice that Power BI has set the **Zip** field to the data type **Whole Number**. To ensure that the leading zero is not dropped from Zip codes that start with zero, we will format them as **Text**. To do this, select the **Zip column**. Then, from the ribbon, click **Home**, click **Data Type**, and change it to **Text**.

16. The **Change Column Type** dialog box opens. Click the **Replace Current** button which overwrites Power BI’s predicted data type.

    ![](Images/powerbi-01-09.png)
    
    Now let’s get the data that is in Excel source file.
    
17. From the ribbon, click **Home**, click **New Source**, and click then **Excel**.

    ![](Images/excel_workbook.png)
    
18. Browse to **Local Disk(C:)> DIAD**, double-click **Data**, double-click the **USSales** folder, and then click **bi_dimensions.xlsx**.

19. Click the **Open** button. The **Navigator** dialog box opens.

    ![](Images/ussales_file.png)
    
20. The **Navigator** dialog box lists three sheets that are in the Excel workbook. It also lists the **Product** table. Click **product** in the panel on the left. In the preview panel, notice that the first row is the headers. This is not part of the data.

21. Now, deselect **product** from the left panel and click **Product_Table**. Notice that this table has only the contents of the named table. This is the data we need.

    ![](Images/powerbi-01-12.png)
    
   >**Note**: Table names are differentiated from Worksheet names by using different icons.
    
22. From the left panel, click **geo**. In the preview panel, notice that the first few rows are headers and are not part of the data. We will remove them shortly.

23. From the left panel, click **manufacturer**. In the preview panel, notice that the last couple of rows are footers and are not part of the data. We will remove them shortly.

24. Make sure that **Product_Table**, **geo** and **manufacturer** are selected in the left panel, and then click **OK**. Notice all that three sheets are added as queries in the Query Editor.

    ![](Images/powerbi-01-13.png)

## Task 2: Adding additional data

In this scenario, the international subsidiaries have agreed to provide their sales data so that the company’s sales can be analyzed together. You’ve created a folder where they each put their data.

To analyze all the data together, you import the new data from each of the subsidiaries and combine it with the US Sales you loaded earlier.

You can load the files one at a time, like how you loaded the US Sales data, but Power BI provides an easier way to load all the files in a folder together.

25. On the **Home** tab of the Query Editor, click on the **New Source** drop-down menu.

26. Click **More…** as shown in the figure.

    ![](Images/powerbi-01-14.png)
    
27. The Get Data dialog box opens.

28. In the **Get Data** dialog box, click **Folder** as shown in the diagram.

29. Click **Connect** and the **Folder** dialog box will open.

    ![](Images/powerbi-01-15.png)
    
30. Click the **Browse…** button.

31. In the **Browse** for Folder dialog box, navigate to the location where you unzipped the class files.

32. Open the **This PC> Windows(C:)> DIAD**.

33. Open the **Data** folder.

34. Click the **InternationalSales** folder.

35. Click **OK** (to close the **Browse for Folder** dialog box).

36. Click **OK** (to close the **Folder** dialog box).

    ![](Images/powerbi-01-16.png)
    
      >**Note**: This approach will load all the files located in the folder. This is useful when you have a group that puts files on an FTP site each month and you are not always sure of the names of the files or the number of files. All the files must be of the same file type with columns in the same order.

The dialog box will display the list of files in the folder.

37. Click **Combine & Transform Data**.
 
    ![](Images/powerbi-01-17.png)
    
     >**Note**: The data in your file for **Date accessed**, **Date modified**, and **Date created** might be different than the dates displayed in the screenshot. 

The **Combine Files** dialog box will open. By default, Power BI will again detect the data type based on the first 200 rows. Notice there is an option to select various file Delimiters. The file we are working with is Comma delimited, so let’s leave the Delimiter option as Comma.

There is also an option to select each individual file in the folder (using **Example File** drop-down) to validate the format of the files.

38. Click **OK**.

    ![](Images/powerbi-01-18.png)

    You will now be in the **Query Editor** window with a new query named **InternationalSales**. 

39. If you do not see the **Queries** pane on left, click on the > (greater than) icon to expand. 

40. If you do not see the **Query Settings** pane on the right as shown in the figure, click on **View** in the ribbon and click **Query Settings** to see the pane. 

41. Click on the Query **InternationalSales**.

    ![](Images/powerbi-01-19.png)
    
    Notice that column Zip is of the Whole Number type. Based on the first 200 rows, Power BI thinks theZip column consists of whole numbers. But zip code could be alpha numeric in some countries orregions or contain leading zeros. If we do not change the data type, we will receive an error when we load the data shortly. So, let’s change the Zip column to data type Text.
 
42. Highlight the **Zip** column and change the **Data Type** to **Text**.

43. The **Change Column Type** dialog box will open. Click the **Replace Current** button.

    ![](Images/powerbi-01-20.png)
    
    In the Queries panel, notice that a Transform File from the InternationalSales folder is created. This contains the function used to load each of the files into the folder.

    ![](Images/powerbi-01-21.png)
    
    If you compare the **InternationalSales** and the **sales** table, you will see the **InternationalSales** table contains two new columns, **Source.Name** and **Country**.

44. We do not need the **Source.Name** column. Click the **Source.Name** column and right click and select **Remove** option or you can select the **Source.Name** column and then click on **Manage Coloumns** and then select **Remove Coloumns**.
    
45. Next, click the drop-down menu next to the **Country** column to see the unique values. 

46. You will only see Australia as shown in the figure. By default, Power BI only loads the first 1000 rows. Click **Load more** to validate that you have data from the various countries included.

   ![](Images/powerbi-01-23.png)
   
  Now, you will see the countries (blank), Australia, Canada, Germany, Japan, Mexico, and Nigeria.

   ![](Images/powerbi-01-24.png)
    
47. Click **OK**.

   >**Note**: You can perform various types of filters, sorting operations using the drop-down to verify the imported data. 

## Summary

### You have successfully completed the lab!

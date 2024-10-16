# Sales Trend Analysis of E-Commerce Plant Supplier from 2022-2024 

---

#### Dashboard Model to create key base measures - 
    

    **Sales = SUM(Fact_Sales[Sales_USD])
    Quantity = SUM(Fact_Sales[quantity])
    Gross Profit = [Sales] - [COGs]
    
    COGs = SUM(Fact_Sales[COGS_USD])**
    ```
    
    **Model Building - Create additional measures PYTD and YTD measures for base inputs:**
    
    **PYTD_Sales = 
    CALCULATE(
        [Sales], 
        SAMEPERIODLASTYEAR(Dim_Date[Date]), 
        Dim_Date[Inpast] = TRUE
    )
    
    PYTD_Quantity = 
    CALCULATE(
        [Quantity], 
        SAMEPERIODLASTYEAR(Dim_Date[Date]), 
        Dim_Date[Inpast] = TRUE
    )
    
    PYTD_GrossProfit = 
    CALCULATE(
        [Gross Profit], 
        SAMEPERIODLASTYEAR(Dim_Date[Date]), 
        Dim_Date[Inpast] = TRUE
    )
    
    YTD_Sales = TOTALYTD([Sales],Fact_Sales[Date_Time])
    YTD_Quantity = TOTALYTD([Quantity],Fact_Sales[Date_Time])
    YTD_GrossProfit = TOTALYTD([Gross Profit],Fact_Sales[Date_Time])**
    ```
    
    **Model Building - Create switch measures for model dashboard:**
    
   
    **S_PYTD = 
    VAR selected_value = SELECTEDVALUE(Slc_Values[Values])
    VAR result = SWITCH(selected_value, 
        "Sales", [PYTD_Sales],
        "Quantity", [PYTD_Quantity],
        "Gross Profit", [PYTD_GrossProfit],
        BLANK()
    )
    Return 
    result 
    
    S_YTD = 
    VAR selected_value = SELECTEDVALUE(Slc_Values[Values])
    VAR result = SWITCH(selected_value, 
        "Sales", [YTD_Sales],
        "Quantity", [YTD_Quantity],
        "Gross Profit", [YTD_GrossProfit],
        BLANK()
    )
    Return 
    result 
    
    YTD vs PYTD = [S_YTD]-[S_PYTD]**
    ```

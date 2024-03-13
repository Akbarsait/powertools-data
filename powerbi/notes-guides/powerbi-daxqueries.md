# DAX Queries 

### Getting Started
Reporting clients like Power BI and Excel execute DAX queries whenever a field is placed on a report or when a filter is applied. By using SQL Server Management Studio (SSMS), Power BI Report Builder, and open-source tools like DAX Studio, you can create and run your own DAX queries. DAX queries return results as a table right within the tool, allowing you to quickly create and test the performance of your DAX formulas.

DAX queries have a simple syntax comprised of just one required keyword, EVALUATE, and several optional keywords: ORDER BY, START AT, DEFINE, MEASURE, VAR, TABLE, and COLUMN. Each keyword defines a statement used for the duration of the query.

- More reading: https://learn.microsoft.com/en-us/dax/dax-queries
- working with DAX query view: https://learn.microsoft.com/en-us/power-bi/transform-model/dax-query-view
- Deep dive into DAX query view and writing DAX queries: https://powerbi.microsoft.com/en-us/blog/deep-dive-into-dax-query-view-and-writing-dax-queries/
- Weaving DataOps into Microsoft Fabric - DAX Query View Testing Pattern: https://www.kerski.tech/bringing-dataops-to-power-bi-part36/

#### Enable DAX query 
As of Mar 2024, DAX query is in preview mode.  To enable it go to File > Options and Settings > Options > Preview features and clicked the check box next to DAX query view
![Enable DAX Query](/assets/dax/daxqueries-1.png)

### DAX Query Tutorials
- Weaving DataOps into Microsoft Fabric - Version Control and Testing: https://www.youtube.com/watch?v=WyMQSyf3NvM
- Weaving DataOps into Microsoft Fabric - DAX Query View Testing Pattern: https://www.kerski.tech/bringing-dataops-to-power-bi-part36/
- How would you test your semantic model schemas with INFO DAX? | John Kerski posted on the topic: https://www.linkedin.com/posts/john-kerski-41a697100_with-the-recent-release-of-the-info-dax-functions-activity-7153415678111150080-lOMQ?utm_source=share&utm_medium=member_ios
- DataType Enum (Microsoft.AnalysisServices.Tabular): https://learn.microsoft.com/en-us/dotnet/api/microsoft.analysisservices.tabular.datatype?view=analysisservices-dotnet
- Relationships DAX query (using INFO.RELATIONSHIPS): https://www.datazoepowerbi.com/post/relationships-dax-query-using-info-relationships
- (3) DAX Query: Power up your Power BI! | LinkedIn - https://www.linkedin.com/pulse/dax-query-power-up-your-bi-hung-nguyen-rgy7e/
- Boost your productivity with DAX Query View in Power BI Desktop!: https://www.youtube.com/watch?v=oPGGYLKhTOA
- Create a measure from a filtered visual in Power BI? Of Course, you can!: https://www.youtube.com/watch?v=GFENAFw1co4
- Thinking about your DAX Queries like a SQL Query in Power BI: https://www.youtube.com/watch?v=tQrr7RPSvsQ&t=7s
- powerbi-desktop-samples/new-power-bi-service-samples at main · microsoft/powerbi-desktop-samples: https://github.com/microsoft/powerbi-desktop-samples/tree/main/new-power-bi-service-samples
- DAX Queries - DAX: https://learn.microsoft.com/en-us/dax/dax-queries
- DAX Query Best Practices and Historical Context (with Jeffrey Wang): https://www.youtube.com/watch?v=bCcJorCKw8k
- Unboxing DAX Query View in Power BI - Unplugged #54: https://www.youtube.com/watch?v=hiBRhmX-pbM
- DAX query view introduces new INFO DAX functions: https://powerbi.microsoft.com/en-us/blog/dax-query-view-introduces-new-info-dax-functions/
- Deep dive into DAX query view and writing DAX queries: https://powerbi.microsoft.com/en-us/blog/deep-dive-into-dax-query-view-and-writing-dax-queries/

### Data Transformation & Governance 
- Roche’s Maxim of Data Transformation: https://ssbipolar.com/2021/05/31/roches-maxim/
- Microsoft Fabric adoption roadmap: Governance: https://learn.microsoft.com/en-us/power-bi/guidance/fabric-adoption-roadmap-governance
- This project aims to provide a solution to collect activity & catalog data from your Power BI tenant using powershell scripts and a Power BI templates to analyse all this data: https://github.com/RuiRomano/pbimonitor

#### Power Query
- What is Power Query: https://learn.microsoft.com/en-us/power-query/power-query-what-is-power-query
- Blog Post on Power Query by SQLbi - https://www.sqlbi.com/topics/power-query/

### DAX Training
- Microsoft Learning Path: https://learn.microsoft.com/en-us/training/browse/?products=power-bi&expanded=power-platform&resource_type=learning%20path
- DAX and Power BI Free and Paid Training: https://www.sqlbi.com/training/
- Guy in a Cube Channel: https://www.youtube.com/@GuyInACube

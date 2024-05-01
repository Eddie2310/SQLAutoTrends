# SQLAutoTrends
This project utilizes SQL to delve into recall data, revealing key trends and insights in automotive safety.

**The this SQL statement calculates the total number of unique manufacturers listed in the "recalls_data" table.**

SELECT COUNT(DISTINCT Manufacturer) AS TotalManufacturers
FROM recalls_data;




**This SQL query retrieves recall data from the "recalls_data" table specifically for Tesla, Inc. Which is Company is used, you use any company listed in the table by changing Tesla, Inc.' to any name**

SELECT Manufacturer, Subject, Component, `Report Received Date`
FROM recalls_data
WHERE Manufacturer = 'Tesla, Inc.'
ORDER BY YEAR (`Report Received Date`) ASC;

**This SQL statement retrieves recall data for Tesla, Inc., including Manufacturer, Subject, Component, and Report Received Date, while also counting the occurrences of each subject, grouping the results by Manufacturer, Subject, Component, and Report Received Date, and ordering them by the year of the Report Received Date in descending order.**

SELECT Manufacturer, Subject, COUNT(Subject) AS SubjectCount, Component, `Report Received Date`
FROM recalls_data
WHERE Manufacturer = 'Tesla, Inc.'
GROUP BY Manufacturer, Subject, Component, `Report Received Date`
ORDER BY YEAR (`Report Received Date`) DESC;


**This SQL query counts the occurrences of each component in Tesla, Inc. recalls and presents the results, sorted by component count in descending order.**

SELECT Manufacturer, Component, COUNT(*) AS ComponentCount
FROM recalls_data
WHERE Manufacturer = 'Tesla, Inc.'
GROUP BY Manufacturer, Component
ORDER BY ComponentCount DESC;

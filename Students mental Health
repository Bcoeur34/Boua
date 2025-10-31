-- Summary: Student Mental Health Insights
--#This analysis provides a clear, data-driven perspective on the mental health of our student population, emphasizing key differences between international and domestic students.
--#By leveraging SQL-based analytics, we examined three core indicators, depression, social connectedness, and anxiety, and found that mental well-being is strongly influenced by background, living situation, and social integration.
-- #The findings reveal that international students tend to experience greater social isolation and elevated anxiety, while domestic students report higher levels of depression. These patterns suggest that both groups face distinct challenges requiring tailored support strategies.

--Strategic Recommendations (Summary)
-- 1- Expand Mental Health Support
--Strengthen counseling and early intervention programs tailored for both domestic and international students.
-----Promote Social Integration
--Launch peer mentorship and community events to build stronger connections and reduce isolation.
-----Enhance Residential Life
--Encourage on-campus living and social programs that support emotional well-being.
-----Monitor Mental Health Trends
--Conduct regular data-driven surveys to track progress and guide future decisions.
-----Increase Awareness and Reduce Stigma
--Run ongoing campaigns to normalize mental health discussions and encourage help-seeking.

-- View First 10 Records
SELECT TOP 10 *
FROM dbo.students;

--Total Number of Students
SELECT  COUNT(*) AS total_records
FROM students;

--Count of International vs Domestic Students
SELECT  inter_dom , COUNT(*) AS count_inter_dom
FROM students
GROUP BY inter_dom;

--Depression (PHQ) Analysis by Group
SELECT inter_dom ,MIN(todep) AS min_phq , MAX(todep) AS max_phq , 
 ROUND(AVG(todep) ,2) AS avg_phq
FROM students
GROUP BY inter_dom;

--Social Connectedness (SCS) by Group
SELECT inter_dom ,MIN(tosc) AS min_sc , MAX(tosc) AS max_sc , 
ROUND(AVG(tosc) ,2) AS avg_sc
FROM students
GROUP BY inter_dom;

--Academic Stress (AS) by Group
SELECT inter_dom ,MIN(toas) AS min_as , MAX(toas) AS max_as , ROUND(AVG(toas) ,2)
AS avg_as
FROM students
GROUP BY inter_dom;

--Top 10 International Students
SELECT TOP(10) *
FROM students
WHERE inter_dom= 'Inter';
--Suicidal Thoughts by Group
SELECT inter_dom , suicide , COUNT(suicide)AS count_suicide
FROM students
GROUP BY inter_dom , suicide ;

--Average Age by Group
SELECT inter_dom ,  AVG(age) AS avg_age
FROM students
GROUP BY inter_dom;
--Comparing Stay Duration and Well-being
SELECT stay, 
       ROUND(AVG(todep), 2) AS average_phq, 
       ROUND(AVG(tosc), 2) AS average_scs, 
       ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
--SQL_Oracle
--==========

--SQL_Oracle
--Created by Christine Tanner 10/11/2012 
--Final Test perfect score
--Display a list of instructors that brought in the most revenue


SELECT i.fname, i.lname, SUM(s.amtpaid)
FROM students s,courses c, instructors i
WHERE s.courseid=c.courseid 
AND i.instructorid=c.instructorid 
AND amtpaid IS NOT NULL
GROUP BY i.fname, i.lname
ORDER BY SUM(s.amtpaid) DESC, i.lname;
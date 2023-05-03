Download Link: https://assignmentchef.com/product/solved-cs348-project-2-pl-sql
<br>
In this project, you are asked to complete 5 procedures with PL/SQL.




Notes:




<ol>

 <li>The schema definition of database tables and sample test data are provided in <strong>sql </strong>and <strong>data.sql,</strong> respectively. You need to use <strong>droptables.sql</strong> to clean your database before you start this project because test data may be different from the data used in Project 1. Study and acquaint yourself with the schema (in tables.sql) and the data in the tables (in data.sql). This will make it easier to understand the required procedures.</li>

</ol>




<ol start="2">

 <li>You should finish all your work in <strong>sql</strong>. Skeleton code for procedures is already provided in answer.sql. Oracle will give error messages if you do not finish all of the procedures, so you can comment the unfinished ones during development.</li>

</ol>




<ol start="3">

 <li>Please do not change the names of procedures in answer.sql.</li>

</ol>




<ol start="4">

 <li>You can assume that all possible inputs to Procedures 1-4 will be legal input, but we will test illegal input in Procedure 5. So, the exception block is not required for testing Procedures 1-4. Please, refer to the requirement of Procedure 5 for details.</li>

</ol>




<ol start="5">

 <li>Submit your answer via <strong>Blackboard</strong>.</li>

</ol>




<ol start="6">

 <li>Hint: You may want to use the command “<strong>show errors;</strong>” to debug your procedures.</li>

</ol>




The detailed requirements of each procedure are listed below:







<h1> CarRentalSiteDetail</h1>




Create a procedure that shows the detailed information of a specific <strong>CarRentalSite</strong>, given the <strong>CarRentalSiteId</strong> as input. The detailed information should include the

following:

<ol>

 <li>CarRentalSite Name</li>

 <li>CarRentalSite City</li>

 <li>CarRentalSite total rentals in the Rentals table.</li>

 <li>The most popular <strong>compact</strong> car and the <strong>number of days rented</strong> in the Rentals table. We define the most popular compact car as the one having the largest number of rental days in the Rentals table. <strong><em>You can assume there is only one most popular compact car.</em></strong></li>

</ol>




<u>The output should be in the following format</u>:




<h2>CarRentalSiteDetail(1);</h2>




CarRentalSite Name: Hertz

CarRentalSite City: Lafayette

CarRentalSite Total Rentals: 6

Most Popular Compact Car: Chevy Spark Total Days Rented: 15




<h3>2. MonthlyBusinessRentalsReport</h3>

<strong> </strong>

Create a procedure that can generate a simple report for the <strong>business</strong> rentals of all months in the database. For each month, you need to list the total number of <strong>business</strong> rentals and the CarRentalSites that have business rentals in that month. Only display the months with <strong>business</strong> rentals. The ordering of months should be from the earliest to the latest and the ordering of CarRentalSites should be by <strong>CarRentalSiteName</strong> attribute.




<u>The output should be in the following format:</u>




<h2>MonthlyBusinessRentalsReport;</h2>




Total Business Rentals in 2018-1: 2

In Car Rental Sites:

<ul>

 <li>Hertz: 36 days</li>

</ul>

Total Business Rentals in 2018-2: 2

In Car Rental Sites:

<ul>

 <li>Alamo: 10 days</li>

 <li>Hertz: 14 days</li>

</ul>

Total Business Rentals in 2018-4: 1

In Car Rental Sites:

<ul>

 <li>Enterprise: 2 days</li>

</ul>

Total Business Rentals in 2018-5: 3

In Car Rental Sites:

<ul>

 <li>Avis: 2 days</li>

 <li>Budget: 3 days</li>

 <li>Hertz: 25 days</li>

</ul>

Total Business Rentals in 2018-6: 1 In Car Rental Sites:

<ul>

 <li>Alamo: 10 days</li>

</ul>




<h1> MostandLeastProfitCarIndiana</h1>

<strong> </strong>

Create a procedure that can generate a simple report for the cars with <strong>least average profit</strong> and <strong>most average profit</strong> in each car <strong>category</strong> ONLY for cars provided by car dealers located in <strong>Indiana</strong>. Here, we define the profit of a car as the average of :

(Rentals.RentalRate – Car.SuggestedDealerRentalPrice)

since the car appears in different rental entries with different rental rates. <u>Notice that</u> <u>there may be <strong>more than one car</strong> with the same average profit</u>. Display all the car names and their profit for all categories ordered by CarName.

<strong> </strong>

<u>The output should be in the following format:</u>







<h2>     MostandLeastProfitCarIndiana;</h2>

Least Profit in compact

<ul>

 <li>Ford Focus: 4</li>

 <li>Nissan Versa: 4</li>

 <li>Toyota Yaris: 4</li>

</ul>

Least Profit in luxury

<ul>

 <li>Porsche: 40</li>

</ul>

Least Profit in van

<ul>

 <li>Chrysler: 2</li>

</ul>

Most Profit in compact

<ul>

 <li>Chevy Spark: 5</li>

</ul>

Most Profit in luxury

<ul>

 <li>Audi: 45</li>

</ul>

Most Profit in van

<ul>

 <li>Honda Odyssey: 9</li>

</ul>










<h1> BusinessRentalCategory</h1>

<strong> </strong>

Create Procedure <strong>BusinessRentalCategory</strong> that will populate a table named <strong><u>BusinessRentalCategoryTable</u></strong> with the most recent information about how many car rentals of each of the following car categories: compact, SUV, and luxury, respectively.




<u>The output after running <strong>“select * from BusinessRentalCategoryTable;”</strong> should look</u> <u>like:</u>







CARRENTALSITEID    COMPACT     LUXURY      SUV ————— ———- ———- ———-

<table width="422">

 <tbody>

  <tr>

   <td width="240">             1    1</td>

   <td width="96">     0</td>

   <td width="86">       0</td>

  </tr>

  <tr>

   <td width="240">             2    1</td>

   <td width="96">     0</td>

   <td width="86">       0</td>

  </tr>

  <tr>

   <td width="240">             3    2</td>

   <td width="96">     0</td>

   <td width="86">       0</td>

  </tr>

  <tr>

   <td width="240">           4        0</td>

   <td width="96">     1</td>

   <td width="86">       0</td>

  </tr>

  <tr>

   <td width="240">             5    0 </td>

   <td width="96">     0</td>

   <td width="86">       1</td>

  </tr>

 </tbody>

</table>










<h1> CarCategoryInventoryInfo</h1>

<strong> </strong>

Given a <strong>CarSiteId</strong> as input, list the <strong>CarRentalSiteNames</strong> and the <strong>number of available cars</strong> in the car inventory. List the names of car rental sites (in alphabetical order) and the number of available cars in the car inventory. You may need to use <strong>Exception</strong> in PL/SQL to prevent your procedure from crashing if given an invalid customer id or an invalid product id.




<u>The output of a valid input should be similar to:</u>







<h2>CarCategoryInventoryInfo(1);</h2>




CarRentalSiteId: 1

CarRentalSiteName: Hertz

CarName: Chevy: 20

CarName: Chevy Spark: 10

CarName: Chrysler: 10

CarName: Honda CRV: 3




<u>The output of invalid inputs should be similar to</u>:




<h2>CarCategoryInventoryInfo(111);</h2>




CarRentalSiteId: 111 Invalid CarRentalSiteId!



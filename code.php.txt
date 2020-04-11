<?php
$servername = "localhost";
$username = "root";
$password = "VVVvvv1@";
$database = "db5";
$conn=new mysqli($servername,$username,$password,$database);
if($conn->connect_error)
{
die("connection failed" . $conn->connect_error);
}
else
{
if ($conn->query("insert into student1 values (1,'arun','sharma','a@gmail.com'); "))
if ($conn->query("insert into student1 values (2,'bharath','sharma','b@gmail.co m'); "))
if ($conn->query("insert into student1 values (3,'nitin','joshi','n@gmail.com') ; "))
{
echo "Values are inserted into student1";
}
else
echo "error caught";
}
$result=($conn->query("select * FROM student1 ORDER BY first_name DESC;"));
if ($result->num_rows >0)
{
while ($row=$result->fetch_assoc())
{
echo "\nid:".$row["id"];
echo "\nfirstname:".$row["first_name"];
echo "\nlastname:".$row["last_name"];
echo "\nemail:".$row["email"];
}
}
$conn->close();
?>

Create a form that accepts the dates from the user and write a JS code to calculate the difference
between two dates given by the user.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Date Difference Calculator</title>
</head>
<body>
    <h1>Date Difference Calculator</h1>
    <form id="dateForm">
        <label for="startDate">Start Date:</label>
        <input type="date" id="startDate" name="startDate" required>
        <br><br>
        <label for="endDate">End Date:</label>
        <input type="date" id="endDate" name="endDate" required>
        <br><br>
        <button type="button" onclick="calculateDifference()">Calculate Difference</button>
    </form>
    <p id="result"></p>

    <script>
        function calculateDifference() {
            // Get the values of the input fields
            const startDate = document.getElementById('startDate').value;
            const endDate = document.getElementById('endDate').value;

            // Convert the date strings to Date objects
            const start = new Date(startDate);
            const end = new Date(endDate);

            // Calculate the difference in time
            const differenceInTime = end.getTime() - start.getTime();

            // Calculate the difference in days
            const differenceInDays = differenceInTime / (1000 * 3600 * 24);

            // Display the result
            document.getElementById('result').innerText = `The difference between the two dates is ${differenceInDays} days.`;
        }
    </script>
</body>
</html>



2. Write a source code to create the login form that contains a textbox for username, a textbox for
password and a submit button. Make the following validations (both username and password are
required and cannot be the same and length should be greater than 5 characters long).
	
!DOCTYPE html>
<html lang="en">

<head>
    <title>Document</title>
</head>

<body>
    <!-- 
       Q2. Write a source code to create the login form that contains a textbox for username,
        a textbox for password and a submit button. Make the following validations 
        (both username and password are required and cannot be the same and length
        should be greater than 5 characters long). (2018) 
    -->

    <form action="profile.html" method="post" onsubmit="return validate()">
        Username: <input type="text" id="uName"><br><br>
        Password: <input type="password" id="uPass"><br><br>

        <input type="submit">
    </form>
    <script type="text/javascript">
        function validate() {
            var username = document.getElementById("uName").value;
            var password = document.getElementById("uPass").value;

            if (username.trim() == "" || password.trim() == "") {
                alert("Please enter the credentials.");
                return false;
            } else if (username.length < 6 || password.length < 6) {
                alert("Username and password should be greater than 5 characters.");
                return false;
            } else if (username == password) {
                alert("Username and password cannot be same.");
                return false;
            } else {
                return true;
            }
        }
    </script>
</body>

</html>


3. Make a form with name, address, email and password, then validate values for empty and correct
values using JavaScript.

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <!-- 
        Q3. Make a form with name, address, email and password, then validate
           values for empty and correct values using JavaScript. (2019)
    
        Ans: Assuming following "Test Cases" for validations:

             i. username, email, address and password should not be empty.
             ii. username, email, address and password should not accept blank spaces.
             iii. Both username and password should be "admin".
             iv. email format should be in standard form like e.g., "abc@gmail.com.np".
             v. address should strictly be "Nepal".
    -->

    <form action="profile.html" onsubmit="return validate()">
        Username: <input type="text" id="uName"><br><br>
        User Address: <input type="text" id="uAddress"><br><br>
        Email Address: <input type="email" id="uEmail"><br><br>
        Password: <input type="password" id="uPassword"><br><br>

        <input type="submit">
    </form>

    <script type="text/javascript">
        function validate() {
            var userName = document.getElementById("uName").value;
            var uAddress = document.getElementById("uAddress").value;
            var uEmail = document.getElementById("uEmail").value;
            var uPassword = document.getElementById("uPassword").value;

            //email validation
            var regularExp = /^([a-zA-Z0-9._-]+)@([a-zA-Z0-9-]+)\.([a-z]{2,20})\.([a-z]{2,20})$/;

            //address validations
            var regularAdd = /^Nepal$/;

            if (userName.trim() == "" || uAddress.trim() == "" || uEmail.trim() == "" || uPassword.trim() == "") {
                alert("Please enter the credentials.");
                return false;
            } else if (userName != "admin" || uPassword != "admin") {
                alert("Username and password did not match.");
                return false;
            }
            else if (!(regularExp.test(uEmail))) {
                alert("Invalid email address.");
                return false;
            } else if (!(regularAdd.test(uAddress))) {
                alert("Your address did not match.");
                return false;
            }
            else {
                return true;
            }
        }
    </script>
</body>

</html>



Create a two-dimensional array storing five student’s data and display them in HTML table.

<!DOCTYPE html>
<html lang="en">

<head>
    <title>Array Table - Example</title>
</head>

<body>
    <!-- 
        Q5. Define array. Create a two-dimensional array storing five student’s data 
        and display them in HTML table. (2022)
     -->
    <table border="1">
        <tr>
            <th>Name</th>
            <th>Semester</th>
            <th>Address</th>
            <th>Contact No.</th>
        </tr>
        <script type="text/javascript">
            var arr = new Array(
                Array("Dimaria", "Eight", "Argentina", 9999999999),
                Array("Ronaldo", "Seven", "Portugal", 7777777777),
                Array("Kante", "Six", "France", 8888888888),
                Array("Messi", "Fifth", "Argentina", 6666666666),
                Array("Ozil", "Fourth", "Germany", 5555555555)
            );

            for (var i = 0; i < arr.length; i++) {
                document.write("<tr>");
                for (var j = 0; j < arr[i].length; j++) {
                    document.write("<td>" + arr[i][j] + "</td>");
                }
                document.write("</tr>");
            }
        </script>
    </table>
</body>

</html>


5. Write a source code that enables the creation, retrieval, and deletion of a cookie containing a
username and password.


<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <script>
        //Simple Example for creating a cookie
         document.cookie = "name=dimaria; expires=Fri, 4 Aug 2023 12:00:00 UTC; path=/";

        //reading a cookie in console
        console.log(document.cookie);

        //deleting a cookie
        document.cookie = "name=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";
    </script>
</body>

</html>


6. Write an HTML and CSS source code to generate the following layouts using DIV.

<html>
    <head>
        <title>Positioning and Layout in CSS</title>
        <style>
            .container{
                margin: auto;
                height: 600px;
                width:1000px ;
                position: relative;
                border: 2px solid black;
            }
            .header{
                height: 150px;
                width: 1000px;
                position: absolute;
                border-bottom: 2px solid black;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .topic{
                height: 400px;
                width: 200px;
                top: 150px;
                position: absolute;
                border-right: 2px solid black;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .main{
                height: 400px;
                width: 600px;
                top: 150px;
                left: 200px;
                border-right: 2px solid black;
                position: absolute;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .other{
                height: 400px;
                width: 200px;
                top: 150px;
                left: 800px;
                position: absolute;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .copyright{
                height: 50px;
                width: 1000px;
                top: 550px;
                position: absolute;
                display: flex;
                justify-content: center;
                align-items: center;
                border-top: 2px solid black;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="header">Header Goes Here</div>
            <div class="topic">Topic HTML, CSS</div>
            <div class="main">Main Content Goes Here</div>
            <div class="other">Other Contents.....</div>
            <div class="copyright">Copyright © 2074 www.mysite.com</div>
        </div>
    </body>
</html>



8. Write a JavaScript program that display a text “Welcome to SDC - Class of 2023” after 5 seconds
in your browser.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome Message</title>
</head>
<body>
    <h1>Welcome Message</h1>
    <p id="welcomeMessage"></p>

    <script>
        // Function to display the welcome message
        function displayWelcomeMessage() {
            document.getElementById('welcomeMessage').innerText = "Welcome to SDC - Class of 2023";
        }

        // Set a timeout to display the message after 5 seconds (5000 milliseconds)
        setTimeout(displayWelcomeMessage, 5000);
    </script>
</body>
</html>




9. Write a JavaScript, create an array of fruits with values apple, orange, and mango. Then add three
more items in front of array using JavaScript function and remove two items from back of array.
Now display the items of array in string format.	

<!DOCTYPE html>
<html lang="en">

<head>
    <title>Document</title>
</head>

<body>
    <!-- 
        Q4. Write a JavaScript Program, create an array of fruits with values apple, orange,
           and mango. Then add three more items in front of array using JavaScript 
           function and remove two items from back of array. Now display the items
           of array in string format. (2020 makeup)
     -->

    <button onclick="addFruits()">Add Fruits</button>
    <button onclick="removeFruits()">Remove Fruits</button>

    <p id="output"></p>

    <script type="text/javascript">

        var fruits = ["apple", "orange", "mango"];
        document.getElementById("output").innerHTML = fruits; //default print

        function addFruits() {
            //adding fruits infront of the array
            fruits.splice(0, 0, "papaya", "cherry", "grapes");
            var result = fruits.toString();

            document.getElementById("output").innerHTML = result;
        }

        function removeFruits() {
            //removing fruits from back of an array
            fruits.splice(-2);
            var result = fruits.toString();

            document.getElementById("output").innerHTML = result;
        }
    </script>
</body>

</html>



10. Create a form which contains text field for username, password, age, radio button for gender and
a submit button. When submit is clicked perform following validation: all the fields are required,
radio button should be selected, username should be between 2-to-15-character, password should
be equals to “SDCBIM”, age should contain number only and should be between 15 to 30. If all
the values of fields are entered correctly display “welcome”.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation</title>
</head>
<body>
    <h1>Registration Form</h1>
    <form id="registrationForm" onsubmit="return validateForm()">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
        <br><br>
        
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required>
        <br><br>
        
        <label for="age">Age:</label>
        <input type="number" id="age" name="age" required>
        <br><br>
        
        <label>Gender:</label>
        <input type="radio" id="male" name="gender" value="male">
        <label for="male">Male</label>
        <input type="radio" id="female" name="gender" value="female">
        <label for="female">Female</label>
        <br><br>
        
        <button type="submit">Submit</button>
    </form>
    <p id="message"></p>

    <script>
        function validateForm() {
            // Get form values
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const age = document.getElementById('age').value;
            const genderMale = document.getElementById('male').checked;
            const genderFemale = document.getElementById('female').checked;

            // Validate username length
            if (username.length < 2 || username.length > 15) {
                alert('Username should be between 2 and 15 characters.');
                return false;
            }

            // Validate password
            if (password !== 'SDCBIM') {
                alert('Password should be "SDCBIM".');
                return false;
            }

            // Validate age
            if (isNaN(age) || age < 15 || age > 30) {
                alert('Age should be a number between 15 and 30.');
                return false;
            }

            // Validate gender selection
            if (!genderMale && !genderFemale) {
                alert('Please select a gender.');
                return false;
            }

            // All validations passed
            document.getElementById('message').innerText = 'Welcome';
            return false; // Prevent form submission to display message
        }
    </script>
</body>
</html>



11. Write a program to create array of size 10 which contains name of students as elements. Change
the array into string, add two elements from position 5, remove 4 elements from position 6, insert
three elements in last position, and extract any three elements from array. Display all the results.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Array Operations</title>
</head>
<body>
    <h1>Array Operations</h1>
    <script>
        // Step 1: Create an array of size 10 containing names of students
        let students = ["Alice", "Bob", "Charlie", "David", "Eva", "Frank", "Grace", "Hannah", "Ivy", "Jack"];
        document.write("<p>Original Array: " + students + "</p>");

        // Step 2: Change the array into a string
        let studentsString = students.toString();
        document.write("<p>Array as String: " + studentsString + "</p>");

        // Step 3: Add two elements from position 5
        students.splice(5, 0, "Kevin", "Laura");
        document.write("<p>Array after adding two elements at position 5: " + students + "</p>");

        // Step 4: Remove 4 elements from position 6
        students.splice(6, 4);
        document.write("<p>Array after removing 4 elements from position 6: " + students + "</p>");

        // Step 5: Insert three elements at the last position
        students.push("Megan", "Nathan", "Olivia");
        document.write("<p>Array after adding three elements at the end: " + students + "</p>");

        // Step 6: Extract any three elements from the array
        let extractedElements = students.slice(2, 5); // Extract 3 elements starting from position 2
        document.write("<p>Extracted Elements: " + extractedElements + "</p>");
    </script>
</body>
</html>




12. Write an HTML and CSS source code to generate the following layouts using DIV.
<html>
    <head>
        <title>Positioning and layout</title>
        <style>
            .container{
                margin: auto;
                height: 600px;
                width: 800px;
                border: 2px solid black;
                position: relative;
            }
            .header{
                position: absolute;
                height: 50px;
                width: 800px;
                font-size: 30px;
                font-weight: bolder;
                border-bottom: 2px solid black;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .navigation{
                position: absolute;
                height: 50px;
                width: 800px;
                top: 50px;
                font-size: 30px;
                font-weight: bolder;
                border-bottom: 2px solid black;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .index{
                position: absolute;
                height: 400px;
                width: 200px;
                top: 100px;
                font-size: 30px;
                font-weight: bolder;
                border-right: 2px solid black;
                border-bottom: 2px solid black;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .content{
                position: absolute;
                height: 400px;
                width: 600px;
                top: 100px;
                left: 200px;
                font-size: 30px;
                font-weight: bolder;
                border-bottom: 2px solid black;
                display: flex;
                justify-content: center;
                align-items: center;
            }
            .footer{
                position: absolute;
                height: 100px;
                width: 800px;
                top: 500px;
                font-size: 30px;
                font-weight: bolder;
                display: flex;
                justify-content: center;
                align-items: center;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <div class="header">Header Section</div>
            <div class="navigation">Navigation Bar</div>
            <div class="index">Index</div>
            <div class="content"> content Section</div>
            <div class="footer">Footer Section</div>
        </div>
    </body>
</html>


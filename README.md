# Table
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
        crossorigin="anonymous"></script>
</head>

<body>
    <div class="container" id="movies-list">
        <!-- <table class="table table-hover">
            <thead>
                <tr>

                    <th scope="col">First-Name</th>
                    <th scope="col">Last-Name</th>
                    <th scope="col">Department</th>
                    <th scope="col">Salary</th>
                    <th scope="col">Loc</th>
                    <th scope="col">Action</th>

                </tr>
            </thead>
            <tbody>
                <tr id="tr">
                    <th id="101">Tushar</th>
                    <td id="102">Patil</td>
                    <td id="103">Developer</td>
                    <td id="104">1000000</td>
                    <td id="105">Pune</td>
                    <td id="106">
                        <button type="button" class="btn btn-primary" onclick="homeTable(101)">Add</button>
                        <button type="button" class="btn btn-secondary">Delete</button>
                    </td>
                </tr>
            </tbody>
        </table> -->
    </div>

    <script>
        window.onload = function () {
            console.log("Hello World")
        }

        let homet = [
            {
                firstname: "Tushar",
                lastname: "Patil",
                dept: "Developer",
                salary: 12345,
                loc: "Pune",
                Action: `<button type="button" class="btn btn-primary" onclick="homeTable(101)">Add</button>
                        <button type="button" class="btn btn-secondary">Delete</button>`
            },
            {
                firstname: "Tushar",
                lastname: "Patil",
                dept: "Developer",
                salary: 12345,
                loc: "Pune",
                Action: `<button type="button" class="btn btn-primary" onclick="homeTable(101)">Add</button>
                        <button type="button" class="btn btn-secondary">Delete</button>`
            }
        ];
        const homeTable = () => {
            let firstname = prompt("Enter first Name");
            let lastname = prompt("Enter last Name");
            let dept = prompt("Enter Department");
            let salary = prompt("Enter the Salary");
            let loc = prompt("Enter Location");
            let Action = `<button type="button" class="btn btn-primary" onclick="homeTable()">Add</button>
                        <button type="button" class="btn btn-secondary">Delete</button>`

            let obj1 = {
                fName: firstname,
                lName: lastname,
                deptN: dept,
                salarY: salary,
                loC: loc,
                ActioN: Action
            }
           homet.push(obj1);
           console.log(homet);
        }
        let newArr=homet.map(myFunction);
        function myFunction(value,index){
           return value;
        }

       localStorage.setItem("Arrays",JSON.stringify(newArr))

        function displayMovies(homet) {
            let table = ' <table class="table table-hover">';
            table += `<thead>
                <tr>

                    <th scope="col">First-Name</th>
                    <th scope="col">Last-Name</th>
                    <th scope="col">Department</th>
                    <th scope="col">Salary</th>
                    <th scope="col">Loc</th>
                    <th scope="col">Action</th>

                </tr>
            </thead>`;
            homet.forEach((home, index) => {
                table = table + `<tr>`;
                table = table + `<td> ${home.firstname}</td>`;
                table = table + `<td> ${home.lastname}</td>`;
                table = table + `<td> ${home.dept}</td>`;
                table = table + `<td> ${home.salary}</td>`;
                table = table + `<td> ${home.loc}</td>`;
                table = table + `<td> ${home.Action}</td>`;
                table += `</tr>`;
            });
            table += "</table>";
            document.getElementById("movies-list").innerHTML = table;
        }

        displayMovies(homet);
    </script>
</body>

</html>


/////////////////////////////////////////////////////////


<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
        crossorigin="anonymous"></script>
</head>

<body>
    <div class="container" id="T-list">
        
    </div>
    <!-- <div>
        <button onclick=" displayData(jData)">Create</button>
    </div> -->

    <script>
        window.onload = function () {
            console.log("Hello World")
        }

        let jData = [
            {
                firstname: "Gaurav",
                lastname: "Patil",
                dept: "Developer",
                salary: 10000,
                Age: 21,
                Action: `<button type="button" class="btn btn-outline-success"onclick="homeTable()">Add</button>
                        <button type="button" class="btn btn-outline-danger">Delete</button>`
            },
            {
                firstname: "Tushar",
                lastname: "Patil",
                dept: "Engineer",
                salary: 12345,
                Age: 20,
                Action: `<button type="button" class="btn btn-outline-success"onclick="homeTable()">Add</button>
                        <button type="button" class="btn btn-outline-danger" >Delete</button>`
            },
            {
                firstname: "Gaurav",
                lastname: "Dhamankar",
                dept: "Software",
                salary: 12000,
                Age: 21,
                Action: `<button type="button" class="btn btn-outline-success"onclick="homeTable()">Add</button>
                        <button type="button" class="btn btn-outline-danger">Delete</button>`
            },
            {
                firstname: "Mohit",
                lastname: "Khodse",
                dept: "Engineer",
                salary: 13000,
                Age: 21,
                Action: `<button type="button" class="btn btn-outline-success"onclick="homeTable()">Add</button>
                        <button type="button" class="btn btn-outline-danger">Delete</button>`
            },
            {
                firstname: "Gaurav",
                lastname: "Patil",
                dept: "Developer",
                salary: 10000,
                Age: 21,
                Action: `<button type="button" class="btn btn-outline-success"onclick="homeTable()">Add</button>
                        <button type="button" class="btn btn-outline-danger">Delete</button>`
            }
        ];
        const homeTable = () => {
            let firstname = prompt("Enter first Name");
            let lastname = prompt("Enter last Name");
            let dept = prompt("Enter Job title");
            let salary = prompt("Enter the Salary");
            let Age = prompt("Enter Age");
            let Action = `<button type="button" class="btn btn-outline-success"onclick="homeTable()">Add</button>
                        <button type="button" class="btn btn-outline-danger">Delete</button>`

            let obj1 = {
                fName: firstname,
                lName: lastname,
                deptN: dept,
                salarY: salary,
                Age: Age,
                ActioN: Action
            }
           jData.push(obj1);
           console.log(jData);
           localStorage.setItem("Array",JSON.stringify(obj1))


        }
        // let newArr=jData.map(myFunction);
        // function myFunction(value,index){
        //    return value;
        // }

       localStorage.setItem("Array_1",JSON.stringify(jData))

        function displayData(jData) {
            let table = ' <table class="table table-striped table-hover mt-4 ">';
            table += `<thead class="table-info">
                <tr>

                    <th scope="col">First-Name</th>
                    <th scope="col">Last-Name</th>
                    <th scope="col">Job Title</th>
                    <th scope="col">Salary</th>
                    <th scope="col">Age</th>
                    <th scope="col">Action</th>

                </tr>
            </thead>`;
            jData.forEach((tRow, index) => {
                table = table + `<tr>`;
                table = table + `<td> ${tRow.firstname}</td>`;
                table = table + `<td> ${tRow.lastname}</td>`;
                table = table + `<td> ${tRow.dept}</td>`;
                table = table + `<td> ${tRow.salary}</td>`;
                table = table + `<td> ${tRow.Age}</td>`;
                table = table + `<td> ${tRow.Action}</td>`;
                table += `</tr>`;
            });
            table += "</table>";
            document.getElementById("T-list").innerHTML = table;
        }

        displayData(jData);
    </script>
</body>

</html>

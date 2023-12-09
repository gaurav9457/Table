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


//////////////////////////////////////////////

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN"
      crossorigin="anonymous"
    />
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
      crossorigin="anonymous"
    ></script>
    <style>
        .popup {
            display:none;
            position:fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: grey;
            text-align: center;
        }
        .popup-content {
            position: relative;
            /* top: 50%; */
            /* transform: translateY(-50%); */
            background-color: black;
            color: white;
            width: 80%;
            max-width: 450px;
            margin: 0 auto;
            padding: 20px;
            border-radius: 5px;
        }
        .close {
            position: absolute;
            top: 10px;
            right: 10px;
            cursor: pointer;
        }
    </style>
  </head>
  <body>
    <!----------------- NavBar ---------------- -->
    <div class="container-fluid bg-body-tertiary">
      <div class="container">
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">Employee Data</a>
          </div>
        </nav>
      </div>
    </div>

    <!-- -----------Form-------------- -->
    <div class="container " >
      
         <form action="" id="EmployeeData">
              <div class="row mx-md-5">
            <h5 class="mt-3">Personal Information :</h5>
            <div class="col-md-8 mx-md-5">
               
                <label for="fname" class="form-label">Fullname</label>
                <input
                  type="text"
                  id="fname"
                  class="form-control" placeholder="Enter Your Fullname" required />
                
                  <label for="flexRadioDefault1" class="form-label">Gender</label>
              
                  <div class="form-check">
                    <input type="radio" id="gender" name="gender" value="Male"> <label for="male">Male</label>
                
                    <!-- <label class="form-check-label" for="flexRadioDefault1">
                     Male
                    </label> -->
                    
                  </div>
                  <div class="form-check">
                    <input type="radio" id="gender" name="gender" value="Female"> <label for="female">Female</label>
                    <!-- <label class="form-check-label" for="flexRadioDefault2">
                      Female
                    </label> -->
                  </div>
                  <label for="dob">Date Of Birth :</label>
              <div class="row mt-2">
                <div class="col-md-4">
              <input type="date" name="" id="dob"> 
            </div>
        </div>
        

    </div>

    <h5 class="mt-3">Contact Details :</h5>
    <div class="col-md-8 mx-md-5">
               
        <label for="hno" class="form-label">Address</label>
        <input
          type="text"
          id="hno"
          class="form-control" placeholder="House No "/>
        
          <label for="Street" class="form-label">Street</label>
        <input
          type="text"
          id="Street"
          class="form-control" placeholder="Street"/>
          <label for="City" class="form-label">City</label>
        <input
          type="text"
          id="City"
          class="form-control" placeholder="City"/>
          <label for="state" class="form-label">State</label>
          <input
            type="text"
            id="state"
            class="form-control" placeholder="State"/>

          </div>
          
     <h5 class="mt-3">Employment Details</h5>   
     <div class="col-md-8 mx-md-5">
               
        <label for="jTitle" class="form-label">Job Title</label>
        <input
          type="text"
          id="jTitle"
          class="form-control" placeholder="Enter Job Title"/>
        
          <label for="Department" class="form-label">Department</label>
        <input
          type="text"
          id="Department"
          class="form-control" placeholder="Department"/>
          <label for="Empid" class="form-label">Employee Id</label>
        <input
          type="text"
          id="Empid"
          class="form-control" placeholder="Empid"/>
          

    </div> 

    <h5 class="mt-3" >Education Details</h5> 
    <div class="row">
      <div class="col-md-4"><div>
        <label for="Passout" class="form-label">Passout Date :</label>
        <div>
        <input type="date" id="Passout"/>
      </div>
    </div></div>
      <div class="col-md-4"> <label for="Marks" class="form-label">Marks</label>
        <input
          type="number"
          id="Marks"
          class="form-control" placeholder="Enter Marks"/></div>
      <div class="col-md-4">  <label for="field" class="form-label">Field</label>
        <input
          type="text"
          id="field"
          class="form-control" placeholder="Enter Field"/></div>
    </div>  
     <!-- <div class="col-md-8 mx-md-5"> -->
        <!-- <div>
          <label for="Passout" class="form-label">Passout Date :</label>
          <div>
          <input type="date" id="Passout"/>
        </div>
      </div> -->
        
          <!-- <label for="Marks" class="form-label">Marks</label>
        <input
          type="number"
          id="Marks"
          class="form-control" placeholder="Enter Marks"/> -->
          <!-- <label for="field" class="form-label">Field</label>
        <input
          type="text"
          id="field"
          class="form-control" placeholder="Enter Field"/> -->
          
    </div> 


    <div class="col-md-6 mx-md-auto d-flex justify-content-between">
    <button class="btn btn-success btn-lg mt-3" type="Submit" value="Submit" onclick="return submitForm()">Submit</button>
    <button class="btn btn-outline-danger btn-lg mt-3" type="" value="Cancle">Cancle</button>
     </div>
         </div>
         </form>
</div>

      <!-- ----------Footer------------- -->
     <div class="container-fluid bg-body-tertiary mt-4">
        <footer class="py-3 my-4">
            <ul class="nav justify-content-center border-bottom pb-3 mb-3">
              <li class="nav-item"><a href="http://127.0.0.1:5500/Form.html?" class="nav-link px-2 text-muted">Home</a></li>
              <li class="nav-item"><a href="#" class="nav-link px-2 text-muted">Features</a></li>
              <li class="nav-item"><a href="#" class="nav-link px-2 text-muted">Pricing</a></li>
              <li class="nav-item"><a href="#" class="nav-link px-2 text-muted">FAQs</a></li>
              <li class="nav-item"><a href="#" class="nav-link px-2 text-muted">About</a></li>
            </ul>
            <p class="text-center text-muted">© 2022 Company, Inc</p>
          </footer>
     </div>

     <div id="popup" class="popup">
        <div class="popup-content">
            <span class="close" onclick="closePopup()">&times;</span>
            <h2>Employee data Submitted</h2>
            <div id="popup-content"></div>
        </div>
    </div>



</div>
      <!-- </div> -->
    </div>
   
    <script>
         function submitForm() {
            
            const firstName = document.getElementById('fname').value;
            const gender = Array.from(document.querySelectorAll('input[name="gender"]:checked')).map(e => e.value);
            // const gender=document.getElementById('gender').value;
            const dob = document.getElementById('dob').value;
           
            const hno =document.getElementById('hno').value;
            const Street =document.getElementById('Street').value;
            const City =document.getElementById('City').value;

            const jTitle =document.getElementById('jTitle').value;
            const Department =document.getElementById('Department').value;
            const Empid =document.getElementById('Empid').value;

            const Passout =document.getElementById('Passout').value;
            const Marks =document.getElementById('Marks').value;
            const field =document.getElementById('field').value;
           
            
            const popupContent = `
                <p><b>First Name:</b> ${firstName}</p>
                <p><b>Gender:</b> ${gender}</p>
                <p><b>Date of Birth:</b> ${dob}</p>
                <p><b>Address :</b> ${hno}</p>
                <p><b>Street :</b> ${Street}</p>
                <p><b>City :</b> ${City}</p>
                <p><b>Job Title:</b> ${jTitle}</p>
                <p><b>Department:</b> ${Department}</p>
                <p><b>Employee Id:</b> ${Empid}</p>
                <p><b>Passout Date:</b> ${Passout}</p>
                <p><b>Marks :</b> ${Marks}</p>
                <p><b>field:</b> ${field}</p>
                `;
               alert("Form Submitted")
            const popup = document.getElementById('popup');
            const popupContentDiv = document.getElementById('popup-content');
            popupContentDiv.innerHTML = popupContent;
            popup.style.display = 'block';

            document.getElementById('EmployeeData').reset();
            
            const StoreData={
              firstName : firstName,
              gender : gender,
              dob :dob,
              hno :hno,
              Street :Street,
              City :City,
              jTitle :jTitle,
              Department :Department,
              Empid :Empid,
              Passout :Passout,
              Marks :Marks,
              field :field

            }
            localStorage.setItem("Name",JSON.stringify(StoreData));
            return false; 
        }

         
        function closePopup() {
            
            const popup = document.getElementById('popup');
            popup.style.display = 'none';
            const popupContentDiv = document.getElementById('popup-content');
            popupContentDiv.innerHTML = '';
        }

         
    </script>
    <script
      src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js"
      integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.min.js"
      integrity="sha384-BBtl+eGJRgqQAUMxJ7pMwbEyER4l1g+O15P+16Ep7Q9Q+zqX6gSbd85u4mG4QzX+"
      crossorigin="anonymous"
    ></script>
  </body>
</html>

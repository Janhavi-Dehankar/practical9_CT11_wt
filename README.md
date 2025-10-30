# practical9_CT11_wt
contains web technology practical 9
<!DOCTYPE html>
<html>
<head>
  <title>Admission Registration Form Validation</title>
  <script>
    function validateForm() {
      let name = document.getElementById("name").value;
      let age=document.getElementById("age").value;
      let email = document.getElementById("email").value;
      let password = document.getElementById("password").value;
      let phone = document.getElementById("phone").value;

      if (name.trim() === "") {
        alert("Please enter your name.");
        return false;
      }

      if(age<17)
      {
        alert("age should be greater than or equals to 18");
        return false;
      }

      let emailPattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
      if (!email.match(emailPattern)) {
        alert("Please enter a valid email address.");
        return false;
      }

      if (password.length < 6) {
        alert("Password must be at least 6 characters long.");
        return false;
      }

      let phonePattern = /^[0-9]{10}$/;
      if (!phone.match(phonePattern)) {
        alert("Please enter a valid 10-digit phone number.");
        return false;
      }

      alert("Form submitted successfully!");
      return true;
    }
  </script>
</head>

<body>
  <h2>Admission Registration Form</h2>
  <form onsubmit="return validateForm()">
    <label>Full Name:</label><br>
    <input type="text" id="name" placeholder="Enter your full name"><br><br>

    <label>Age:</label><br>
    <input type="text" id="age" placeholder="Enter your age"><br><br>

    <label>Email:</label><br>
    <input type="text" id="email" placeholder="Enter your email"><br><br>

    <label>Password:</label><br>
    <input type="password" id="password" placeholder="Enter your password"><br><br>

    <label>Phone Number:</label><br>
    <input type="text" id="phone" placeholder="Enter your phone number"><br><br>

    <input type="submit" value="Submit">
  </form>
</body>
</html>

<!DOCTYPE html>
<html>
<head>
    <title>Registration Form</title>

    <!-- Internal CSS -->
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f0f4ff;
        }
        .container {
            width: 420px;
            margin: auto;
            background: white;
            padding: 25px;
            margin-top: 50px;
            border-radius: 10px;
            box-shadow: 0px 0px 12px rgba(0,0,0,0.2);
        }
        h2 {
            text-align: center;
            margin-bottom: 20px;
        }
        input {
            width: 100%;
            padding: 10px;
            margin: 7px 0;
            border: 1px solid #aaa;
            border-radius: 5px;
        }
        button {
            width: 100%;
            padding: 12px;
            margin-top: 15px;
            border: none;
            background: #1e90ff;
            color: white;
            font-size: 18px;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #005bbb;
        }
        .error {
            color: red;
            font-size: 14px;
            margin-bottom: -5px;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Registration Form</h2>

    <form onsubmit="return validateForm()">
        <label>Full Name</label>
        <input type="text" id="name">

        <label>Email</label>
        <input type="text" id="email">

        <label>Password</label>
        <input type="password" id="password">

        <label>Confirm Password</label>
        <input type="password" id="confirmPassword">

        <p class="error" id="errorMsg"></p>

        <button type="submit">Register</button>
    </form>
</div>

<!-- JavaScript Validation -->
<script>
function validateForm() {
    var name = document.getElementById("name").value;
    var email = document.getElementById("email").value;
    var password = document.getElementById("password").value;
    var confirmPassword = document.getElementById("confirmPassword").value;
    var errorMsg = document.getElementById("errorMsg");

    if (name == "" || email == "" || password == "" || confirmPassword == "") {
        errorMsg.innerHTML = "All fields are required!";
        return false;
    }

    var emailPattern = /\S+@\S+\.\S+/;
    if (!emailPattern.test(email)) {
        errorMsg.innerHTML = "Enter a valid email!";
        return false;
    }

    if (password.length < 6) {
        errorMsg.innerHTML = "Password must be at least 6 characters!";
        return false;
    }

    if (password !== confirmPassword) {
        errorMsg.innerHTML = "Passwords do not match!";
        return false;
    }

    alert("Registration Successful!");
    return true;
}
</script>

</body>
</html>

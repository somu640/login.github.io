<!DOCTYPE html>

<head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="login.css">
    <script src="login.js"></script>
</head>

<body>
    <div class="wrapper">
        <h2>619 emplogin</h2>
        <div id="error_message"></div>
        <form id="myform" action="success.html" method="POST" onsubmit="return validation()">
            <div class="input_field">
                <input type="text" placeholder="name" id="name">
            </div>
            <div class="input_field">
                <input type="text" placeholder="xyz@gmail.com" id="email">
            </div>
            <div class="input_field">
                <input type="text" placeholder="8885365912" id="phone">
            </div>
            <div class="btn">
                <input type="submit">
            </div>

        </form>
    </div>
</body>

</html>


* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    outline: none;
    font-family: "Josefin Sans", sans-serif;
}

body {
    background: #fece0c;
}

.wrapper {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    max-width: 350px;
    width: 100%;
    background: #fff;
    padding: 25px;
    border-radius: 5px;
    box-shadow: 4px 4px 2px rgba(254, 236, 164, 1);
}

.wrapper h2 {
    text-align: center;
    margin-bottom: 20px;
    text-transform: uppercase;
    letter-spacing: 3px;
    color: #332902;
}

.wrapper .input_field {
    margin-bottom: 10px;
}

.wrapper .input_field input[type='text'] {
    width: 100%;
    border: 1px solid #e0e0e0;
    padding: 10px;
}

.wrapper .btn input[type='submit'] {
    border: 0;
    margin-top: 15px;
    padding: 10px;
    width: 100%;
    background: #fece0c;
    color: #332902;
    text-transform: uppercase;
    letter-spacing: 5px;
    font-weight: bold;
    border-radius: 25px;
    cursor: pointer;
}

.wrapper #error_message {
    margin-bottom: 20px;
    padding: 10px;
    background: #fe8b8e;
    text-align: center;
    font-size: 14px;
    transition: all 0.5s ease;
}

function validation() {
    var name = document.getElementById("name").value;
    var email = document.getElementById("email").value;
    var phone = document.getElementById("phone").value;
    var error_message = document.getElementById("error_message");
    var text;
    var pattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;

    error_message.style.padding = "10px";
    if (name.length < 5) {
        text = "Please enter a valid name";
        error_message.innerHTML = text;
        return false;
    }
    if (email.indexOf("@") == -1 || email.length < 6) {
        text = "Please enter a valid Email";
        error_message.innerHTML = text;
        return false;
    }
    if (email.match(pattern)) {
        text = "Entered Email is valid";
        error_message.innerHTML = text;
        return true;
    }
    if (isNaN(phone) || phone.length != 10) {
        text = "Please enter a valid Phone number";
        error_message.innerHTML = text;
        return false;
    }

    alert("Form submitted successfully")
    return true;

}

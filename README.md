# HARISH-K_511321104028_NAANMUDHALVAN_PROJECT_FILE

FOR GITHUB README FILE:


PROJECT CREATED BY:

NAME: HARISH K

REGISTER NO: 511321104028

COLLEGE CODE: 5113

COLLEGE NAME:KINGSTON ENGINEERING COLLEGE

LOGIN DETAILS:

USERNAME: admin

PASSWORD: admin

body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    margin: 0;
    padding: 0;
}

.container {
    max-width: 500px;
    margin: 50px auto;
    background-color: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1 {
    text-align: center;
    color: #333;
}

.form-group {
    margin-bottom: 15px;
}

label {
    display: block;
    margin-bottom: 5px;
    color: #666;
}

input[type="text"],
input[type="email"] {
    width: 100%;
    padding: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-sizing: border-box;
}

button {
    display: block;
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

#message {
    margin-top: 20px;
    padding: 10px;
    border-radius: 4px;
}

.success {
    background-color: #d4edda;
    color: #155724;
}

.error {
    background-color: #f8d7da;
    color: #721c24;
}
document.getElementById('userForm').addEventListener('submit', function(e) {
    e.preventDefault();
    
    var name = document.getElementById('name').value;
    var email = document.getElementById('email').value;

    fetch('/api/users', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify({name: name, email: email}),
    })
    .then(response => response.json())
    .then(data => {
        document.getElementById('message').innerHTML = 'User registered successfully!';
        document.getElementById('message').className = 'success';
        document.getElementById('userForm').reset();
    })
    .catch((error) => {
        document.getElementById('message').innerHTML = 'Error: ' + error;
        document.getElementById('message').className = 'error';
    });
});


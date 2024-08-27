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

<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>PG Registration</title>
    <link rel="stylesheet" th:href="@{/css/style.css}">
</head>
<body>
    <h1>PG Registration</h1>
    <form th:action="@{/register}" th:object="${user}" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" th:field="*{name}" required><br>

        <label for="email">Email:</label>
        <input type="email" id="email" th:field="*{email}" required><br>

        <label for="phoneNumber">Phone Number:</label>
        <input type="tel" id="phoneNumber" th:field="*{phoneNumber}" required><br>

        <label for="aadhaarNumber">Aadhaar Number:</label>
        <input type="text" id="aadhaarNumber" th:field="*{aadhaarNumber}" required><br>

        <label for="city">City:</label>
        <input type="text" id="city" th:field="*{city}" required><br>

        <input type="submit" value="Register">
    </form>
</body>
</html>


<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>Vacant Rooms</title>
    <link rel="stylesheet" th:href="@{/css/style.css}">
</head>
<body>
    <h1>Vacant Rooms and Pricing</h1>
    <table>
        <tr>
            <th>Room Type</th>
            <th>Availability</th>
            <th>Cost per Person</th>
        </tr>
        <tr>
            <td>Single Room</td>
            <td>5</td>
            <td>₹5000/month</td>
        </tr>
        <tr>
            <td>Double Sharing</td>
            <td>10</td>
            <td>₹3500/month</td>
        </tr>
        <tr>
            <td>Triple Sharing</td>
            <td>15</td>
            <td>₹2500/month</td>
        </tr>
    </table>
</body>
</html>



<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>Admin Page</title>
    <link rel="stylesheet" th:href="@{/css/style.css}">
</head>
<body>
    <h1>Admin Page</h1>
    <table>
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Email</th>
            <th>Phone Number</th>
            <th>Aadhaar Number</th>
            <th>City</th>
        </tr>
        <tr th:each="user : ${users}">
            <td th:text="${user.id}"></td>
            <td th:text="${user.name}"></td>
            <td th:text="${user.email}"></td>
            <td th:text="${user.phoneNumber}"></td>
            <td th:text="${user.aadhaarNumber}"></td>
            <td th:text="${user.city}"></td>
        </tr>
    </table>
</body>
</html>




body {
    font-family: Arial, sans-serif;
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
}

h1 {
    color: #333;
}

form {
    margin-bottom: 20px;
}

label {
    display: inline-block;
    width: 150px;
    margin-bottom: 10px;
}

input[type="text"],
input[type="email"],
input[type="tel"] {
    width: 250px;
    padding: 5px;
}

input[type="submit"] {
    background-color: #4CAF50;
    color: white;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
}

table {
    width: 100%;
    border-collapse: collapse;
}

th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: left;
}

th {
    background-color: #f2f2f2;
}

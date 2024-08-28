Here's a formatted version of your User Service API Testing document:

---

# User Service API Testing

**Base URL**: `http://localhost:5001/api/v1/users`

## 1. Create User

### Endpoint
**POST**: `/api/v1/users`

### Test Cases

#### a) New User Creation

- **Request Body**:
    ```json
    {
        "username": "vinay12e",
        "email": "vinay123@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

- **Expected Response**:
    ```json
    {
        "id": "66cf0d427db3ad732f4a02a9",
        "username": "vinay12e",
        "email": "vinay123@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

#### b) Duplicate Username

- **Request Body**:
    ```json
    {
        "username": "vinay12",
        "email": "vinay123@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

- **Expected Response**:
    ```json
    {
        "message": "Username already exists"
    }
    ```

#### c) Duplicate Email

- **Request Body**:
    ```json
    {
        "username": "vinay123",
        "email": "vinay123@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

- **Expected Response**:
    ```json
    {
        "message": "Email already exists"
    }
    ```

## 2. Get User by Username

### Endpoint
**GET**: `/api/v1/users/{username}`

- **Example**: `GET http://localhost:5001/api/v1/users/vinay12`

### Test Cases

#### a) User Exists

- **Expected Response**:
    ```json
    {
        "id": "1",
        "username": "vinay12",
        "email": "vinay@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

#### b) User Does Not Exist

- **Expected Response**:
    ```json
    {
        "message": "User not found with username: vinay12123"
    }
    ```

## 3. Update User

### Endpoint
**PUT**: `/api/v1/users/{username}`

- **Example**: `PUT http://localhost:5001/api/v1/users/vinay123`

### Test Cases

#### a) User Exists

- **Request Body**:
    ```json
    {
        "username": "vinay7032",
        "email": "vinay123@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

- **Expected Response**:
    ```json
    {
        "id": "1",
        "username": "vinay7032",
        "email": "vinay123@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

#### b) User Does Not Exist

- **Request Body**:
    ```json
    {
        "username": "vinay7032",
        "email": "vinay123@gmail.com",
        "password": "vinay@12345",
        "country": "India",
        "state": "AP"
    }
    ```

- **Expected Response**:
    ```json
    {
        "message": "User not found with username: vinay12123"
    }
    ```

## 4. Update Password

### Endpoint
**PUT**: `/api/v1/users/{username}/password`

- **Example**: `PUT http://localhost:5001/api/v1/users/vinay123/password`

### Test Cases

#### a) User Exists

- **Request Body**:
    ```json
    {
        "password": "Vinay@1234"
    }
    ```

- **Expected Response**: No response expected.

#### b) User Does Not Exist

- **Request Body**:
    ```json
    {
        "password": "Vinay@1234"
    }
    ```

- **Expected Response**:
    ```json
    {
        "message": "User not found with username: vinay123"
    }
    ```

## 5. Delete User

### Endpoint
**DELETE**: `/api/v1/users/{username}/`

- **Example**: `DELETE http://localhost:5001/api/v1/users/vinay123/`

### Test Cases

#### a) User Exists

- **Request Body**: No request body.

- **Expected Response**: No response expected.

#### b) User Does Not Exist

- **Request Body**: No request body.

- **Expected Response**:
    ```json
    {
        "message": "User not found with username: vinay123"
    }
    ```

--- 

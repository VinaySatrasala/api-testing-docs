Here is a formatted API testing document for the `CalcController` that follows the same structure as your `User Service API Testing` document:

---

# Calculation Service API Testing

**Base URL**: `http://localhost:5001/api/v1/calculate`

## 1. Calculate Electricity Emissions

### Endpoint
**POST**: `/api/v1/calculate/electricity`

### Test Cases

#### a) Calculate Emissions from Electricity Usage

- **Request Body**:
    ```json
    {
        "kwh_used": 350
    }
    ```

- **Expected Response**:
    ```json
    {
        "kwh_used": 350,
        "emission": 322.0
    }
    ```

## 2. Calculate Water Emissions

### Endpoint
**POST**: `/api/v1/calculate/water`

### Test Cases

#### a) Calculate Emissions from Water Usage

- **Request Body**:
    ```json
    {
        "litres_used": 500
    }
    ```

- **Expected Response**:
    ```json
    {
        "litres_used": 500,
        "emission": 0.15
    }
    ```

## 3. Calculate Waste Emissions

### Endpoint
**POST**: `/api/v1/calculate/waste`

### Test Cases

#### a) Calculate Emissions from Waste

- **Request Body**:
    ```json
    {
        "recyclable_waste": 10,
        "non_recyclable_waste": 5
    }
    ```

- **Expected Response**:
    ```json
    {
        "recyclable_waste": 10,
        "non_recyclable_waste": 5,
        "emission": 2.6
    }
    ```

## 4. Calculate Fuel Emissions

### Endpoint
**POST**: `/api/v1/calculate/fuel`

### Test Cases

#### a) Calculate Emissions from Fuel Sources

- **Request Body**:
    ```json
    {
        "lpg": 15,
        "firewood": 25
    }
    ```

- **Expected Response**:
    ```json
    {
        "lpg": 15,
        "firewood": 25,
        "emission": 104.7
    }
    ```

## 5. Calculate Dietary Emissions

### Endpoint
**POST**: `/api/v1/calculate/diet`

### Test Cases

#### a) Calculate Emissions from Dietary Habits

- **Request Body**:
    ```json
    {
        "meat_consumption": 5,
        "dairy_cosumption": 3,
        "other_consumpotion": 10
    }
    ```

- **Expected Response**:
    ```json
    {
        "meat_consumption": 5,
        "dairy_cosumption": 3,
        "other_consumpotion": 10,
        "emission": 151.0
    }
    ```

## 6. Calculate Public Transport Emissions

### Endpoint
**POST**: `/api/v1/calculate/public_transport`

### Test Cases

#### a) Calculate Emissions from Public Transport (Bus and Train)

- **Request Body**:
    ```json
    {
        "bus": 100,
        "train": 200
    }
    ```

- **Expected Response**:
    ```json
    {
        "bus_km": 100,
        "train_km": 200,
        "emission": 26.9
    }
    ```

#### b) Calculate Emissions from Flight

- **Request Body**:
    ```json
    {
        "flight": {
            "from": "sfo",
            "to": "yyz"
        }
    }
    ```

- **Expected Response**:
    ```json
    {
        "flight_km": [Calculated Distance],
        "emission": [Calculated Emission]
    }
    ```

## 7. Calculate Private Transport Emissions

### Endpoint
**POST**: `/api/v1/calculate/private_transport`

### Test Cases

#### a) Calculate Emissions from Private Transport (Petrol)

- **Request Body**:
    ```json
    {
        "fuel_type": "Petrol",
        "efficiency": 12.0,
        "travelled": 150
    }
    ```

- **Expected Response**:
    ```json
    {
        "distance": 150,
        "emission": 28.875
    }
    ```

#### b) Calculate Emissions from Private Transport (Diesel)

- **Request Body**:
    ```json
    {
        "fuel_type": "Diesel",
        "efficiency": 10.0,
        "travelled": 200
    }
    ```

- **Expected Response**:
    ```json
    {
        "distance": 200,
        "emission": 53.6
    }
    ```

#### c) Calculate Emissions from Private Transport (Natural Gas)

- **Request Body**:
    ```json
    {
        "fuel_type": "Natural Gas",
        "efficiency": 8.0,
        "travelled": 100
    }
    ```

- **Expected Response**:
    ```json
    {
        "distance": 100,
        "emission": 24.125
    }
    ```

---

This document provides a structured approach to testing the `CalcController` API for the Calculation Service, detailing the endpoints, request bodies, and expected responses for different scenarios. This should make it easier to ensure that each component of the service works as expected.
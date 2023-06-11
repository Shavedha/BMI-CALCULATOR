# EXPERIMENT 8 - Create a BMI calculator using React
## AIM
To create a BMI calculator using React
## ALGORITHM
1. Create a functional component named BMICalculator using React's useState hook to manage the weight, height, and BMI state variables.
2. Implement a calculateBMI function that calculates the BMI value based on the provided weight and height inputs and updates the BMI state using setBMI.
3. Render a box-shaped container with a heading, weight and height input fields, a button to trigger the BMI calculation, and display the calculated BMI value.
4. Utilize the useState hook to bind the input values to the weight and height state variables and update them using setWeight and setHeight respectively.
5. Display the calculated BMI value using the bmi state variable when it is available.
## PROGRAM:
### App.js
```
import React, { useState } from 'react';
import './App.css'

function BMICalculator() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBMI] = useState(null);

  const calculateBMI = () => {
    const heightInMeters = height / 100;
    const bmiValue = weight / (heightInMeters * heightInMeters);
    setBMI(bmiValue.toFixed(2));
  };

  return (
    
        <div className='box'>
          <h2>BMI CALCULATOR</h2>
          <div>
            <label htmlFor="weight">Weight (kg):</label>
            <input
              type="text"
              id="weight"
              value={weight}
              onChange={(e) => setWeight(e.target.value)}
            />
          </div>
          <div>
            <label htmlFor="height">Height (cm):</label>
            <input
              type="text"
              id="height"
              value={height}
              onChange={(e) => setHeight(e.target.value)}
            />
          </div>
          <button onClick={calculateBMI}>Calculate BMI</button>
          {bmi && <p>Your BMI is: {bmi}</p>}
      </div>
    
  );
}

export default BMICalculator;
```
### App.css
```
body{
  background-color: black;
}
.box
{
  text-align: center;
  background-color: rgb(220, 122, 18);
  margin:100px;
  padding:10px;
  height: 250px;
}
label{
  font-size: larger;
}
```
## OUTPUT
<img width="960" alt="image" src="https://github.com/Shavedha/BMI-CALCULATOR/assets/93427376/41c02a55-271b-46b0-a994-0e6ecc05578e">

## RESULT
Thus a BMI calculator using React is created and implemented.

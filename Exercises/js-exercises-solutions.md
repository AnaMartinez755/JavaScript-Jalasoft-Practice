# JavaScript Exercise Solutions

In this file, I will attach each exercise solution with its number as a reference. _Fell free to comment or send me a message if you think something is wrong or missing._

## JavaScript Exercise Solutions List

**1-** Write a JavaScript program to find the area of a triangle where three sides are 5, 6, 7.

```js
function findTrianguleAreaKnowingSides(sideA, sideB, sideC) {
  // The following formula I search on internet.
  const semiPerimeter = (sideA + sideB + sideC) / 2;

  const trainguleArea = Math.sqrt(
    semiPerimeter *
      (semiPerimeter - sideA) *
      (semiPerimeter - sideB) *
      (semiPerimeter - sideC)
  );

  return trainguleArea;
}

// Testing:
const sideA = 5,
  sideB = 6,
  sideC = 7;

console.log(
  "The area of the triangule which sides are:",
  sideA,
  sideB,
  sideC,
  "is:",
  findTrianguleAreaKnowingSides(sideA, sideB, sideC).toFixed(3)
); // -> 14.697
```

**2-** Write a JavaScript program to find out if 1st January will be a Sunday between 2014 and 2050.

```js
const startingYear = 2014,
  endYear = 2050;
const workingDate = new Date(2000, 0, 1);
const daysOfWeek = [
  "Sunday",
  "Monday",
  "Tuesday",
  "Wednesday",
  "Thursday",
  "Friday",
  "Saturday",
];

// Testing:
for (let year = startingYear; year <= endYear; year++) {
  workingDate.setFullYear(year);
  if (daysOfWeek[workingDate.getDay()] === "Sunday") {
    console.log(year, "January 1st stars Sunday");
  }
}
```

**3-** Write a JavaScript program to convert temperatures to and from Celsius, Fahrenheit.

```js
function fromCelciusToFahrenheit(celciusTemp) {
  const fahrenheitTemp = (celciusTemp / 5) * 9 + 32;
  return fahrenheitTemp;
}

function fromFahrenheitToCelcius(fahrenheitTemp) {
  const celciusTemp = (((fahrenheitTemp - 32) / 9) * 5).toFixed(2);
  return celciusTemp;
}

// Testing:
console.log("70 in fahrenheit is", fromFahrenheitToCelcius(70), "in celcius"); // ->
console.log("30 in celcius is", fromCelciusToFahrenheit(30), "in fahrenheit"); // ->
```

**4-** Write a JavaScript program to create a new string from a given string by changing the position of the first and last characters. The string length must be broader than or equal to 1.

```js
function createNewStringFromString(olderString) {
  if (typeof olderString != "string" && olderString.length < 1) {
    return "ERROR.";
  }

  const newString =
    olderString[olderString.length - 1] +
    olderString.substring(1, olderString.length - 1) +
    olderString[0];

  return newString;
}

// Testing:
const testingWord = "Home";
console.log(createNewStringFromString(testingWord)); // -> 'eomH'
```

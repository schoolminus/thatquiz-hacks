# Bookmarklet:

``javascript:(function()%7Bfunction solveEquation() %7B%0A  %2F%2F Prompt the user for the number of milliseconds per problem%0A  const millisecondsPerProblem %3D parseInt(prompt("How many milliseconds per problem%3F"%2C 5))%3B%0A%0A  if (isNaN(millisecondsPerProblem)) %7B%0A    alert("Invalid input. Using default value of 5 milliseconds.")%3B%0A  %7D%0A%0A  %2F%2F Get the equation elements%0A  const equationElement %3D document.querySelector('td.qq.nw.q8s')%3B%0A  if (!equationElement) %7B%0A    alert("No equation found. Stopping.")%3B%0A    return%3B%0A  %7D%0A%0A  %2F%2F Extract the equation text%0A  const equationText %3D equationElement.innerText.trim()%3B%0A  const equationParts %3D equationText.split(' ')%3B%0A  const number1 %3D parseInt(equationParts%5B0%5D)%3B%0A  const number2 %3D parseInt(equationParts%5B2%5D)%3B%0A  const operation %3D equationParts%5B1%5D%3B%0A%0A  %2F%2F Calculate the result%0A  let result%3B%0A  switch (operation) %7B%0A    case '%2B'%3A%0A      result %3D number1 %2B number2%3B%0A      break%3B%0A    case '–'%3A%0A      result %3D number1 - number2%3B%0A      break%3B%0A    case '×'%3A%0A      result %3D number1 * number2%3B%0A      break%3B%0A    case '÷'%3A%0A      result %3D number1 %2F number2%3B%0A      break%3B%0A    default%3A%0A      alert(%60Invalid operation%3A %24%7Boperation%7D%60)%3B%0A      return%3B%0A  %7D%0A%0A  %2F%2F Input the result%0A  const inputElement %3D document.querySelector('input.Mh')%3B%0A  if (!inputElement) %7B%0A    alert("No input found. Stopping.")%3B%0A    return%3B%0A  %7D%0A  inputElement.value %3D result.toString()%3B%0A%0A  %2F%2F Click the "OK" button%0A  const okButton %3D document.querySelector('button.u82')%3B%0A  if (!okButton) %7B%0A    alert("No OK button found. Stopping.")%3B%0A    return%3B%0A  %7D%0A%0A  %2F%2F Call the function again for the next equation with the specified delay%0A  setTimeout(solveEquation%2C millisecondsPerProblem)%3B%0A%7D%0A%0A%2F%2F Start solving equations%0AsolveEquation()%3B%7D)()%3B``

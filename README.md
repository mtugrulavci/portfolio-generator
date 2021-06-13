# portfolio-generator
  
We start by asking the user for their information with Inquirer prompts; this returns all of the data as an object in a Promise.

The promptProject() function captures the returning data from promptUser() and we recursively call promptProject() for as many projects as the user wants to add. Each project will be pushed into a projects array in the collection of portfolio information, and when we're done, the final set of data is returned to the next .then().

The finished portfolio data object is returned as portfolioData and sent into the generatePage() function, which will return the finished HTML template code into pageHTML.

We pass pageHTML into the newly created writeFile() function, which returns a Promise. This is why we use return here, so the Promise is returned into the next .then() method.

Upon a successful file creation, we take the writeFileResponse object provided by the writeFile() function's resolve() execution to log it, and then we return copyFile().

The Promise returned by copyFile() then lets us know if the CSS file was copied correctly, and if so, we're all done!




# NP HTML5, CSS3, and JavaScript 6e Tutorial 13, Case Problem 2
1.  Use your editor to open the dl_expenses_txt.html and dl_expenses_txt.js files from the html13 > case2 folder. Enter your name and the date in the comment section of each file, and save them as dl_expenses.html and dl_expenses.js respectively.
2.  Go to the dl_expenses.html file in your editor. Add a script element for the dl_expenses.js file. Load the file asynchronously.
3.  Scroll down to the empInfo table and add pattern attributes to the following fields using regular expressions (Note: Regular expressions in the HTML pattern attribute do not include the opening and closing / character):
    a.  The accID field should consist only of the letters "ACT" followed by exactly 6 digits.
    b.  The deptID field should consist only of the letters "DEPT" followed by 4 to 6 digits.
    c.  The projID field should consist only of the letters "PROJ" followed by a dash and then two lowercase letters followed by another dash and 3 digits.
    d.  The ssn field should consist only of 3 digits followed by a dash followed by 2 more digits followed by a dash, ending with 4 more digits.
4.  Take some time to study the class names for the input elements in the travelExp table. This table will be used to calculate the total travel expenses for each day and across all categories. Note that input elements that contribute to the total are placed in the sum class. Input elements belonging to a common date are placed in the dateO through date5 classes. Finally, input elements belonging to different expense categories are placed in the trans, lodge, meal, and other classes. Save your changes to the file.
5.  Return to the dl_expenses.js file in your editor. Directly below the initial comment section, add an event listener for the load event. Apply an anonymous function to the load event that does the following:
    a.  Declares a variable named changingCells that matches all input elements in the travelExp
    table that belong to the sum class.
    b.  For every item in the changingCells collection, adds an onchange event handler that runs
    calcExp() function.
    c.  For the button with the ID "submitButton", adds an event handler for the click event that runs the validateSummary() function when the button is clicked.
6.  Kay wants a customized validation message if employees neglect to fill out the summary field that provides a summary of the travel expenses. Create the validateSummary() function that dis¬plays the message "You must include a summary of the trip in your report." if the validation state of the summary field value is missing; otherwise set the custom validation message to an empty text string.
7.  Create the calcClass() function with a single parameter sumClass. The purpose of this function is to sum the values of input elements belonging to the sumClass class of elements. Add the follow¬ing commands to the function:
    a.  Create a variable named sumFields containing the object collection of all elements belonging
    to the sumClass class.
    b.  Create a variable named sumtotal that will be used to keep a running total of the total values
    in the input elements in the sumFields object collection. Set the initial value of sumTotal to 0.
    c.  Loop through the items in the sumFields object collection. For each item, declare a variable named itemValue equal to the numeric value of the current input element in the sumFields array. (Hint: Use the parseFloat() function to extract the numeric value.) If itemValue is a numeric value, add it to itemValue. (Hint: Use the isNaN() function to determine whether itemValue is or is not a number.)
    d.  After the for loop, return the value of sumTotal.
8.  Create the calcExp() function. The purpose of this function is to calculate the row and column totals from the travelExp table. Add the following commands to the function:
    a.  Create the exptable variable referencing all the table row (tr) elements within the table body of the travelExp table.
    b.  Loop through the rows in the expTable collection and, for each table row, set the value of the input element with the ID subtotal/nc/ex to the value returned by the calcClass() function using the parameter value date/nc/ex. Where /nc/ex is the value of the index counter in the for loop. Format the value returned by the calcClass() function as a text string using the formatNumber() function to 2 decimals.
    c.  After the for loop, set the values of the transTotal, lodgeTotal, mealTotal, and otherTotal input elements by calling the calcClass() function using parameter values "trans", "lodge", "meal", and "other". Format the values using the formatNumber() to 2 decimal places.
    d.  Set the value of the expTotal input element to the value returned by the calcClass() function using "sum" as the parameter value. Format the returned value using the formatUSCurrency() function.
9.  Document your work with comments through the newly added code.
10. Save your changes to the file and load dl_expenses.html in your browser. Verify the following:
    a.  You cannot submit the form without adding a travel summary, a name, a social security number, and account, department, and project IDs in the correct format.
    b.  If you fail to enter a travel summary, the customized message, "You must include a summary of the trip in your report." is displayed.
    c.  When you enter or change values in the expense report table, the column and row totals are automatically updated and the column and row totals are formatted to 2 decimals places with a thousands separator. The overall travel expense total should be shown in currency format. (Note: At the time of this writing, Firefox does not support the date data type, so you will not see the mm/dd/yyyy value in the travel date column.)

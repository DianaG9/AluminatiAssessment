Hi team! 

Changes I made to the code: 

-Delete "console.log('divisor', num)" since no console log is needed

-Changed for(var i = 0; i < limit; i++) to (let i = 1; i <= limit.value; i++)  since no number can be divided by 0 nor 0 can be divided by any number, using let instead of var and changing "<limit" to "<=limit" so it takes the limit as a value as well.

-Changed numbers = [...numbers, i]; to numbers.push(i); for good practices

-Changed the function "hov" to "Hover" and the function "n" to "RandomNumbers" so it's more understandable for someone reading the code and also capitalized

-Added ref from Vue to be able to have reactive variables

-Changed the const limit to a ref variable

-moved the styles to the style.css file

-Changed the active style from red to a gradient green, more user-friendly

-Added styles to the numbers class
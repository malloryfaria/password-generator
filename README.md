# Password Generator

This project is a JavaScript learning experience for module 3 in the UofT coding bootcamp.

## Build status

Live

## Deployed application
https://malloryfaria.github.io/password-generator/
 
## Screenshots

![the generator](/assets/images/generator.jpg?raw=true "the generator")

## Tech/framework used

<b>Built with</b>
- HTML
- JavaScript
- CSS

## Features
Semantic tags

## Code Example

```
// WHEN I click the button to generate a password
function generatePassword() {
    var password = "";
    var passwordCharset = "";

    // THEN I am presented with a series of prompts for password criteria WHEN prompted for password criteria
    // THEN I select which criteria to include in the password WHEN prompted for the length of the password
    // THEN I choose a length of at least 8 characters and no more than 128 characters
      var passwordLength = window.prompt("How many characters would you like your password to be?");
        if(
          passwordLength >128 ||  passwordLength <8 || isNaN(passwordLength)) {
          window.alert("Your password is not a valid length. Please enter a number between 8 and 128.");
          return;
        }
    
    // WHEN prompted for character types to include in the password THEN I choose lowercase, uppercase, numeric, and/or special characters
    // WHEN I answer each prompt THEN my input should be validated and at least one character type should be selected

            var characterSetChoice1 = window.confirm("Would you like to include lowercase letters?");
            console.log(characterSetChoice1);
            if(characterSetChoice1) {
              passwordCharset += lowerCaseCharacters;
            }
            console.log(passwordCharset);
      
            var characterSetChoice2 = window.confirm("Would you like to include uppercase letters?");
            console.log(characterSetChoice2);
            if(characterSetChoice2) {
              passwordCharset += upperCaseCharacters;
            }
            console.log(passwordCharset);
      
            var characterSetChoice3 = window.confirm("Would you like to include numerical characters?");
            console.log(characterSetChoice3);
            if(characterSetChoice3) {
              passwordCharset += numericCharacters;
            }
            console.log(passwordCharset);
      
            var characterSetChoice4 = window.confirm("Would you like to include special characters?");
            console.log(characterSetChoice4);
            if(characterSetChoice4) {
              passwordCharset += specialCharacters;
            }
            console.log(passwordCharset);

          // Checks if user selected any of the options
    
            if (passwordCharset === "") {
              window.alert("You must choose at least one option of character types to include!");
            }

          // WHEN all prompts are answered and user chose at least 1 that was TRUE, THEN a password is generated that matches the selected criteria

            if(passwordLength >=8 && passwordLength <=128) {
              for(var i = 0; i < passwordLength; i++) {
                password += passwordCharset.charAt(Math.floor(Math.random() * passwordCharset.length));
              };
              
              // place this generated password in the local storage
              localStorage.setItem("password", password);
              var password = localStorage.getItem("password");
              console.log(password);
              return password;
            };
};
```


## License
None

© [Mallory](https://github.com/malloryfaria)


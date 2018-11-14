# iPhone Calculator made with jQuery

## The following project was completed in collaboration with [Jack Li](https://github.com/lijaack)

### Overview

We employed HTML, CSS, JavaScript, and jQuery to make a calculator that looks like the native app on iPhone. This application uses jQuery logic to pull number values from the calculator buttons, push them to a string, then use the eval() function to do the calculation.


 Game Logic:

 ``` javascript
$(document).ready(function () {
    var btnClickedArray = [];
    var result;

    $(".btn").on("click", function () {
    var btnClicked = $(this).val();
    if (btnClicked != "=" && btnClicked != "clear") {
        $(btnClickedArray.push(btnClicked));
        var equation = btnClickedArray.join("");
        $("#result").text(equation);
    }
    if (btnClicked === "=") {
        for(i = 0; i < btnClickedArray.length; i++){
        if (btnClickedArray[i]==="^"){
            btnClickedArray[i]="**";
        }
        }
        calculation = btnClickedArray.join("");
        var result = eval(calculation);
        $("#result").text(result);
        clearMe();
    });
    $("#button-clear").on("click", function () {
    $("#result").empty();
    clearMe();
    });
    function clearMe() {
    btnClickedArray = [];
    };
});
 ```
### Feel free to play around with the calculator by clicking the numbers and operators!

[Link to the deployed calculator](https://jacksonsabol.github.io/jQuery-Calculator/)

Thank you for reading!

### Built With:
* HTML
* CSS
* JavaScript
* jQuery Library
* Bootstrap CSS Library


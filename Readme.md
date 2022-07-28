//----------------Reverse string------------------------------

 function reverseStr(str){
    return str.split("").reverse().join("");
 }

 reverseStr("Ankit")//----------------Reverse string------------------------------

function reverseStr(str){
    return str.split("").reverse().join("");
 }

 console.log(reverseStr("Ankit"))


 // -----------------reverse string using forLoop------------------

 function reverseStrForLoop(str){
    let reversedStr = "";
    for(var i = str.length-1; i >= 0; i--){
        reversedStr += str[i]
    }

    return reversedStr
 }

 console.log(reverseStrForLoop("ANKIT"))


 //---------reverse sentence---------------

 function reverseSentence(sen){
    const arr = sen.split(" ");
    const reversed = arr.map(el => {
        return el.split('').reverse().join("");
     });
     return reversed.join(" ");

 }

 console.log(reverseSentence("My Name is Ankit"))


 //------call---bind ----apply------------

 var employee1 = { firstName: "John", lastName: "Rodson" };
var employee2 = { firstName: "Jimmy", lastName: "Baily" };

function invite(greeting1, greeting2) {
  console.log(
    greeting1 + " " + this.firstName + " " + this.lastName + ", " + greeting2
  );
}

invite.call(employee1, "Hello", "How are you?"); // Hello John Rodson, How are you?
invite.call(employee2, "Hello", "How are you?"); // Hello Jimmy Baily, How are you?

invite.apply(employee1, ["Hello", "How are you?"]); // Hello John Rodson, How are you?
invite.apply(employee2, ["Hello", "How are you?"]); // Hello Jimmy Baily, How are you?

var inviteEmployee1 = invite.bind(employee1);
var inviteEmployee2 = invite.bind(employee2);
inviteEmployee1("Hello", "How are you?"); // Hello John Rodson, How are you?
inviteEmployee2("Hello", "How are you?"); // Hello Jimmy Baily, How are you?''


//------------closure--------------
function Welcome(name) {
    var greetingInfo = function (message) {
      console.log(message + " " + name);
    };
    return greetingInfo;
  }
  var myFunction = Welcome("John");
  myFunction("Welcome "); //Output: Welcome John
  myFunction("Hello Mr."); //output: Hello Mr.John


  //----------IIFE------Imediately invoked fn----------
  (function () {
    var message = "IIFE";
    console.log(message);
  })();


  //--------------currying function---------------
  const multiArgFunction = (a, b, c) => a + b + c;
console.log(multiArgFunction(1, 2, 3)); // 6

const curryUnaryFunction = (a) => (b) => (c) => a + b + c;
curryUnaryFunction(1); // returns a function: b => c =>  1 + b + c
curryUnaryFunction(1)(2); // returns a function: c => 3 + c
curryUnaryFunction(1)(2)(3); // returns the number 6







//------------Higher order function-------------
const firstOrderFunc = () =>
  console.log("Hello, I am a First order function");
const higherOrder = (ReturnFirstOrderFunc) => ReturnFirstOrderFunc();
higherOrder(firstOrderFunc);


//-----------Substr--------------------

function subStr(str){
  return str.substr(1 , 4)
}

console.log(subStr("Ankit")) //nkit (Removes the letter on 1)


function SubStr(str){
  return str.substr(2)
}

console.log(SubStr("Ankit")); // kit (Removes letter before 2)


//-----------------Slice-----------------
let arr = [1, 2, 3, 4, 5]
console.log(arr.slice(1,3)) // [2,3] It picked first element on 1 and 3rd is the optional argument, It exclude last element when 2 arguments
console.log(arr.slice(2)) // [3,4,5] It picked from 2 and print till end, & if index is not found in arr then show []
console.log(arr) // [1,2,3,4,5] //Doesn't affect the arr

//=----------------splice=----------------------

console.log(arr.splice(1,3)) // [2,3,4] It return the first argument till last position 3.
console.log(arr) //[1,5 ] It modifies the arr
let newArr = [1,2,3,4,5]
console.log(newArr.splice(3)) // [4, 5] It returned 3 element placed till last


//-----------callback function----------------
function callBackFn(name){
  console.log("Hello " + name)
}

function outerFn(callback){
  let name = "Ankit"
  // let name = prompt("Please enter your name.");

  callback(name)
}

outerFn(callBackFn) // return Hello Ankit , It passed function in another function as a argument



//--------------------HTML---------------------
<!DOCTYPE html>
<head>
    <style>
        body * {
          margin: 10px;
          border: 1px solid blue;
        }
      </style>
</head>
<body>
    <form onclick="alert('form')">FORM
        <div onclick="alert('div')">DIV
          <p onclick="alert('p')">P</p>
          <button onclick="event.stopPropagation()">Click me</button>

        </div>
      </form>
       <!--  Event bubbling is -> when we click on p it triggers click of p then div then form automatically- ,        When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.

        If we use event.stopPropagation() then it doesnt't work for parent -->

        <a href="JavaScript:void(0);" onclick="alert('Well done!')">
            Click Me!
          </a> <!---------void(0) prvent the page from refreshing-->


</body>
let myImage = document.querySelector('img');

myImage.onclick = function() {
    let mySrc = myImage.getAttribute('src');
    if(mySrc === 'images/sun-flower.png') {
      myImage.setAttribute('src', 'images/wave.jpg');
    } else {
      myImage.setAttribute('src', 'images/sun-flower.png');
    }
}

let myButton = document.querySelector('button');
let myHeading = document.querySelector('h1');

function setUserName() {
  let myName = prompt('请输入你的名字。');
  if(!myName || myName === null) {
    setUserName();
  } else {
  localStorage.setItem('name', myName);
  myHeading.textContent = 'I Miss U，' + myName;
}
}
myButton.onclick = function() {
   setUserName();
}
if(!localStorage.getItem('name')) {
  setUserName();
} else {
  let storedName = localStorage.getItem('name');
  myHeading.textContent = 'I Miss U，' + storedName;
}

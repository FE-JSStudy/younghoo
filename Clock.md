# 02 JS and CSS Clock



### 1. CSS 

``transform-origin``  : 원점의 위치를 지정하는 속성

``transform``  : 움직임을 나타내는 속성 - ex) rotate()

``transition`` : 움직임이는 방법(?)을 정의

``transition-timing-function`` : 어떻게 움직이는지 나타내는 속성 - ex) ease-in-out, cubic-bezier()



### 2. JS

```javascript
const now = new Date();
# 현재 시간을 'now'라는 변수에 저장

const seconds = now.getSeconds();
# 'now'의 getSeconds() 메서드를 통해 현재 시간의 '초'를 seconds라는 변수에 저장

const secondsDegrees = (seconds / 60) * 360 + 90;
# seconds 변수('초')의 위치를 각도로 나타냄
# '+ 90'은 css의 'transform: rotate(90deg)'로 설정했기 때문에 더해줌

secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
# 위에 코드로 구한 초침의 각도를 css 속성의 transform의 rotate에 지정한 각도와 계산

+ min과 hour는 초와 동일
```



### 💥 초침이 다 돌고 빠르게 다시 도는 것을 고치기 위해서는?

```javascript
const now = new Date();
let seconds = now.getSeconds();

function setDate() {
    
    seconds++ ;
    const secondsDegrees = (seconds / 60) * 360 + 90;
    const secondHand = document.querySelector('.second-hand');
    secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
    
    ...
}
```






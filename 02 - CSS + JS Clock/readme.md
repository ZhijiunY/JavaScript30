CSS + JS Clock
===

![image](./index.png)
這是一個利用 HTML, CSS 和 JavaScript 實現的網頁時鐘。
這個時鐘顯示當前時間，並且每秒更新一次。它使用了 CSS 來實現時鐘指針的動畫效果。

```css
.hand {
    transform-origin: 100%;
    transform: rotate(90deg);
    transition: all 0.05s;
}
```

1. 獲取指針元素
```javascript
const secondHand = document.querySelector('.second-hand');
const minsHand = document.querySelector('.min-hand');
const hourHand = document.querySelector('.hour-hand');
```
2. 設置時間的函數
```javascript
function setDate() {
  const now = new Date();
}
```
3. 計算秒針角度
```javascript
  const seconds = now.getSeconds();
  const secondsDegrees = ((seconds / 60) * 360) + 90;
  secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
```
4. 計算分針角度
```javascript
  const mins = now.getMinutes();
  const minsDegrees = ((mins / 60) * 360) + ((seconds/60)*6) + 90;
  minsHand.style.transform = `rotate(${minsDegrees}deg)`;
```
5. 計算時針角度
```javascript
  const hour = now.getHours();
  const hourDegrees = ((hour / 12) * 360) + ((mins/60)*30) + 90;
  hourHand.style.transform = `rotate(${hourDegrees}deg)`;
```

6. 每秒更新時間
```javascript
setInterval(setDate, 1000);
setDate();
```
index.html initial page speed: mobile 27; desktop 90

Steps to Optimize index.html:

1) async the google analytics script | speed: mobile 28; desktop 91

2) use the media = print condition for print.css | speed: mobile 28; desktop 90

3) Download image files from internet and add them to local image directory | speed: mobile 27; desktop 91

4) Create smaller pizzaria file pizzaria2 | speed: mobile 74; desktop 87

5) Inline style.css | speed: mobile 75; desktop 87

6) Remove web font (save a web call) | mobile: 87; desktop 90

7) Lossely Compress pizzaria2 and profilePic images | mobile 93; desktop 95




main.js 60 framerate challenge:

1) Move var pizzasDiv = document.getElementById("randomPizzas") outside of loop. It doesn't change; don't need to get it every time

2) Replace  phase = Math.sin((document.body.scrollTop / 1250) + (i % 5))  with  phase = Math.sin((scrollTop / 1250) + (i % 5)) (line: 506)
   Create var scrollTop = document.body.scrollTop outside of the for loop, it only needs to be computed once.


Resize pizza in under 5ms:

1) Refactor code in changePizzaSizes(size) function. Bring calculation of offsetWidth for the randomPizzaContainer class and the
   randomPizzas id outside of the loop. These values are consistent for each pizza, so removing them from the loop saves unnecessary
   computation.
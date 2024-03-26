# Elegant-pharaoh
Let's swim

![buh](https://github.com/nicolasbaez/Elegant-pharaoh/blob/main/xp031.gif)
![buh](https://github.com/nicolasbaez/Elegant-pharaoh/blob/main/xp031_1.gif)
![buh](https://github.com/nicolasbaez/Elegant-pharaoh/blob/main/xp031_2.gif)
![buh](https://github.com/nicolasbaez/Elegant-pharaoh/blob/main/xp031_3.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  h = w / 2;
  clear();
  rotateY(PI / 2);
  stroke(h);
  for (i = 0; i <= 3; i += map(sin(w), -1, 1, 0.1, 0.05)) {
    fill(0, h, (i * h) / PI);
    beginShape();
    for (j = 0; j < 7; j += 1) {
      r = noise(i, j) * h;
      curveVertex(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
    endShape();
  }
  w += 0.01;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp031.gif", 628, { delay: 0, units: "frames" });
  }
};

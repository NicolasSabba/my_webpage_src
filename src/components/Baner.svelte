<script>
  // Load canvas
  import P5Canvas from "./P5js.svelte";
  // Setup canvas script
  let sketch1 = function (p5) {
    // Get view size
    let WIDTH = window.innerWidth;
    let HEIGHT = window.innerHeight;
    // Calculate col and rows
    let cols = Math.ceil(WIDTH / 40);
    let rows = Math.ceil(HEIGHT / 45) + 1;
    // Create rows
    let lines = [];
    for (let y = 0; y < rows; y++) {
      lines.push([]);
    }
    let time = 0;
    let index = 0;
    // Load function
    p5.setup = function () {
      // Create canvas
      p5.createCanvas(WIDTH, HEIGHT);
      // Draw variables
      p5.strokeWeight(10);
      p5.stroke(195, 86, 56);
    };
    // Draw function
    p5.draw = function () {
      time += p5.deltaTime;
      // Push a new line
      while (time > 10) {
        time -= 10;
        if (lines[index].length < cols) {
          lines[index].push(p5.random());
        } else if (index + 1 < rows) {
          index += 1;
          lines[index].push(p5.random());
        } else {
          lines.shift();
          lines.push([]);
          lines[index].push(p5.random());
        }
      }
      // Draw lines
      p5.background(82, 80, 87);
      for (let y = 0; y < lines.length; y++) {
        for (let x = 0; x < lines[y].length; x++) {
          if (lines[y][x] > 0.5) {
            p5.line(0 + (40 * x), 0 + (45 * y), 40 + (40 * x), 45 + (45 * y))
          } else {
            p5.line(0 + (40 * x), 45 + (45 * y), 40 + (40 * x), 0 + (45 * y))
          }
        }
      }
    };
  };
</script>

<style>
  main {
    padding: 0px;
    margin: 0px;
    overflow: hidden;
  }
</style>

<main>
  <P5Canvas id="p5canvas1" sketch={sketch1} />
</main>

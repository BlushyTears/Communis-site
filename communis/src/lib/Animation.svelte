<!-- Copy pasted from chatgpt ayy lmao -->

<script lang="ts">
  import { onMount } from "svelte";

  let canvas, ctx;
  const particles = [];

  const PARTICLE_COUNT = 200;
  const MAX_PARTICLE_VELOCITY = 2;

  function Particle() {
    this.x = Math.random() * canvas.width;
    this.y = Math.random() * canvas.height;
    this.vx = (Math.random() - 0.5) * MAX_PARTICLE_VELOCITY;
    this.vy = (Math.random() - 0.5) * MAX_PARTICLE_VELOCITY;

    
    const colorOptions = ["#003049", "#d62828", "#f77f00", "#fcbf49"]; // These color codes follow the main color theme as app.css
    this.color = colorOptions[Math.floor(Math.random() * colorOptions.length)];

    this.draw = function () {
      ctx.beginPath();
      ctx.fillStyle = this.color;
      ctx.arc(this.x, this.y, 5, 0, Math.PI * 2);
      ctx.fill();
    };

    this.update = function () {
      if (this.x < 0 || this.x > canvas.width) {
        this.vx = -this.vx;
      }
      if (this.y < 0 || this.y > canvas.height) {
        this.vy = -this.vy;
      }
      this.x += this.vx;
      this.y += this.vy;
    };
  }

  onMount(() => {
    canvas = document.querySelector("canvas");
    ctx = canvas.getContext("2d");

    for (let i = 0; i < PARTICLE_COUNT; i++) {
      particles.push(new Particle());
    }

    function animate() {
      requestAnimationFrame(animate);
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      for (let i = 0; i < particles.length; i++) {
        particles[i].update();
        particles[i].draw();
      }
    }

    animate();
  });
</script>

<canvas width="2500" height="1600" />

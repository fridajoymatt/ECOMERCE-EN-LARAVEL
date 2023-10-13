<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ECOMERCE-EN-LARAVEL</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #9CC17E;
        }

        canvas {
            position: absolute;
        }

        .card {
            background-color: #fff;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            padding: 20px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <canvas id="particles"></canvas>
    <div class="card">
        <h1 align="center">ECOMERCE-EN-LARAVEL</h1>
        <p align="center">This is an E-commerce website. I have attached project screenshots during its execution. Contact me for a demo.</p>
      <h2 align="center">Connect with me</h2>

<div align="center">
  <a href="https://github.com/fridajoymatt/" target="_blank">
    <img src="https://img.shields.io/badge/github-%2324292e.svg?&style=for-the-badge&logo=github&logoColor=white" alt="github" style="margin-bottom: 5px;" />
  </a>
  <a href="https://dev.to/fridajoymatt" target="_blank">
    <img src="https://img.shields.io/badge/dev.to-%2308090A.svg?&style=for-the-badge&logo=dev.to&logoColor=white" alt="devto" style="margin-bottom: 5px;" />
  </a>
  <a href="https://www.linkedin.com/in/firdaous-kpelafia-131485277/" target="_blank">
    <img src="https://img.shields.io/badge/linkedin-%231E77B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" alt="linkedin" style="margin-bottom: 5px;" />
  </a>
</div>
    </div>

    <script>
    // Code JavaScript pour les particules
    const canvas = document.getElementById("particles");
    const ctx = canvas.getContext("2d");

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    class Particle {
        constructor() {
            this.x = Math.random() * canvas.width;
            this.y = Math.random() * canvas.height;
            this.size = Math.random() * 5 + 1;
            this.speedX = Math.random() * 3 - 1.5;
            this.speedY = Math.random() * 3 - 1.5;
        }

        update() {
            this.x += this.speedX;
            this.y += this.speedY;

            if (this.size > 0.2) this.size -= 0.1;

            // Réinitialiser la particule lorsque sortie de la toile
            if (this.x > canvas.width || this.x < 0 || this.y > canvas.height || this.y < 0) {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 5 + 1;
                this.speedX = Math.random() * 3 - 1.5;
                this.speedY = Math.random() * 3 - 1.5;
            }
        }

        draw() {
            ctx.fillStyle = "#fff";
            ctx.strokeStyle = "#fff";
            ctx.beginPath();
            ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
            ctx.fill();
        }
    }

    const particlesArray = [];

    function createParticles() {
        for (let i = 0; i < 100; i++) {
            particlesArray.push(new Particle());
        }
    }

    function handleParticles() {
        for (let i = 0; i < particlesArray.length; i++) {
            particlesArray[i].update();
            particlesArray[i].draw();
        }
    }

    function animate() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        handleParticles();
        requestAnimationFrame(animate);
    }

    window.addEventListener("resize", function () {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    });

    createParticles();
    animate();
</script>

</body>
</html>

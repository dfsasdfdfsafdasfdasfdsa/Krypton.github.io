<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Krypton Client Download</title>
<style>
  /* Base styles */
  html, body {
    margin: 0; padding: 0;
    width: 100%; height: 100%;
    background: black;
    overflow: hidden;
    font-family: Arial, sans-serif;
    color: #e0e0e0;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    position: relative;
  }

  /* Container */
  .container {
    position: relative;
    z-index: 10;
    max-width: 500px;
    padding: 20px 30px;
    background: rgba(0,0,0,0.6);
    border-radius: 12px;
    box-shadow: 0 0 30px #00ff00aa;
  }

  h1 {
    font-size: 2.5rem;
    margin-bottom: 0.5rem;
    color: #00ff00;
    text-shadow: 0 0 10px #00ff00;
  }

  p {
    margin-bottom: 2rem;
    color: #88ffaa;
    font-size: 1.2rem;
  }

  a.btn {
    display: inline-block;
    background-color: #00c853;
    color: #121212;
    text-decoration: none;
    font-size: 1.3rem;
    padding: 15px 45px;
    border-radius: 8px;
    font-weight: bold;
    box-shadow: 0 0 15px #00ff00cc;
    transition: background-color 0.3s ease, transform 0.3s ease;
  }

  a.btn:hover {
    background-color: #00e676;
    box-shadow: 0 0 30px #00ff00ff;
    transform: scale(1.05);
  }

  footer {
    position: fixed;
    bottom: 15px;
    width: 100%;
    font-size: 0.8rem;
    color: #616161;
    z-index: 10;
  }

  /* Starfield container */
  #starfield {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    z-index: 1;
    overflow: hidden;
  }

  /* Individual stars */
  .star {
    position: absolute;
    background: white;
    border-radius: 50%;
    opacity: 0.8;
    animation-name: drift;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
  }

  /* Different sizes and speeds for stars */
  .star.small {
    width: 1px;
    height: 1px;
    animation-duration: 60s;
  }

  .star.medium {
    width: 2px;
    height: 2px;
    animation-duration: 90s;
  }

  .star.large {
    width: 3px;
    height: 3px;
    animation-duration: 120s;
  }

  /* Drift animation: moves star horizontally from right to left */
  @keyframes drift {
    from {
      transform: translateX(100vw);
    }
    to {
      transform: translateX(-10vw);
    }
  }
</style>
</head>
<body>

  <div id="starfield"></div>

  <div class="container">
    <h1>Krypton Client</h1>
    <p>Fast, secure, and free — click below to download.</p>
    <a class="btn" href="https://drive.google.com/uc?export=download&id=1IyvphzRI4MI6bNeBzXVtct4j_W5k43I5" download>
      ⬇ Download Krypton Client
    </a>
  </div>

  <footer>© 2025 Krypton</footer>

  <script>
    const starfield = document.getElementById('starfield');
    const starCounts = { small: 80, medium: 40, large: 20 };

    function createStar(sizeClass) {
      const star = document.createElement('div');
      star.classList.add('star', sizeClass);
      star.style.top = Math.random() * 100 + 'vh';
      // Start somewhere off-screen to the right randomly
      star.style.left = (Math.random() * 100 + 100) + 'vw';
      starfield.appendChild(star);
      // Remove and recreate star after animation completes (loop)
      star.addEventListener('animationiteration', () => {
        star.style.top = Math.random() * 100 + 'vh';
        star.style.left = (Math.random() * 100 + 100) + 'vw';
      });
    }

    // Create stars
    Object.entries(starCounts).forEach(([size, count]) => {
      for (let i = 0; i < count; i++) {
        createStar(size);
      }
    });
  </script>

</body>
</html>

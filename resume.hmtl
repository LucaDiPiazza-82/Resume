html

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Interactive Resume - Your Name</title>
<style>
  /* Basic Reset */
  * {
    margin: 0; padding: 0; box-sizing: border-box;
  }
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: #f4f7f6;
    color: #333;
    line-height: 1.6;
    position: relative;
  }
  header {
    background: #2a9d8f;
    color: white;
    padding: 2rem 1rem;
    text-align: center;
  }
  header h1 {
    margin-bottom: 0.3rem;
  }
  nav {
    margin-top: 1rem;
  }
  nav a {
    color: #e9c46a;
    margin: 0 1rem;
    text-decoration: none;
    font-weight: bold;
    transition: color 0.3s;
  }
  nav a:hover {
    color: #f4a261;
  }
  section {
    max-width: 800px;
    margin: 2rem auto;
    padding: 0 1rem;
  }
  h2 {
    border-bottom: 2px solid #2a9d8f;
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
  }
  /* Skill Bars */
  .skill {
    margin-bottom: 1rem;
  }
  .skill-name {
    font-weight: bold;
    margin-bottom: 0.3rem;
  }
  .skill-bar {
    background: #ddd;
    border-radius: 20px;
    overflow: hidden;
  }
  .skill-level {
    height: 20px;
    background: #2a9d8f;
    width: 0;
    border-radius: 20px;
    transition: width 1.5s ease-in-out;
  }
  /* Contact Button */
  .contact-btn {
    display: inline-block;
    background: #e76f51;
    color: white;
    padding: 0.7rem 1.5rem;
    border-radius: 25px;
    text-decoration: none;
    font-weight: bold;
    transition: background 0.3s;
    margin-top: 1rem;
  }
  .contact-btn:hover {
    background: #f4a261;
  }
  /* Smooth Scroll */
  html {
    scroll-behavior: smooth;
  }
  /* Interactive clickable word */
  .clickable {
    color: #e76f51;
    cursor: pointer;
    font-weight: bold;
    text-decoration: underline;
    position: relative; /* for positioning popup arrow */
  }
  /* Detached popup panel */
  #popup {
    position: absolute;
    max-width: 300px;
    background: white;
    box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    border-radius: 8px;
    padding: 1rem;
    opacity: 0;
    transform: scale(0.7);
    transform-origin: top center;
    transition: opacity 0.3s ease, transform 0.3s ease;
    pointer-events: none;
    z-index: 1000;
  }
  #popup.show {
    opacity: 1;
    transform: scale(1);
    pointer-events: auto;
  }
  /* Popup arrow */
  #popup::before {
    content: "";
    position: absolute;
    top: -10px;
    left: 50%;
    transform: translateX(-50%);
    border-left: 10px solid transparent;
    border-right: 10px solid transparent;
    border-bottom: 10px solid white;
  }
</style>
</head>
<body>

<header>
  <h1>Your Name</h1>
  <p>Web Developer | Designer | Problem Solver</p>
  <nav>
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#experience">Experience</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section id="about">
  <h2>About Me</h2>
  <p>Passionate web developer with 3+ years of experience creating responsive and accessible websites. Skilled in HTML, CSS, JavaScript, and modern frameworks.</p>
</section>

<section id="skills">
  <h2>Skills</h2>
  <div class="skill">
    <div class="skill-name">HTML & CSS</div>
    <div class="skill-bar"><div class="skill-level" data-level="90%"></div></div>
  </div>
  <div class="skill">
    <div class="skill-name">JavaScript</div>
    <div class="skill-bar"><div class="skill-level" data-level="75%"></div></div>
  </div>
  <div class="skill">
    <div class="skill-name">React</div>
    <div class="skill-bar"><div class="skill-level" data-level="60%"></div></div>
  </div>
  <div class="skill">
    <div class="skill-name">Node.js</div>
    <div class="skill-bar"><div class="skill-level" data-level="50%"></div></div>
  </div>
</section>

<section id="experience">
  <h2>Experience</h2>
  <h3>Frontend Developer - GreenTech Solutions</h3>
  <p><em>Jan 2023 – Present</em></p>
  <ul>
    <li>Developed sustainable web applications focusing on energy-efficient UI design.</li>
    <li>Collaborated with UX designers to improve accessibility and responsiveness.</li>
  </ul>

  <h3>Junior Web Developer - EcoStart</h3>
  <p><em>Jun 2021 – Dec 2022</em></p>
  <ul>
    <li>
      <span class="clickable" id="maintained-word">Maintained</span> and enhanced company website to improve user engagement.
    </li>
    <li>Implemented interactive features using JavaScript and CSS animations.</li>
  </ul>
</section>

<section id="contact" style="text-align:center;">
  <h2>Contact Me</h2>
  <p>If you want to get in touch, feel free to send me an email or download my resume.</p>
  <a href="mailto:your.email@example.com" class="contact-btn">Email Me</a>
  <a href="Your_Resume.pdf" download class="contact-btn" style="background:#264653; margin-left: 1rem;">Download Resume</a>
</section>

<!-- Detached popup -->
<div id="popup" role="dialog" aria-modal="true" aria-hidden="true">
  <p>During this time, I implemented several interactive features including JavaScript-driven animations and optimized the site for mobile devices, which increased visitor retention by 20%.</p>
</div>

<script>
  // Animate skill bars when section is in view
  function animateSkills() {
    const skills = document.querySelectorAll('.skill-level');
    skills.forEach(skill => {
      const level = skill.getAttribute('data-level');
      skill.style.width = level;
    });
  }

  // Trigger animation on scroll when skills section is visible
  window.addEventListener('scroll', () => {
    const skillsSection = document.getElementById('skills');
    const rect = skillsSection.getBoundingClientRect();
    if(rect.top < window.innerHeight && rect.bottom >= 0) {
      animateSkills();
    }
  });

  // Animate immediately if skills section is already visible on load
  window.addEventListener('load', () => {
    const skillsSection = document.getElementById('skills');
    const rect = skillsSection.getBoundingClientRect();
    if(rect.top < window.innerHeight && rect.bottom >= 0) {
      animateSkills();
    }
  });

  // Detached popup logic
  const maintainedWord = document.getElementById('maintained-word');
  const popup = document.getElementById('popup');

  function positionPopup() {
    const rect = maintainedWord.getBoundingClientRect();
    const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
    const scrollLeft = window.pageXOffset || document.documentElement.scrollLeft;

    // Position popup centered horizontally below the clicked word
    const popupWidth = popup.offsetWidth;
    const left = rect.left + scrollLeft + rect.width / 2 - popupWidth / 2;
    const top = rect.bottom + scrollTop + 10; // 10px below the word

    popup.style.left = `${Math.max(left, 10)}px`; // prevent overflow left side
    popup.style.top = `${top}px`;
  }

  function togglePopup() {
    if (popup.classList.contains('show')) {
      popup.classList.remove('show');
      popup.setAttribute('aria-hidden', 'true');
      document.removeEventListener('click', outsideClickListener);
    } else {
      positionPopup();
      popup.classList.add('show');
      popup.setAttribute('aria-hidden', 'false');
      // Close popup when clicking outside
      setTimeout(() => {
        document.addEventListener('click', outsideClickListener);
      }, 0);
    }
  }

  function outsideClickListener(event) {
    if (!popup.contains(event.target) && event.target !== maintainedWord) {
      togglePopup();
    }
  }

  maintainedWord.addEventListener('click', (e) => {
    e.stopPropagation();
    togglePopup();
  });

  // Close popup on ESC key
  window.addEventListener('keydown', (e) => {
    if(e.key === 'Escape' && popup.classList.contains('show')) {
      togglePopup();
    }
  });

  // Reposition popup on window resize or scroll if open
  window.addEventListener('resize', () => {
    if(popup.classList.contains('show')) {
      positionPopup();
    }
  });
  window.addEventListener('scroll', () => {
    if(popup.classList.contains('show')) {
      positionPopup();
    }
  });
</script>

</body>
</html>



// Footer Year
document.getElementById('year').textContent = new Date().getFullYear();

// Hamburger Menu
const menuToggle = document.getElementById('menuToggle');
const siteNav = document.getElementById('siteNav');
menuToggle.addEventListener('click', () => {
  const expanded = menuToggle.getAttribute('aria-expanded') === 'true';
  menuToggle.setAttribute('aria-expanded', !expanded);
  siteNav.classList.toggle('open');
});

// Smooth Scroll
document.querySelectorAll('.nav-link').forEach(link => {
  link.addEventListener('click', e => {
    e.preventDefault();
    const target = document.querySelector(link.getAttribute('href'));
    target.scrollIntoView({ behavior: 'smooth' });
    if(siteNav.classList.contains('open')){
      siteNav.classList.remove('open');
      menuToggle.setAttribute('aria-expanded', false);
    }
  });
});

// Contact Form
const form = document.querySelector('.contact-form');
form.addEventListener('submit', e => {
  e.preventDefault();
  alert('💌 Thank you! Ysabelle will get back to you soon.');
  form.reset();
});

// Fade-in Scroll Animation
const faders = document.querySelectorAll('.fade-on-scroll');
const appearOptions = { threshold:0.3 };
const appearOnScroll = new IntersectionObserver((entries, observer) => {
  entries.forEach(entry => {
    if(entry.isIntersecting){
      entry.target.style.opacity = 1;
      entry.target.style.transform = 'translateY(0)';
      observer.unobserve(entry.target);
    }
  });
}, appearOptions);
faders.forEach(fader => appearOnScroll.observe(fader));

// Hero Animated Background
const canvas = document.getElementById('heroCanvas');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let circles = [];
for(let i=0;i<50;i++){
  circles.push({
    x: Math.random()*canvas.width,
    y: Math.random()*canvas.height,
    r: Math.random()*4+2,
    dx:(Math.random()-0.5)*1.2,
    dy:(Math.random()-0.5)*1.2
  });
}

let mouse = {x: canvas.width/2, y: canvas.height/2};
window.addEventListener('mousemove', e => {
  mouse.x = e.clientX;
  mouse.y = e.clientY;
});

function animate(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  circles.forEach(c=>{
    // small reaction to mouse
    let dx = mouse.x - c.x;
    let dy = mouse.y - c.y;
    c.x += c.dx + dx*0.0005;
    c.y += c.dy + dy*0.0005;

    ctx.beginPath();
    ctx.arc(c.x,c.y,c.r,0,Math.PI*2);
    ctx.fillStyle='rgba(255,182,193,0.5)';
    ctx.fill();

    if(c.x<0||c.x>canvas.width) c.dx*=-1;
    if(c.y<0||c.y>canvas.height) c.dy*=-1;
  });
  requestAnimationFrame(animate);
}
animate();
window.addEventListener('resize',()=>{canvas.width = window.innerWidth; canvas.height = window.innerHeight;});

// Intro Screen Elements
const introScreen = document.getElementById('introScreen');
const introBtn = document.getElementById('introBtn');
const progressBar = document.getElementById('progress');

// Create Canvas for Intro Particles
const introCanvas = document.createElement('canvas');
introCanvas.id = 'introCanvas';
introScreen.appendChild(introCanvas);
const introCtx = introCanvas.getContext('2d');

function resizeIntroCanvas(){
  introCanvas.width = window.innerWidth;
  introCanvas.height = window.innerHeight;
}
resizeIntroCanvas();
window.addEventListener('resize', resizeIntroCanvas);

// Intro Particles
let introParticles = [];
for(let i=0;i<50;i++){
  introParticles.push({
    x: Math.random()*introCanvas.width,
    y: Math.random()*introCanvas.height,
    r: Math.random()*4+2,
    dx: (Math.random()-0.5)*1.2,
    dy: (Math.random()-0.5)*1.2
  });
}

let introMouse = {x: introCanvas.width/2, y: introCanvas.height/2};
introCanvas.addEventListener('mousemove', e => {
  introMouse.x = e.clientX;
  introMouse.y = e.clientY;
});

function animateIntro(){
  introCtx.clearRect(0,0,introCanvas.width,introCanvas.height);
  introParticles.forEach(p=>{
    let dx = introMouse.x - p.x;
    let dy = introMouse.y - p.y;
    p.x += p.dx + dx*0.0005;
    p.y += p.dy + dy*0.0005;

    introCtx.beginPath();
    introCtx.arc(p.x,p.y,p.r,0,Math.PI*2);
    introCtx.fillStyle='rgba(255,182,193,0.5)';
    introCtx.fill();

    if(p.x<0||p.x>introCanvas.width) p.dx*=-1;
    if(p.y<0||p.y>introCanvas.height) p.dy*=-1;
  });
  requestAnimationFrame(animateIntro);
}
animateIntro();

// Click Me Button Logic - Start Loading
introBtn.addEventListener('click', () => {
  let progress = 0;
  const interval = setInterval(() => {
    progress += 1;
    progressBar.style.width = progress + '%';
    if(progress >= 100){
      clearInterval(interval);
      introScreen.style.opacity = 0;
      setTimeout(()=>{ introScreen.style.display = 'none'; },500);
    }
  }, 30);
});

// Exit Button - Go back to intro
const exitBtn = document.getElementById('exitBtn');
exitBtn.addEventListener('click', e => {
  e.preventDefault();
  introScreen.style.display = 'flex';
  introScreen.style.opacity = 1;
  progressBar.style.width = '0%';
});

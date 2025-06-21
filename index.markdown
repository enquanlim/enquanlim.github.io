---
layout: home
title: ""
---

<style>
/*─────────────────────────────────────────────────────────────────────────*/
/* Overall layout & sidebar                                              */
/*─────────────────────────────────────────────────────────────────────────*/
/* Reset body margins to ensure flush layout */
body {
  margin: 0 !important;
  padding: 0 !important;
  background-color: #f0f7f0; /* Light green background */
}

/* Hide Posts section and About link from Jekyll theme */
/* Remove the problematic selectors and just hide common post elements */
.post-list,
.posts,
#posts,
.site-nav a[href*="about"],
.site-header a[href*="about"],
nav a[href*="about"],
header a[href*="about"] {
  display: none !important;
}

/* Page wrapper specific - remove absolute positioning */
.page-wrapper { 
  display: flex; 
  margin: 0 auto;  /* Center the wrapper */
  padding: 0;
  max-width: 1200px;  /* Set a max width for the content */
  position: relative;
}

.sidebar {
  position: fixed;  /* Changed from sticky to fixed */
  left: 0;  /* Ensure it starts at the left edge */
  top: 0;
  width: 200px;
  padding: 1rem;
  background: #2d5a2d; /* Dark green sidebar */
  border-right: 2px solid #4caf50;
  height: 100vh;
  box-sizing: border-box;
  margin: 0;
}

.sidebar-nav { list-style: none; padding: 0; margin: 0; }
.sidebar-nav li + li { margin-top: 0.5rem; }
.sidebar-nav a {
  display: block;
  padding: 0.4rem 0.6rem;
  text-decoration: none;
  color: #e8f5e9; /* Light green text */
  font-weight: 600;
  border-radius: 4px;
  transition: all 0.3s ease;
}
.sidebar-nav a.active,
.sidebar-nav a:hover { 
  background: #4caf50; 
  color: #fff;
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

.main-content { 
  flex: 1; 
  padding: 2rem; 
  box-sizing: border-box;
  margin-left: 200px;  /* Account for fixed sidebar */
  background: #ffffff;
  min-height: 100vh;
}

/* Typography with green theme */
h1, h2, h3 {
  color: #2d5a2d;
}

h2 {
  border-bottom: 2px solid #4caf50;
  padding-bottom: 0.5rem;
  margin-bottom: 1.5rem;
}

/* Links */
a {
  color: #388e3c;
  text-decoration: none;
  transition: color 0.3s ease;
}

a:hover {
  color: #2e7d32;
  text-decoration: underline;
}

/* Lists */
ul li {
  margin-bottom: 0.5rem;
}

/* Skills and education sections */
.main-content ul {
  list-style-type: none;
  padding-left: 0;
}

.main-content ul li::before {
  content: "• ";
  color: #4caf50;
  font-weight: bold;
  margin-right: 0.5rem;
}

/*─────────────────────────────────────────────────────────────────────────*/
/* Tab behavior                                                          */
/*─────────────────────────────────────────────────────────────────────────*/
.tab-content { display: none; }
.tab-content.active { display: block; }

/*─────────────────────────────────────────────────────────────────────────*/
/* Timeline (inside About Me tab)                                         */
/*─────────────────────────────────────────────────────────────────────────*/
.timeline-container {
  position: relative; margin: 2rem 0; padding-left: 2rem;
}
.timeline-container::before {
  content: ''; position: absolute;
  left: 1rem; top: 0; bottom: 0; width: 3px;
  background: linear-gradient(to bottom, #4caf50, #81c784);
}
.timeline-entry { position: relative; margin-bottom: 2rem; }
.timeline-marker {
  position: absolute; left: -0.4rem; top: 0.2rem;
  width: 1.1rem; height: 1.1rem; background: #fff;
  border: 3px solid #4caf50; border-radius: 50%;
  box-shadow: 0 0 0 3px rgba(76, 175, 80, 0.2);
  transition: all 0.3s ease;
}
.timeline-entry:hover .timeline-marker {
  transform: scale(1.2);
  box-shadow: 0 0 0 5px rgba(76, 175, 80, 0.3);
}
.timeline-content { 
  padding-left: 1.5rem; 
  background: #f1f8e9;
  padding: 1rem 1rem 1rem 2.5rem;
  border-radius: 8px;
  border-left: 3px solid transparent;
  transition: all 0.3s ease;
}
.timeline-entry:hover .timeline-content {
  border-left-color: #4caf50;
  box-shadow: 0 3px 10px rgba(76, 175, 80, 0.2);
}
.timeline-date {
  display: block; font-size: 0.9rem; font-weight: bold;
  color: #388e3c; margin-bottom: 0.25rem;
}
.timeline-title { 
  margin: 0; 
  font-size: 1.1rem; 
  color: #2d5a2d;
}
.timeline-content p { margin: 0.5rem 0 0; line-height: 1.4; }

/* CV & Contact styling */
#contact ul {
  list-style: none;
  padding: 0;
}

#contact ul li {
  background: #e8f5e9;
  padding: 1rem;
  margin-bottom: 1rem;
  border-radius: 8px;
  border-left: 4px solid #4caf50;
  transition: all 0.3s ease;
}

#contact ul li:hover {
  background: #c8e6c9;
  transform: translateX(5px);
}

#contact ul li::before {
  content: none; /* Remove the arrow for contact items */
}

/* Strong text styling */
strong {
  color: #2d5a2d;
  font-weight: 700;
}

/* Section spacing */
.main-content > div > *:not(:last-child) {
  margin-bottom: 2rem;
}

/*─────────────────────────────────────────────────────────────────────────*/
/* Mobile Responsiveness                                                   */
/*─────────────────────────────────────────────────────────────────────────*/
/* Hamburger menu button */
.menu-toggle {
  display: none;
  position: fixed;
  top: 1rem;
  left: 1rem;
  z-index: 1001;
  background: #4caf50;
  border: none;
  border-radius: 4px;
  padding: 0.5rem;
  cursor: pointer;
  width: 40px;
  height: 40px;
  justify-content: center;
  align-items: center;
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

.menu-toggle span {
  display: block;
  width: 25px;
  height: 3px;
  background: white;
  margin: 5px 0;
  transition: all 0.3s ease;
}

.menu-toggle.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.menu-toggle.active span:nth-child(2) {
  opacity: 0;
}

.menu-toggle.active span:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -6px);
}

/* Mobile styles */
@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
    flex-direction: column;
  }
  
  .sidebar {
    position: fixed;
    left: -250px; /* Hide sidebar off-screen */
    width: 250px;
    transition: left 0.3s ease;
    z-index: 1000;
    box-shadow: 2px 0 10px rgba(0,0,0,0.1);
  }
  
  .sidebar.active {
    left: 0; /* Slide in sidebar */
  }
  
  .main-content {
    margin-left: 0;
    padding: 1rem;
    padding-top: 4rem; /* Space for hamburger button */
  }
  
  .page-wrapper {
    max-width: 100%;
  }
  
  /* Adjust timeline for mobile */
  .timeline-container {
    padding-left: 1.5rem;
  }
  
  .timeline-container::before {
    left: 0.5rem;
  }
  
  .timeline-marker {
    left: -0.4rem;
  }
  
  .timeline-content {
    padding: 0.8rem;
    padding-left: 1.5rem;
  }
  
  /* Mobile typography adjustments */
  h2 {
    font-size: 1.5rem;
  }
  
  h3 {
    font-size: 1.1rem;
  }
  
  .timeline-title {
    font-size: 1rem;
  }
  
  /* Contact section mobile */
  #contact ul li {
    padding: 0.8rem;
    font-size: 0.9rem;
  }
}

/* Overlay for mobile menu */
.sidebar-overlay {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 999;
}

.sidebar-overlay.active {
  display: block;
}

/* Tablet styles */
@media (min-width: 769px) and (max-width: 1024px) {
  .sidebar {
    width: 180px;
  }
  
  .main-content {
    margin-left: 180px;
  }
}
</style>

<div class="page-wrapper">
<button class="menu-toggle" id="menuToggle">
  <span></span>
  <span></span>
  <span></span>
</button>
<div class="sidebar-overlay" id="sidebarOverlay"></div>
<aside class="sidebar" id="sidebar">
<ul class="sidebar-nav">
<li><a href="#" data-tab="about">About Me</a></li>
<li><a href="#" data-tab="contact">CV &amp; Contact</a></li>
</ul>
</aside>

<main class="main-content">

<div id="about" class="tab-content" markdown="1">
## About Me
I'm based in Singapore. I recently graduated with an MSc in Financial Statistics from the London School of Economics and a B.A. in Economics from Nanyang Technological University.

## Career Timeline
<div class="timeline-container">

<div class="timeline-entry">
  <div class="timeline-marker"></div>
  <div class="timeline-content">
    <span class="timeline-date">Sep 2024 – Jun 2025</span>
    <h3 class="timeline-title">MSc Statistics at London School of Economics and Political Science</h3>
  </div>
</div>

<div class="timeline-entry">
  <div class="timeline-marker"></div>
  <div class="timeline-content">
    <span class="timeline-date">Oct 2023 – Sep 2024</span>
    <h3 class="timeline-title">Equity Derivatives Trading Graduate Trainee at Societe Generale</h3>
  </div>
</div>

<div class="timeline-entry">
  <div class="timeline-marker"></div>
  <div class="timeline-content">
    <span class="timeline-date">Oct 2022 – Oct 2023</span>
    <h3 class="timeline-title">Quantitative Research Graduate Trainee at Societe Generale</h3>
  </div>
</div>

</div>

## Education & Certification

- **MSc Statistics (Financial Statistics)**  
  London School of Economics and Political Science
- **BA. Economics**  
  Nanyang Technological University

## Skills

- **Languages**: English (Native), Mandarin (Native)  
- **Programming**: Python (Pandas, NumPy, SciPy, Statsmodels, CVXPY, IPyWidgets, xlwings), R  
- **Quant & ML**: Time-series forecasting, Deep learning, PCA, CART, KNN, Econometric modelling  
- **Financial**: Equity Derivatives (options, futures, variance swaps), Volatility Surface & Greeks   
</div>

<div id="contact" class="tab-content">
<h2>CV &amp; Contact</h2>
<ul>
  <li><a href="/assets/Lim_En_Quan_CV.pdf" target="_blank">Download my resume (PDF)</a></li>
  <li><a href="mailto:limenquan@outlook.com">limenquan@outlook.com</a></li>
</ul>
</div>

</main>
</div>

<script>
document.addEventListener('DOMContentLoaded', function(){
  var links = document.querySelectorAll('.sidebar-nav a');
  var tabs = document.querySelectorAll('.tab-content');
  var menuToggle = document.getElementById('menuToggle');
  var sidebar = document.getElementById('sidebar');
  var sidebarOverlay = document.getElementById('sidebarOverlay');
  
  function activate(tabId){
    tabs.forEach(function(t){ t.classList.toggle('active', t.id===tabId) });
    links.forEach(function(l){ l.classList.toggle('active', l.dataset.tab===tabId) });
    
    // Close mobile menu when a link is clicked
    if(window.innerWidth <= 768) {
      sidebar.classList.remove('active');
      sidebarOverlay.classList.remove('active');
      menuToggle.classList.remove('active');
    }
  }
  
  links.forEach(function(link){
    link.addEventListener('click', function(e){
      e.preventDefault();
      activate(link.dataset.tab);
    });
  });
  
  // Mobile menu toggle
  menuToggle.addEventListener('click', function() {
    sidebar.classList.toggle('active');
    sidebarOverlay.classList.toggle('active');
    menuToggle.classList.toggle('active');
  });
  
  // Close menu when overlay is clicked
  sidebarOverlay.addEventListener('click', function() {
    sidebar.classList.remove('active');
    sidebarOverlay.classList.remove('active');
    menuToggle.classList.remove('active');
  });
  
  // Close menu on window resize if going from mobile to desktop
  window.addEventListener('resize', function() {
    if(window.innerWidth > 768) {
      sidebar.classList.remove('active');
      sidebarOverlay.classList.remove('active');
      menuToggle.classList.remove('active');
    }
  });
  
  activate('about');
  
  // Remove Posts section
  var allH2s = document.querySelectorAll('h2');
  allH2s.forEach(function(h2) {
    if(h2.textContent.trim() === 'Posts') {
      // Remove the h2 and all siblings after it
      var element = h2;
      while(element) {
        var next = element.nextElementSibling;
        element.remove();
        element = next;
      }
    }
  });
  
  // Remove footer section more carefully
  // Look for the duplicate "Lim En Quan" at the bottom
  var allElements = document.querySelectorAll('h2, h3, p');
  var mainContent = document.querySelector('.main-content');
  
  allElements.forEach(function(el) {
    // Check if this element is outside our main content area
    if(!el.closest('.main-content') && !el.closest('.sidebar')) {
      // Check if it contains "Lim En Quan" text
      if(el.textContent.includes('Lim En Quan')) {
        // Find the container section
        var container = el.parentElement;
        while(container && container !== document.body) {
          if(container.tagName === 'FOOTER' || 
             container.tagName === 'SECTION' || 
             container.tagName === 'DIV') {
            container.remove();
            break;
          }
          container = container.parentElement;
        }
      }
    }
  });
});</script>
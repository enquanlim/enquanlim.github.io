---
layout: home
title: ""
description: "Portfolio of Lim En Quan, quantitative finance professional in Singapore. Projects, experience, and contact."
---

<!-- SEO Meta Tags -->
<meta name="description" content="Portfolio of Lim En Quan, quantitative finance professional in Singapore. Projects, experience, and contact.">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="author" content="Lim En Quan">
<meta property="og:title" content="Lim En Quan">
<meta property="og:description" content="Portfolio of Lim En Quan, quantitative finance professional in Singapore. Projects, experience, and contact.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://enquanlim.github.io/">

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

/* Hide Jekyll theme header elements on all screens */
.site-header,
.page-header,
header.site-header,
header[role="banner"],
.wrapper > header:first-child {
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
.timeline-entry {
  position: relative;
  margin-bottom: 2rem;
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInTimeline 0.8s ease-out forwards;
}
.timeline-entry:nth-child(1) { animation-delay: 0.1s; }
.timeline-entry:nth-child(2) { animation-delay: 0.3s; }
.timeline-entry:nth-child(3) { animation-delay: 0.5s; }
@keyframes fadeInTimeline {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
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

/* Projects section styling */
.project-card {
  background: #f1f8e9;
  padding: 1.5rem;
  margin-bottom: 1.5rem;
  border-radius: 8px;
  border-left: 4px solid #4caf50;
  transition: all 0.3s ease;
  cursor: pointer;
}

.project-card:hover {
  box-shadow: 0 4px 12px rgba(76, 175, 80, 0.2);
  transform: translateY(-2px);
}

.project-card h3 {
  margin-top: 0;
  margin-bottom: 0.5rem;
  color: #2d5a2d;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-top: 0.5rem;
}

.tech-tag {
  background: #4caf50;
  color: white;
  padding: 0.2rem 0.8rem;
  border-radius: 15px;
  font-size: 0.85rem;
  font-weight: 500;
}

.project-links {
  margin-top: 1rem;
}

.project-links a {
  display: inline-block;
  margin-right: 1rem;
  color: #388e3c;
  font-weight: 600;
}

.project-links a:hover {
  color: #2e7d32;
}

/* PDF Viewer Modal */
.pdf-modal {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 10000;
  overflow: auto;
}

.pdf-modal-content {
  position: relative;
  background-color: #fefefe;
  margin: 2% auto;
  padding: 0;
  width: 90%;
  max-width: 1000px;
  height: 90vh;
  border-radius: 8px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.3);
}

.pdf-header {
  background: #2d5a2d;
  padding: 1rem;
  border-radius: 8px 8px 0 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.pdf-header h3 {
  color: white;
  margin: 0;
}

.close-pdf {
  color: white;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
  transition: color 0.3s ease;
  background: none;
  border: none;
  padding: 0;
  line-height: 1;
}

.close-pdf:hover,
.close-pdf:focus {
  color: #c8e6c9;
}

.pdf-viewer {
  width: 100%;
  height: calc(90vh - 60px);
  border: none;
  border-radius: 0 0 8px 8px;
}

/* Mobile PDF viewer adjustments */
@media (max-width: 768px) {
  .pdf-modal-content {
    width: 95%;
    margin: 1% auto;
    height: 95vh;
  }
  
  .pdf-viewer {
    height: calc(95vh - 60px);
  }
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

/* Custom title block styles */
.custom-title-block {
  width: 100%;
  max-width: 1200px;
  margin: 2.5rem auto 1.5rem auto;
  text-align: center;
  opacity: 0;
  animation: fadeInTitle 1.2s ease-out forwards;
}
@keyframes fadeInTitle {
  from { opacity: 0; transform: translateY(-30px); }
  to { opacity: 1; transform: translateY(0); }
}
.custom-title-block .main-title {
  font-size: 2.4rem;
  font-weight: 800;
  color: #2d5a2d;
  margin-bottom: 0.3rem;
}
@media (max-width: 600px) {
  .custom-title-block .main-title {
    font-size: 1.5rem;
  }
}

/*─────────────────────────────────────────────────────────────────────────*/
/* Mobile Responsiveness                                                   */
/*─────────────────────────────────────────────────────────────────────────*/
/* Hamburger menu button */
.menu-toggle {
  display: none;
  position: fixed;
  top: 1rem;
  right: 1rem;  /* Changed from left to right */
  z-index: 9999;  /* Increased z-index */
  background: #4caf50;
  border: none;
  border-radius: 4px;
  padding: 0;  /* Changed padding to 0 */
  cursor: pointer;
  width: 40px;
  height: 40px;
  flex-direction: column;  /* Added to stack spans vertically */
  justify-content: center;
  align-items: center;
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

.menu-toggle span {
  display: block;
  width: 25px;
  height: 3px;
  background: white;
  margin: 4px 0;  /* Changed from 5px to 4px */
  transition: all 0.3s ease;
  border-radius: 2px;  /* Added for smoother look */
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
    z-index: 9998;  /* Increased z-index */
    box-shadow: 2px 0 10px rgba(0,0,0,0.1);
    height: 100vh;
    top: 0;
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
  
  /* Project cards on mobile */
  .project-card {
    padding: 1rem;
  }
  
  .tech-tag {
    font-size: 0.8rem;
    padding: 0.15rem 0.6rem;
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
  z-index: 9997;  /* Increased z-index */
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

.site-title, .page-title, h1 {
  width: 100%;
  max-width: 1200px;
  margin: 2.5rem auto 1.5rem auto;
  text-align: center;
  font-size: 2.2rem;
  font-weight: 700;
  color: #2d5a2d;
}

@media (max-width: 600px) {
  .site-title, .page-title, h1 {
    font-size: 1.5rem;
    margin-top: 1.2rem;
    margin-bottom: 1rem;
  }
}

.page-wrapper {
  margin-top: 0;
}

/* Hide Jekyll default footer */
.site-footer, footer, .footer, .page-footer {
  display: none !important;
}
</style>

<div class="custom-title-block">
  <div class="main-title">Lim En Quan</div>
</div>

<div class="page-wrapper" role="main">
  <button class="menu-toggle" id="menuToggle" aria-label="Open navigation menu" aria-controls="sidebar" aria-expanded="false">
    <span></span>
    <span></span>
    <span></span>
  </button>
  <div class="sidebar-overlay" id="sidebarOverlay" tabindex="-1" aria-hidden="true"></div>
  <aside class="sidebar" id="sidebar" role="navigation" aria-label="Main navigation">
  <ul class="sidebar-nav">
  <li><a href="#" data-tab="about" aria-controls="about" aria-selected="true">About Me</a></li>
  <li><a href="#" data-tab="projects" aria-controls="projects">Projects</a></li>
  <li><a href="#" data-tab="contact" aria-controls="contact">CV &amp; Contact</a></li>
  </ul>
  </aside>

  <main class="main-content">

  <div id="about" class="tab-content" markdown="1" tabindex="0" aria-labelledby="about-tab">
  
  Upon my graduation from NTU, I joined SocGen where I spent a year with the Quant Research team and another year in the Asia Flow Index Trading team. During my 2 years, I've developed a fundamental understanding of equity derivatives pricing, volatility modeling, and quantitative strategies. 

  Currently, I'm seeking opportunities in trading or derivatives pricing roles where I can apply my technical skills and market knowledge.

  <h2>Career Timeline</h2>
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

  <h2>Education & Certification</h2>

  - **MSc Statistics (Financial Statistics)**  
  London School of Economics and Political Science
- **BA. Economics**  
  Nanyang Technological University

<h2>Skills</h2>

- **Languages**: English (Native), Mandarin (Fluent)  
- **Programming**: Python (Pandas, NumPy, SciPy, Statsmodels, CVXPY, IPyWidgets, xlwings), R  
- **Quant & ML**: Time-series forecasting, bagging/boosting, deep learning, PCA, econometric modelling  
- **Financial**: Equity derivatives (options, futures, variance swaps), volatility surfaces & Greeks  
</div>

<div id="projects" class="tab-content">
  <h2>Projects</h2>

  <!-- Project 1 -->
  <div class="project-card" onclick="openPDF('A Hidden Markov Model Framework for Identifying Risk-On and Risk-Off States in the US Equities Market', '/assets/Classification.pdf')">
    <h3>A Hidden Markov Model Framework for Identifying Risk-On and Risk-Off States in the US Equities Market</h3>
    <p>In this project, I tried to distinguish between “risk-on” and “risk-off” phases in equity markets—essential for dynamic asset allocation. I propose a regime‐detection framework built on Gaussian Mixture Models (GMM) and Hidden Markov Models (HMM) applied to S&P 500 daily log‐returns.</p>
    
    With a rolling feed‐forward retraining scheme and grid‐search hyperparameter tuning aimed at maximizing correlation with subsequent returns, the system classifies market states and validates its signals through a backtested trading strategy, illustrating how regime awareness can enhance portfolio performance.
    <div class="project-tech">
      <span class="tech-tag">Python</span>
      <span class="tech-tag">NumPy</span>
      <span class="tech-tag">Pandas</span>
    </div>
    <div class="project-links">
    </div>
  </div>

  <!-- Project 3 -->
  <div class="project-card" onclick="openPDF('Regression-Based Prediction of Heating and Cooling Loads in Residential Buildings', '/assets/optimal_lambda.pdf')">
    <h3>Finding the optimal λ for EWMA model for NKY and HSI</h3>
    <p>In this project, I investigated the optimal decay parameter λ for the Exponentially Weighted Moving Average (EWMA) volatility model in the context of Japanese and Hong Kong equities by analyzing monthly returns of the Nikkei 225 (1980–2024) and Hang Seng Index (1987–2024). </p>
    
    Using a rolling 36-month in-sample window with one-month out-of-sample forecasts, the study applies constrained minimization to select λ values that minimize RMSE and MAE between realized and EWMA volatilities. 
    
    By revealing how market-specific volatility dynamics affect the smoothing parameter, the project offers a tailored approach to EWMA-based risk management that enhances forecast accuracy and adapts to distinct asset behaviors. 
    
    <div class="project-tech">
      <span class="tech-tag">Python</span>
      <span class="tech-tag">Machine Learning</span>
      <span class="tech-tag">Volatility Modeling</span>
    </div>
    <div class="project-links">
    </div>
  </div>

  <!-- Project 2 -->
  <div class="project-card" onclick="openPDF('Regression-Based Prediction of Heating and Cooling Loads in Residential Buildings', '/assets/Regression.pdf')">
    <h3>Regression-Based Prediction of Heating and Cooling Loads in Residential Buildings</h3>
    <p>In this project, I developed a machine-learning tool that translates early‐stage architectural specifications—such as wall and roof area into accurate forecasts of heating and cooling energy demands. </p>
    
    By training linear, polynomial, LASSO and ridge regressions (including Bayesian variants) on the UCI Energy Efficiency dataset and systematically comparing their mean‐squared‐error performance, the study identifies the optimal modeling approach for low-error thermal‐load estimation. 
    
    The resulting models enable architects and engineers to evaluate and refine building designs for energy efficiency long before construction begins.
    <div class="project-tech">
      <span class="tech-tag">Python</span>
      <span class="tech-tag">Machine Learning</span>
      <span class="tech-tag">Statistics</span>
    </div>
    <div class="project-links">
    </div>
  </div>

  <!-- PDF Viewer Modal -->
  <div id="pdfModal" class="pdf-modal">
    <div class="pdf-modal-content">
      <div class="pdf-header">
        <h3 id="pdfTitle">Project Title</h3>
        <button class="close-pdf" onclick="closePDF()">&times;</button>
      </div>
      <iframe id="pdfViewer" class="pdf-viewer" src=""></iframe>
    </div>
  </div>

  </div>

  <div id="contact" class="tab-content">
  <h2>CV &amp; Contact</h2>
  <ul>
    <li><a href="/assets/Lim_En_Quan_CV.pdf" target="_blank">View CV (PDF)</a></li>
    <li><a href="mailto:limenquan@outlook.com">limenquan@outlook.com</a></li>
  </ul>
  </div>

  </main>
  </div>

<script>
// PDF viewer functions
function openPDF(title, pdfPath) {
  document.getElementById('pdfTitle').textContent = title;
  document.getElementById('pdfViewer').src = pdfPath;
  document.getElementById('pdfModal').style.display = 'block';
  document.body.style.overflow = 'hidden'; // Prevent scrolling when modal is open
}

function closePDF() {
  document.getElementById('pdfModal').style.display = 'none';
  document.getElementById('pdfViewer').src = ''; // Clear the iframe
  document.body.style.overflow = 'auto'; // Re-enable scrolling
}

// Close modal when clicking outside of it
window.onclick = function(event) {
  var modal = document.getElementById('pdfModal');
  if (event.target == modal) {
    closePDF();
  }
}

// Close modal with Escape key
document.addEventListener('keydown', function(event) {
  if (event.key === 'Escape') {
    closePDF();
  }
});

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
});
</script>
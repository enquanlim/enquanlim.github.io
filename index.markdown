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
  background: #f9f9f9;
  border-right: 1px solid #e0e0e0;
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
  color: #333;
  font-weight: 600;
  border-radius: 4px;
}
.sidebar-nav a.active,
.sidebar-nav a:hover { background: #e0e0e0; }

.main-content { 
  flex: 1; 
  padding: 1rem; 
  box-sizing: border-box;
  margin-left: 200px;  /* Account for fixed sidebar */
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
  left: 1rem; top: 0; bottom: 0; width: 2px;
  background: #4caf50;
}
.timeline-entry { position: relative; margin-bottom: 2rem; }
.timeline-marker {
  position: absolute; left: -0.35rem; top: 0.2rem;
  width: 1rem; height: 1rem; background: #fff;
  border: 2px solid #4caf50; border-radius: 50%;
}
.timeline-content { padding-left: 1.5rem; }
.timeline-date {
  display: block; font-size: 0.9rem; font-weight: bold;
  color: #4caf50; margin-bottom: 0.25rem;
}
.timeline-title { margin: 0; font-size: 1.1rem; }
.timeline-content p { margin: 0.5rem 0 0; line-height: 1.4; }
</style>

<div class="page-wrapper">
<aside class="sidebar">
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
- **B.A. Economics (First Class Honours)**  
  Nanyang Technological University

## Skills

- **Languages**: English (Native), Mandarin (Fluent)  
- **Programming**: Python (Pandas, NumPy, SciPy, Statsmodels, CVXPY, IPyWidgets, xlwings), R  
- **Quant & ML**: Time-series forecasting, bagging/boosting, deep learning, PCA, econometric modelling  
- **Financial**: Equity derivatives (options, futures, variance swaps), volatility surfaces & Greeks  
</div>

<div id="contact" class="tab-content">
<h2>CV &amp; Contact</h2>
<ul>
  <li>📄 <a href="/assets/Lim_En_Quan_CV.pdf" target="_blank">Download my résumé (PDF)</a></li>
  <li>✉️ <a href="mailto:limenquan@outlook.com">limenquan@outlook.com</a></li>
</ul>
</div>

</main>
</div>

<script>
document.addEventListener('DOMContentLoaded', function(){
  var links = document.querySelectorAll('.sidebar-nav a');
  var tabs = document.querySelectorAll('.tab-content');
  function activate(tabId){
    tabs.forEach(function(t){ t.classList.toggle('active', t.id===tabId) });
    links.forEach(function(l){ l.classList.toggle('active', l.dataset.tab===tabId) });
  }
  links.forEach(function(link){
    link.addEventListener('click', function(e){
      e.preventDefault();
      activate(link.dataset.tab);
    });
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
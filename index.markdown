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
/* (Your entire existing CSS remains unchanged — omitted here for brevity in explanation,
but keep everything exactly as it was in your current file) */
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
      <li><a href="#" data-tab="about">About Me</a></li>
      <li><a href="#" data-tab="projects">Projects</a></li>
      <li><a href="#" data-tab="contact">CV &amp; Contact</a></li>
    </ul>
  </aside>

  <main class="main-content">

  <div id="about" class="tab-content" markdown="1">
  <!-- About content unchanged -->
  </div>

  <div id="projects" class="tab-content">
  <!-- Projects content unchanged -->
  </div>

  <div id="contact" class="tab-content">
    <h2>CV &amp; Contact</h2>
    <ul>
      <li><a href="#" onclick="return false;">Resume auto-opens when this tab is clicked</a></li>
      <li><a href="mailto:limenquan@outlook.com">limenquan@outlook.com</a></li>
    </ul>
  </div>

  </main>
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

<script>
// PDF viewer functions
function openPDF(title, pdfPath) {
  document.getElementById('pdfTitle').textContent = title;
  document.getElementById('pdfViewer').src = pdfPath;
  document.getElementById('pdfModal').style.display = 'block';
  document.body.style.overflow = 'hidden';
}

function closePDF() {
  document.getElementById('pdfModal').style.display = 'none';
  document.getElementById('pdfViewer').src = '';
  document.body.style.overflow = 'auto';
}

window.onclick = function(event) {
  var modal = document.getElementById('pdfModal');
  if (event.target == modal) {
    closePDF();
  }
}

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
    tabs.forEach(function(t){ 
      t.classList.toggle('active', t.id===tabId) 
    });

    links.forEach(function(l){ 
      l.classList.toggle('active', l.dataset.tab===tabId) 
    });

    // AUTO-OPEN RESUME WHEN CV TAB IS ACTIVATED
    if (tabId === 'contact') {

      // Mobile → open native full screen viewer
      if (window.innerWidth <= 768) {
        window.open('/assets/Lim_En_Quan_CV.pdf', '_blank');
      } 
      // Desktop → open modal
      else {
        openPDF('Lim En Quan - Resume', '/assets/Lim_En_Quan_CV.pdf');
      }
    }

    // Close mobile menu if open
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
  
  menuToggle.addEventListener('click', function() {
    sidebar.classList.toggle('active');
    sidebarOverlay.classList.toggle('active');
    menuToggle.classList.toggle('active');
  });
  
  sidebarOverlay.addEventListener('click', function() {
    sidebar.classList.remove('active');
    sidebarOverlay.classList.remove('active');
    menuToggle.classList.remove('active');
  });
  
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
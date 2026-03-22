---
layout: about
title: about
nav: false
permalink: /
subtitle: >
  PhD student @ <a href='https://team.inria.fr/premedical/'>PreMeDICaL INRIA-Inserm team</a>, Montpellier, France.<br>
  e-mail: thomas.boudou@inria.fr; 
  <a href="https://scholar.google.com/citations?user=6CXRuKsAAAAJ"> Google Scholar</a>.



profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  #more_info: >
  #  <p>555 your office number</p>
  #  <p>123 your address street</p>
  #  <p>Your City, State 12345</p>

selected_papers: false # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

#announcements:
#  enabled: true # includes a list of news items
#  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
#  limit: 5 # leave blank to include all the news in the `_news` folder

#latest_posts:
#  enabled: true
#  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
#  limit: 3 # leave blank to include all the blog posts

#Contact me <a href="mailto:thomas.boudou@inria.fr"><i class="fas fa-envelope"></i> e-mail: thomas.boudou@inria.fr</a>
#or check my publications <a href="https://scholar.google.com/citations?user=6CXRuKsAAAAJ"><i class="ai ai-google-scholar"></i> Google Scholar</a>.

scholar:
  style: apa
  sort_by: year
  order: descending
  group_by: none
---

<br>
I am a PhD student, supervised by <a href='https://researchers.lille.inria.fr/abellet/'>Aurélien Bellet</a>, <a href='https://batistelb.github.io/'>Batiste Le Bars</a> and <a href='https://nirupam115.github.io/'>Nirupam Gupta</a>, within an INRIA–Inserm team at the University of Montpellier, France. My research focuses on the intersection of Byzantine-Robust and Private Learning. Prior to my doctoral studies, I completed a master’s degree at École Normale Supérieure Paris-Saclay and worked for some years as an engineer developing decision-support algorithms for intraoperative diagnostics during arrhythmia surgeries. Through this experience, I witnessed first-hand how robust learning can support clinical practice—where highly specialized annotations, produced by a small group of experts, inevitably introduce variability or errors—and how federated collaboration across hospitals could lead to stronger solutions, provided privacy is preserved. These experiences have fueled my enthusiasm for developing stronger theoretical foundations to advance trustworthy and practical applications of machine learning.
<br><br><br><br><br>

## Publications & Preprints

{% bibliography --template bib --no-group %}



<!-- BACKGROUND SCHEMATIC -->

<style>
    /* Fixed SVG Background Layer */
    .background-schema {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        z-index: -1;
        pointer-events: none;
        opacity: 0.12; /* Keeps it faint so text is readable */
    }
</style>

<svg class="background-schema" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice">
    <g stroke="#007fb5" fill="none" stroke-width="1.5">
        
        <!-- DP-SGD Stability & Isotropic Gaussian Overlap -->
        <g transform="translate(900, 550)">
            
            <!-- Shared initial trajectory (Before differing sample) -->
            <polyline points="-250,-120 -200,-70 -150,-100 -100,-40" stroke-width="2" stroke-linejoin="round"/>
            <circle cx="-250" cy="-120" r="3" fill="#007fb5"/>
            <circle cx="-200" cy="-70" r="3" fill="#007fb5"/>
            <circle cx="-150" cy="-100" r="3" fill="#007fb5"/>
            <circle cx="-100" cy="-40" r="3" fill="#007fb5"/> <!-- Point of divergence -->

            <!-- Path 1 (Dataset S) -->
            <polyline points="-100,-40 -60,20 -10,-10 40,30 90,10" stroke-width="2" stroke-linejoin="round"/>
            <circle cx="-60" cy="20" r="3" fill="#007fb5"/>
            <circle cx="-10" cy="-10" r="3" fill="#007fb5"/>
            <circle cx="40" cy="30" r="3" fill="#007fb5"/>
            
            <!-- Path 2 (Dataset S') - Dashed -->
            <polyline points="-100,-40 -50,-90 0,-60 50,-40 90,-20" stroke-width="2" stroke-dasharray="6 6" stroke-linejoin="round"/>
            <circle cx="-50" cy="-90" r="3" fill="#007fb5"/>
            <circle cx="0" cy="-60" r="3" fill="#007fb5"/>
            <circle cx="50" cy="-40" r="3" fill="#007fb5"/>

            <!-- Distance trackers between iterates (showing divergence then reconvergence) -->
            <line x1="-60" y1="20" x2="-50" y2="-90" stroke-dasharray="2 2" opacity="0.4"/>
            <line x1="-10" y1="-10" x2="0" y2="-60" stroke-dasharray="2 2" opacity="0.4"/>
            <line x1="40" y1="30" x2="50" y2="-40" stroke-dasharray="2 2" opacity="0.4"/>
            
            <!-- Final Iterates and Final Distance -->
            <circle cx="90" cy="10" r="5" fill="#007fb5"/>
            <circle cx="90" cy="-20" r="5" fill="#007fb5"/>
            <line x1="90" y1="10" x2="90" y2="-20" stroke-width="2"/> <!-- Final contractivity -->

            <!-- Isotropic Gaussians (Circles) at Final Iterate for Path 1 -->
            <circle cx="90" cy="10" r="25" stroke-dasharray="2 3" stroke-linecap="round" opacity="1.0"/>
            <circle cx="90" cy="10" r="50" stroke-dasharray="2 5" stroke-linecap="round" opacity="0.8"/>
            <circle cx="90" cy="10" r="75" stroke-dasharray="2 7" stroke-linecap="round" opacity="0.6"/>
            <circle cx="90" cy="10" r="100" stroke-dasharray="2 9" stroke-linecap="round" opacity="0.4"/>

            <!-- Isotropic Gaussians (Circles) at Final Iterate for Path 2 (Overlapping) -->
            <circle cx="90" cy="-20" r="25" stroke-dasharray="2 3" stroke-linecap="round" opacity="1.0"/>
            <circle cx="90" cy="-20" r="50" stroke-dasharray="2 5" stroke-linecap="round" opacity="0.8"/>
            <circle cx="90" cy="-20" r="75" stroke-dasharray="2 7" stroke-linecap="round" opacity="0.8"/>
            <circle cx="90" cy="-20" r="100" stroke-dasharray="2 9" stroke-linecap="round" opacity="0.4"/>
        </g>

        <!-- Byzantine Robustness -->
        <g transform="translate(200, 400)">
            <circle cx="0" cy="0" r="5" fill="#007fb5"/>
            <line x1="0" y1="0" x2="-80" y2="40" />
            <line x1="0" y1="0" x2="-40" y2="90" />
            <line x1="0" y1="0" x2="50" y2="70" />
            <line x1="0" y1="0" x2="70" y2="10" />
            <line x1="0" y1="0" x2="-60" y2="-70" stroke-dasharray="5 5" />
            <circle cx="-60" cy="-70" r="5" fill="none" stroke="#007fb5"/>
            <circle cx="-80" cy="40" r="3" fill="#007fb5"/>
            <circle cx="-40" cy="90" r="3" fill="#007fb5"/>
            <circle cx="50" cy="70" r="3" fill="#007fb5"/>
            <circle cx="70" cy="10" r="3" fill="#007fb5"/>
        </g>

    </g>
</svg>

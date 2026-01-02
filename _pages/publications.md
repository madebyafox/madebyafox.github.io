---
layout: page
permalink: /publications/
title: publications
description: PDFs are provided to ensure timely dissemination of academic work. They can be downloaded for noncommercial, information purposes only, and may not be reposted without permission from the respective copyright holders.
nav: true
nav_order: 3
nav_rank: 3
---
<!-- _pages/publications.md -->
<div class="publications">


<h1>ARTICLES
<span class="description"> &nbsp; peer-reviewed, archival proceedings</span></h1>
{% bibliography --file 1_articles.bib %}

<h1>BOOK CHAPTERS </h1>
{% bibliography --file 2_chapters.bib %}

<h1>PROCEEDINGS
<span class="description"> &nbsp; short papers, workshops, extended-abstracts, non-archival proceedings</span></h1>
{% bibliography --file 3_proceedings.bib %}

<h1>COLLOQUIA
<span class="description"> &nbsp; colloquia, symposia</span></h1>
{% bibliography --file 4_colloquia.bib %}

<h1>POSTER PRESENTATIONS
<span class="description"> &nbsp; short papers and abstracts presented as posters</span></h1>
{% bibliography --file 5_posters.bib %}

<h1>THESES</h1>
{% bibliography --file 9_theses.bib %}

</div> <!-- end pubs -->


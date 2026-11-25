---
layout: about
title: about
permalink: /
subtitle: Ph.D. Candidate, Electrical and Computer Engineering, <a href='https://www.pitt.edu/'>University of Pittsburgh</a>

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>1113 Benedum Hall</p>
    <p>University of Pittsburgh</p>
    <p>Pittsburgh, PA 15261</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # news is placed inside the page body below # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
---

I am a Ph.D. candidate in Electrical and Computer Engineering at the [University of Pittsburgh](https://www.pitt.edu/), advised by Prof. Jun Yang. I expect to graduate in June 2027.

I am also a research intern at [Carnegie Mellon University](https://www.cmu.edu/), working with Dr. Limin Jia. My research makes software secure against memory-safety vulnerabilities, and my work has been published at NDSS and ICS. More details are in my [CV](/assets/pdf/Yubo_Du_CV.pdf?v=2).

## education

- **Ph.D., Electrical and Computer Engineering**, University of Pittsburgh, Jan. 2022 – present. Advisor: Prof. Jun Yang
- **M.S., Computer Science**, Vanderbilt University, Jan. 2020 – Dec. 2021. Advisor: Prof. Gautam Biswas
- **B.S., Physics**, University of Science and Technology of China, Aug. 2014 – Jun. 2018

<h2><a href="/news/" style="color: inherit">news</a></h2>

{% include news.liquid limit=true %}

## research

The goal of my research is to make software secure against memory-safety vulnerabilities by combining the guarantees of deterministic defenses with the efficiency of AI. Deterministic defenses are reliable but expensive, and AI is efficient but unreliable. The two are complementary: AI decides where to focus, and deterministic methods decide what is true. My published work makes deterministic defenses fast enough for real-world software:

- **FPN: Fast Pointer Nullification for Use-After-Free Prevention** (NDSS 2026). A runtime defense that stops use-after-free attacks in deployed C/C++ software. FPN tracks pointers in groups by their locality while keeping protection exact, which reduces memory overhead from about 173% to about 8%. [[Paper]](https://www.ndss-symposium.org/wp-content/uploads/2026-f753-paper.pdf) [[Code]](https://github.com/duyubo/Fast-Pointer-Nullification-NDSS-2026)
- **RTT-UAF: Reuse Time Tracking for Use-After-Free Detection** (ICS 2024). A sanitizer that finds use-after-free bugs during testing. RTT stores a small reuse count in the unused bits of each pointer, so no metadata needs to be propagated, which cuts runtime overhead by up to 7×. [[Paper]](https://doi.org/10.1145/3650200.3656606)

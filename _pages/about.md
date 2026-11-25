---
layout: about
title: About
permalink: /
subtitle: Ph.D. Candidate, Electrical and Computer Engineering, University of Pittsburgh

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>University of Pittsburgh</p>
    <p>Pittsburgh, PA</p>

selected_papers: false # selected papers are placed inside the page body below
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # news is placed inside the page body below # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
---
<style>
  @media (min-width: 576px) {
    .profile { width: 22% !important; }
    .profile .more-info { font-size: 0.8rem; }
  }
</style>


I am a Ph.D. candidate in Electrical and Computer Engineering at the University of Pittsburgh, advised by Prof. [Jun Yang](https://sites.pitt.edu/~juy9/). I expect to graduate in June 2027. I am also a research intern at Carnegie Mellon University, working with Dr. [Limin Jia](https://www.andrew.cmu.edu/user/liminjia/). The goal of my research is to make software secure against memory-safety vulnerabilities by combining the guarantees of deterministic defenses with the efficiency of AI.

## Education

- **Ph.D., Electrical and Computer Engineering**, University of Pittsburgh, Jan. 2022 – present
- **M.S., Computer Science**, Vanderbilt University, Jan. 2020 – Dec. 2021
- **B.S., Physics**, University of Science and Technology of China, Aug. 2014 – Jun. 2018

## Work Experience

- **Research Intern**, Carnegie Mellon University, Aug. 2026 – present
- **Graduate Research Assistant**, University of Pittsburgh, Jan. 2022 – present
- **Research Assistant**, Shenzhen Institutes of Advanced Technology,<br>Chinese Academy of Sciences, Aug. 2018 – Apr. 2019

<h2><a href="/news/" style="color: inherit">News</a></h2>

{% include news.liquid limit=true %}

## Research

Deterministic defenses are reliable but expensive, and AI is efficient but unreliable. The two are complementary: AI decides where to focus, and deterministic methods decide what is true.

### Efficient Deterministic Defense

My published work makes deterministic defenses fast enough for real-world software:

- **FPN: Fast Pointer Nullification for Use-After-Free Prevention** (NDSS 2026). A runtime defense that stops use-after-free attacks in deployed C/C++ software. FPN tracks pointers in groups by their locality while keeping protection exact, which reduces memory overhead from about 173% to about 8%. [[Paper]](https://www.ndss-symposium.org/wp-content/uploads/2026-f753-paper.pdf) [[Code]](https://github.com/duyubo/Fast-Pointer-Nullification-NDSS-2026)
- **RTT-UAF: Reuse Time Tracking for Use-After-Free Detection** (ICS 2024). A sanitizer that finds use-after-free bugs during testing. RTT stores a small reuse count in the unused bits of each pointer, so no metadata needs to be propagated, which cuts runtime overhead by up to 7×. [[Paper]](https://doi.org/10.1145/3650200.3656606)

### Combining Deterministic Checking with AI

My ongoing work goes beyond pure deterministic defense and combines deterministic checking with AI:

- **Diagnostic vulnerability detection.** A sanitizer that reports not only where an out-of-bounds error occurs, but also which buffer is involved and where the pointer first goes out of bounds, so that developers and AI repair tools can find the root cause directly.
- **Verifying the reasoning of AI** (at Carnegie Mellon University). A sanitizer-style checker that compares each step of a large language model's vulnerability analysis with the real behavior of the program, to find where AI reasoning goes wrong and which code patterns mislead it.

<h2><a href="/publications/" style="color: inherit">Selected Publications</a></h2>

{% include selected_papers.liquid %}

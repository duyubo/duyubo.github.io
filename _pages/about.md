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
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
---

I am a Ph.D. candidate in Electrical and Computer Engineering at the [University of Pittsburgh](https://www.pitt.edu/), advised by Prof. Jun Yang. I am also a research intern at [Carnegie Mellon University](https://www.cmu.edu/), working with Prof. Limin Jia. I expect to graduate in **June 2027** and I am on the academic job market this year.

**My research makes software secure against memory-safety vulnerabilities by combining the guarantees of deterministic defenses with the efficiency of AI.** Deterministic defenses are reliable but expensive, and AI is efficient but unreliable. I believe the two are complementary: AI decides where to focus, and deterministic methods decide what is true. My work has three parts:

- **Efficient deterministic defense.** I design runtime defenses and sanitizers that keep exact security guarantees at a much lower cost, such as [FPN](https://www.ndss-symposium.org/wp-content/uploads/2026-f753-paper.pdf) (NDSS 2026) for use-after-free prevention and [RTT](https://doi.org/10.1145/3650200.3656606) (ICS 2024) for use-after-free detection.
- **Diagnostic vulnerability detection.** I build sanitizers that report not only where an error occurs but also its root cause, so that developers and AI repair tools can fix it directly (Witness, under review).
- **Verifying the reasoning of AI (ongoing, at CMU).** I apply the idea behind sanitizers to check each step of an LLM's vulnerability analysis against real program behavior, and to find which code patterns mislead it.

Looking ahead, I plan to work on AI-guided selective protection for deployed software, safe migration to memory-safe languages such as Rust, and deterministic checking of AI-generated code. You can read more in my [research statement](/assets/pdf/Yubo_Du_Research_Statement.pdf) and [CV](/assets/pdf/Yubo_Du_CV.pdf).

Before my Ph.D., I received an M.S. in Computer Science from [Vanderbilt University](https://www.vanderbilt.edu/) and a B.S. in Physics from the [University of Science and Technology of China](https://en.ustc.edu.cn/).

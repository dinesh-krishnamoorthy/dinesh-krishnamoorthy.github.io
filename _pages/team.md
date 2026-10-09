---
layout: page
title: group
permalink: /group/
nav: true
nav_order: 4

# ===============================================================
# Edit the lists below to update the page — no HTML needed.
# Photos go in /assets/img/group/ (square images work best, ~400x400 px).
# If a photo is missing, the person's initials are shown instead.
# ===============================================================
logo: /assets/img/group/collab_logo.png

pi:
  name: Dinesh Krishnamoorthy
  role: Associate Professor · Principal Investigator
  photo: /assets/img/prof_pic.jpg
  initials: DK

students:
  - name: Edvard Kjesbu Bahr
    initials: EB
    degree: MSc, NTNU
    photo: /assets/img/group/edvard.jpg
  - name: Dhruvkumar Patel
    initials: DP
    degree: MSc, Chalmers 
    photo: /assets/img/group/dhruv.jpg
  - name: Merlin Thinnes
    initials: MT
    degree: MSc, RWTH Aachen
    photo: /assets/img/group/merlin.jpg
  - name: Kjell Machalowsky
    initials: KM
    degree: MSc, TU Dortmund
    photo: /assets/img/group/kjell.jpg
  - name: Hari Prasad Varadarajan
    initials: HV
    degree: MTech, IIT Madras
    photo: /assets/img/group/hari.jpg
  - name: Christopher Orrico
    initials: CO
    degree: MSc, TU Eindhoven
    photo: /assets/img/group/christopher.jpg

themes:
  - title: Learning-based control
    text: Model predictive control with learned models and certified learning-based approximations of MPC, so that data-driven controllers come with guarantees.
  - title: Distributed optimization
    text: Algorithms that let many agents, units or subsystems reach good collective decisions while sharing only limited information.
  - title: Safe Bayesian optimization
    text: Sample-efficient, constraint-aware learning for systems where every experiment is expensive and unsafe actions are not an option.
  - title: Feedback-optimizing control
    text: Driving large-scale interconnected systems to their economic optimum in real time, directly from measurements.
---

<style>
  .collab { --c-accent: var(--global-theme-color, #2f6fa8); --c-text: var(--global-text-color, #222); --c-muted: var(--global-text-color-light, #6c757d); --c-line: var(--global-divider-color, rgba(0,0,0,.1)); --c-card: var(--global-card-bg-color, transparent); }
  .collab-hero { text-align: center; padding: 1.5rem 0 2rem; border-bottom: 1px solid var(--c-line); margin-bottom: 2.5rem; }
  .collab-hero img { max-width: 260px; width: 60%; height: auto; margin-bottom: 1.25rem; }
  .collab-hero h1 { font-size: 1.6rem; font-weight: 400; margin: 0 0 .5rem; line-height: 1.35; }
  .collab-hero h1 b { color: var(--c-accent); font-weight: 700; }
  .collab-hero .tagline { color: var(--c-muted); font-size: 1.05rem; max-width: 40rem; margin: 0 auto; }
  .collab h2 { font-size: 1.35rem; font-weight: 600; margin: 2.75rem 0 1.25rem; padding-bottom: .4rem; border-bottom: 2px solid var(--c-accent); display: inline-block; }
  .collab-themes { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1rem; }
  .collab-theme { border: 1px solid var(--c-line); border-top: 3px solid var(--c-accent); border-radius: 6px; padding: 1rem 1.1rem; background: var(--c-card); }
  .collab-theme h3 { font-size: 1rem; font-weight: 600; margin: 0 0 .4rem; }
  .collab-theme p { font-size: .92rem; color: var(--c-muted); margin: 0; line-height: 1.5; }
  .collab-people { display: grid; grid-template-columns: repeat(auto-fill, minmax(160px, 1fr)); gap: 1.75rem 1rem; }
  .collab-person { text-align: center; }
  .collab-avatar { position: relative; width: 132px; height: 132px; margin: 0 auto .75rem; border-radius: 50%; overflow: hidden; background: var(--c-accent); box-shadow: 0 0 0 3px var(--c-line); }
  .collab-avatar span { position: absolute; inset: 0; display: flex; align-items: center; justify-content: center; color: #fff; font-size: 2.2rem; font-weight: 300; letter-spacing: .05em; }
  .collab-avatar img { position: relative; width: 100%; height: 100%; object-fit: cover; }
  .collab-person .name { font-weight: 600; line-height: 1.3; }
  .collab-person .meta { font-size: .88rem; color: var(--c-muted); }
  .collab-pi { display: flex; align-items: center; gap: 1.5rem; flex-wrap: wrap; margin-bottom: 1rem; }
  .collab-pi .collab-avatar { margin: 0; width: 150px; height: 150px; }
  .collab-join { margin-top: 3rem; padding: 1.25rem 1.5rem; border-left: 4px solid var(--c-accent); background: var(--c-card); border-radius: 0 6px 6px 0; box-shadow: 0 0 0 1px var(--c-line); }
  .collab-join h2 { margin-top: 0; border: none; padding: 0; }
</style>

<div class="collab">

  <div class="collab-hero">
    <img src="{{ page.logo | relative_url }}" alt="COLLAB logo" onerror="this.style.display='none'">
    <h1><b>C</b>ontrol, <b>O</b>ptimization and <b>L</b>earning <b>Lab</b></h1>
    <p class="tagline">for collaborative decision making</p>
  </div>

  <p>
    COLLAB is a research group in the
    <a href="https://www.ntnu.edu/itk">Department of Engineering Cybernetics</a> at
    <a href="https://www.ntnu.edu">NTNU</a>, Trondheim. We work at the intersection of
    <b>optimization</b>, <b>control</b> and <b>machine learning</b>, developing methods that allow
    systems, and the many agents within them, to make good decisions together: safely,
    efficiently and in real time.
  </p>
  <p>
    Our work combines rigorous theory with real applications, from process and energy
    systems to other large-scale engineered systems, where decisions must be coordinated
    across many interacting parts.
  </p>

  <h2>What we work on</h2>
  <div class="collab-themes">
    {% for t in page.themes %}
    <div class="collab-theme">
      <h3>{{ t.title }}</h3>
      <p>{{ t.text }}</p>
    </div>
    {% endfor %}
  </div>

  <h2>People</h2>

  <div class="collab-pi">
    <div class="collab-avatar">
      <span>{{ page.pi.initials }}</span>
      <img src="{{ page.pi.photo | relative_url }}" alt="{{ page.pi.name }}" onerror="this.style.display='none'">
    </div>
    <div>
      <div class="name" style="font-size:1.15rem;font-weight:600">{{ page.pi.name }}</div>
      <div class="meta" style="color:var(--c-muted)">{{ page.pi.role }}</div>
    </div>
  </div>

  <h3 style="font-size:1.05rem;font-weight:600;margin:2rem 0 1.25rem;">PhD Students</h3>
  <div class="collab-people">
    {% for s in page.students %}
    <div class="collab-person">
      <div class="collab-avatar">
        <span>{{ s.initials }}</span>
        <img src="{{ s.photo | relative_url }}" alt="{{ s.name }}" loading="lazy" onerror="this.style.display='none'">
      </div>
      <div class="name">{{ s.name }}</div>
      <div class="meta">{{ s.degree }}</div>
      {% if s.topic %}<div class="meta"><i>{{ s.topic }}</i></div>{% endif %}
    </div>
    {% endfor %}
  </div>

  <div class="collab-join">
    <h2>Join us</h2>
    <p style="margin-bottom:0">
      We are always interested in hearing from motivated students and researchers.
      Open PhD and postdoc positions are announced on
      <a href="https://www.jobbnorge.no">Jobbnorge</a>. NTNU master's students interested in a
      project or thesis are welcome to get in touch by email.
    </p>
  </div>

</div>

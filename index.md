---
layout: default
title: Home
---

<section class="hero">
  <div class="code-block"><pre><span class="prompt">> </span><b>cat ./profile.yaml</b>
<span class="key">name</span>: <span class="str">"{{ site.data.profile.name }}"</span>
<span class="key">focus</span>: [<span class="str">"{{ site.data.profile.focus[0] }}"</span>, <span class="str">"{{ site.data.profile.focus[1] }}"</span>, <span class="str">"{{ site.data.profile.focus[2] }}"</span>]
<span class="key">lab</span>: <span class="str">"{{ site.data.profile.lab }}"</span> <span class="typ"># {{ site.data.profile.lab_details }}</span>
<span class="key">rank</span>: <span class="str">"{{ site.data.profile.rank }}"</span>
<span class="key">next</span>: <span class="str">"{{ site.data.profile.next }}"</span></pre></div>
  <div class="hero-text">
    <h1>{{ site.data.profile.hero_title }}</h1>
    <p>{{ site.data.profile.hero_desc }}</p>
    <div class="hero-btns"><a href="/assets/resume.pdf" download class="btn-ghost">Download Resume</a><a href="{{ site.data.profile.social.github }}" class="btn-ghost">GitHub</a></div>
    <p class="hero-note mono">{{ site.data.profile.hero_note }}</p>
  </div>
</section>

<section class="proof"><div class="eyebrow">Built in the lab. Tested like production.</div><div class="logos"><a href="{{ site.data.profile.social.tryhackme }}"><span>TryHackMe Top 3%</span></a><a href="{{ site.data.profile.social.hackthebox }}"><span>HackTheBox Pro</span></a><a href="#"><span>picoCTF 2024</span></a><a href="#"><span>Home Lab</span></a><a href="#"><span>BugCrowd</span></a></div></section>

<section id="projects" class="section">
  <h2>Projects</h2>
  <p class="sub">Reproducible lab with code, architecture, and detection evidence.</p>
  <div class="grid3">
    {% for project in site.projects %}
    <article class="card"><span class="tag">{{ project.tag }}</span><img src="{{ project.image }}" alt="{{ project.title }} — {{ project.description }}" loading="lazy"><h3>{{ project.title }}</h3><p>{{ project.description }}</p><span class="meta mono">{{ project.tech }}</span><div class="links">{% if project.github %}<a href="{{ project.github }}">GitHub</a>{% endif %}{% if project.writeup %}<a href="{{ project.writeup }}">Writeup</a>{% endif %}<a href="{{ project.url | relative_url }}">Details</a></div></article>
    {% endfor %}
  </div>
</section>

<section id="writeups" class="section">
  <h2 style="font-size:18px">Writeups</h2>
  <p class="sub">How I solved it and what to detect next.</p>
  <div class="writeups">
    {% assign sorted = site.writeups | sort: "date" | reverse %}
    {% for post in sorted %}
    <div class="writeup"><span class="date mono">{{ post.date | date: "%Y-%m-%d" }} · {{ post.read_time }}</span><div><h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a> <span>· {{ post.category }} · tags: {{ post.tags | join: ", " }}</span></h4><p class="excerpt">{{ post.excerpt }}</p></div><a class="arrow" href="{{ post.url | relative_url }}">→</a></div>
    {% endfor %}
  </div>
</section>

<section id="experience" class="section">
  <h2 style="font-size:18px">Experience</h2>
  <p class="sub">Lab work, competitions, and self-directed study.</p>
  <div class="timeline">
    {% assign exps = site.experience | sort: "order" %}
    {% for exp in exps %}
    <div class="timeline-item"><h4>{{ exp.title }}</h4><p class="org">{{ exp.org }}</p><p class="date mono">{{ exp.date_range }}</p><ul>{% for bullet in exp.bullets %}<li>{{ bullet }}</li>{% endfor %}</ul></div>
    {% endfor %}
  </div>
</section>

<section class="section">
  <h2>Skills</h2>
  <p class="sub">Tools used hands-on in labs and investigations.</p>
  <div class="skills">
    {% for group in site.data.skills %}
    <div class="skill-group"><h4>{{ group.group }}</h4><div class="pills">{% for item in group.items %}<span class="pill">{{ item }}</span>{% endfor %}</div></div>
    {% endfor %}
  </div>
</section>

<section class="section">
  <h2>Certifications</h2>
  <p class="sub">Certifications with verification links where available.</p>
  <div class="certs">
    {% for cert in site.certs %}
    <div class="cert"><span class="badge">{{ cert.status }}</span><h4>{{ cert.title }}</h4><p>{{ cert.issued }}</p><a href="{{ cert.verify_url }}" class="verify">{{ cert.verify_label }}</a></div>
    {% endfor %}
  </div>
</section>

<section id="contact" class="section">
  <h2>Contact</h2>
  <div class="contact">
    <div class="info">
      <p><b>Email</b><br><a class="mono" href="mailto:{{ site.data.contact.email }}">{{ site.data.contact.email }}</a></p>
      <p><b>GitHub</b><br><a class="mono" href="https://{{ site.data.contact.github }}">{{ site.data.contact.github }}</a></p>
      <p><b>LinkedIn</b><br><a class="mono" href="https://{{ site.data.contact.linkedin }}">{{ site.data.contact.linkedin }}</a></p>
      <p><b>TryHackMe</b><br><a class="mono" href="https://{{ site.data.contact.tryhackme }}">{{ site.data.contact.tryhackme }}</a> · Top 3%</p>
      <p><b>HackTheBox</b><br><a class="mono" href="https://{{ site.data.contact.hackthebox }}">{{ site.data.contact.hackthebox }}</a></p>
    </div>
    <form action="https://formspree.io/f/xplaceholder" method="POST"><input type="email" name="email" placeholder="Your email" required style="margin-bottom:12px"><textarea name="message" placeholder="Message — e.g., Internship, SOC role" required></textarea><br><button type="submit" class="btn-ghost" style="margin-top:12px;display:inline-block">Send message</button></form>
  </div>
</section>

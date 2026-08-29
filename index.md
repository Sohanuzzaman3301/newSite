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
    <div class="hero-btns"><a href="https://raw.githubusercontent.com/Sohanuzzaman3301/cv/main/cv_cyber.pdf" target="_blank" rel="noopener" class="btn-ghost">Download CV</a><a href="{{ site.data.profile.social.github }}" class="btn-ghost">GitHub</a></div>
    <p class="hero-note mono">{{ site.data.profile.hero_note }}</p>
  </div>
</section>

{% if site.projects.size > 0 %}
<section id="projects" class="section">
  <h2>Practical Projects</h2>
  <p class="sub">Reproducible lab with code, architecture, and detection evidence.</p>
  <div class="grid3">
    {% assign projects_sorted = site.projects | sort: "order" %}
    {% for project in projects_sorted %}
    <a href="{{ project.url | relative_url }}" class="card-link-wrapper" aria-label="Open {{ project.title }} details">
      <article class="card">
        <span class="tag">{{ project.tag }}</span>
        <img src="{{ project.image }}" alt="{{ project.title }} — {{ project.description }}" loading="lazy">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <span class="meta mono">{{ project.tech }}</span>
        <div class="links">
          {% if project.github %}<span>GitHub</span>{% endif %}
          {% if project.writeup %}<span>Writeup</span>{% endif %}
          <span>Details</span>
        </div>
      </article>
    </a>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.research.size > 0 %}
<section id="research" class="section">
  <h2>Research</h2>
  <p class="sub">Undergraduate thesis — EMBER2024 ensemble, 95%+ accuracy, SHAP explanations.</p>
  <div class="writeups">
    {% assign research_sorted = site.research | sort: "date" | reverse %}
    {% for post in research_sorted %}
    <div class="writeup">
      {% if post.image %}
      <img src="{{ post.image }}" alt="{{ post.title }}" style="width:100%;max-width:200px;height:auto;border-radius:4px;margin-bottom:8px">
      {% endif %}
      <span class="date mono">{{ post.date | date: "%Y-%m-%d" }} · {{ post.read_time }}</span>
      <div>
        <div class="meta-line">
          <span class="meta-tag">{{ post.category }}</span>
          {% if post.tags.size > 0 %}
          <span class="meta-tags">tags: {{ post.tags | join: ", " }}</span>
          {% endif %}
        </div>
        <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
        <p class="excerpt">{{ post.excerpt }}</p>
      </div>
      <a class="arrow" href="{{ post.url | relative_url }}">→</a>
    </div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.writeups.size > 0 %}
<section id="writeups" class="section">
  <h2 style="font-size:18px">Writeups</h2>
  <p class="sub">How I solved it and what to detect next.</p>
  <div class="writeups">
    {% assign sorted = site.writeups | sort: "date" | reverse %}
    {% for post in sorted %}
    <div class="writeup">
      <span class="date mono">{{ post.date | date: "%Y-%m-%d" }} · {{ post.read_time }}</span>
      <div>
        <div class="meta-line">
          <span class="meta-tag">{{ post.category }}</span>
          {% if post.tags.size > 0 %}
          <span class="meta-tags">tags: {{ post.tags | join: ", " }}</span>
          {% endif %}
        </div>
        <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
        <p class="excerpt">{{ post.excerpt }}</p>
      </div>
      <a class="arrow" href="{{ post.url | relative_url }}">→</a>
    </div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.experience.size > 0 %}
<section id="experience" class="section">
  <h2>Experience</h2>
  <p class="sub">Lab work, competitions, and self-directed study.</p>
  <div class="timeline">
    {% assign exps = site.experience | sort: "order" %}
    {% for exp in exps %}
    <div class="timeline-item">
      <div class="meta-line"><span class="meta-tag">Experience</span></div>
      <h4>{{ exp.title }}</h4>
      <p class="org">{{ exp.org }}</p>
      <p class="date mono">{{ exp.date_range }}</p>
      <ul>{% for bullet in exp.bullets %}<li>{{ bullet }}</li>{% endfor %}</ul>
    </div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.data.skills.size > 0 %}
<section class="section">
  <h2>Skills</h2>
  <p class="sub">Tools used hands-on in labs and investigations.</p>
  <div class="skills">
    {% for group in site.data.skills %}
    <div class="skill-group"><h4>{{ group.group }}</h4><div class="pills">{% for item in group.items %}<span class="pill">{{ item }}</span>{% endfor %}</div></div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.certs.size > 0 %}
<section class="section">
  <h2>Certifications</h2>
  <p class="sub">Certifications with verification links where available.</p>
  <div class="certs">
    {% for cert in site.certs %}
    <div class="cert"><span class="badge">{{ cert.status }}</span><h4>{{ cert.title }}</h4><p>{{ cert.issued }}</p><a href="{{ cert.verify_url }}" class="verify">{{ cert.verify_label }}</a></div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.data.education %}
<section class="section">
  <h2>Education</h2>
  <p class="sub">Formal training — thesis and focus.</p>
  <div class="timeline">
    <div class="timeline-item"><h4>{{ site.data.education.degree }}</h4><p class="org">{{ site.data.education.school }}</p><p class="date mono">{{ site.data.education.period }} · {{ site.data.education.honor }}</p><ul><li>{{ site.data.education.thesis }}</li><li>{{ site.data.education.focus }}</li></ul></div>
  </div>
</section>
{% endif %}

<section id="contact" class="section">
  <h2>Contact</h2>
  <div class="contact">
    <div class="info">
      <p><b>Email</b><br><a class="mono" href="mailto:{{ site.data.contact.email }}">{{ site.data.contact.email }}</a></p>
      <p><b>GitHub</b><br><a class="mono" href="https://{{ site.data.contact.github }}">{{ site.data.contact.github }}</a></p>
      <p><b>LinkedIn</b><br><a class="mono" href="https://{{ site.data.contact.linkedin }}">{{ site.data.contact.linkedin }}</a></p>
      <p><b>TryHackMe</b><br><a class="mono" href="https://{{ site.data.contact.tryhackme }}">{{ site.data.contact.tryhackme }}</a> · Top 2%</p>
      <p><b>HackTheBox</b><br><a class="mono" href="https://{{ site.data.contact.hackthebox }}">{{ site.data.contact.hackthebox }}</a></p>
    </div>
    <form id="contact-form" action="mailto:md.sohanuzzaman@proton.me" method="POST" enctype="text/plain" novalidate><input type="email" name="email" placeholder="Your email" required autocomplete="email" style="margin-bottom:12px"><input type="hidden" name="subject" value="Portfolio contact"><textarea name="message" placeholder="Message — e.g., Internship, SOC role" required rows="4"></textarea><div id="form-status" class="mono" style="font-size:12px;min-height:16px;margin-top:8px;color:var(--fog)" aria-live="polite"></div><button type="submit" id="contact-btn" class="btn" style="margin-top:12px">Send message</button></form>
<script>
(function(){
  const form=document.getElementById('contact-form'), btn=document.getElementById('contact-btn'), status=document.getElementById('form-status');
  if(!form) return;
  form.addEventListener('submit', (e)=>{
    const email=form.email.value.trim(), msg=form.message.value.trim();
    if(!email || !msg){ e.preventDefault(); status.textContent='Add email + message.'; status.style.color='var(--code-rust)'; return; }
    if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)){ e.preventDefault(); status.textContent='Check email format.'; status.style.color='var(--code-rust)'; return; }
    const body=encodeURIComponent(msg+'\n\nFrom: '+email);
    form.action='mailto:md.sohanuzzaman@proton.me?subject=Portfolio contact&body='+body;
    status.textContent='Opening email client…'; status.style.color='var(--fog)';
  });
})();
</script>
  </div>
</section>

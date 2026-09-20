---
layout: default
title: Home
---

<section class="hero">
  <div class="hero-text">
    <h1 class="hero-title">
    <span class="hero-title-static hero-role-dynamic" aria-label="Role">SOC</span>
    <span class="hero-title-dynamic"> Analyst</span>
    </h1>
    <p>Hi, My name is {{ site.data.profile.display_name }}, a cybersecurity professional focused on SOC operations, threat detection, and incident response. THM Top 2%, building SIEM labs and analyzing threats.</p>
    <div class="hero-role-dynamic" aria-hidden="true">
      <span class="hero-role">SOC</span>
    </div>
    <div class="hero-social">
      <a href="{{ site.data.profile.social.linkedin }}" target="_blank" aria-label="LinkedIn" class="social-link">
        <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
        <span>LinkedIn</span>
      </a>
      <a href="mailto:{{ site.data.contact.email }}" target="_blank" aria-label="Mail" class="social-link">
        <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="currentColor"><path d="M20 18h-2V9.25L12 13L6 9.25V18H4V6h1.2l6.8 4.25L18.8 6H20m0-2H4c-1.11 0-2 .89-2 2v12a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V6a2 2 0 0 0-2-2"/></svg>
        <span>Email</span>
      </a>
    </div>
  </div>
  <div class="hero-image">
    <div id="selfie"></div>
  </div>
</section>

<section class="about-section">
  <div class="about-inner">
    <img src="{{ '/assets/images/desktop-about.png' | relative_url }}" alt="Profile photo" class="about-photo">
    <div class="about-text">
      <h2>About</h2>
      <h3>A self taught with a lot of interest in Cyber Security</h3>
      <p>Hi, I am Sohanuzzaman Shanto, a self-taught analyst — ranked 1st at Wuhan Institute of Technology (First Class Scholarship). My interest has always been Cyber Security. I want security to be our top priority and to contribute to a more secure environment.</p>
      <p>I stay relevant by building SIEM labs with Wazuh, Suricata and Sysmon, solving CTFs on TryHackMe (Top 2%) and following the latest developments. I also analyze malware, tune detections and learn from every alert I triage.</p>
      <p>I aim to grow as a SOC analyst in detection engineering, threat hunting and incident response. I keep a close eye on new vulnerabilities and enjoy challenging myself with unsolved weaknesses — to make the world more secure for the next generation, even if it goes unnoticed.</p>
    </div>
  </div>
</section>

{% if site.projects.size > 0 %}
<section id="projects" class="section animate-on-scroll">
  <h2>Practical Projects</h2>
  <p class="sub">Reproducible lab with code, architecture, and detection evidence.</p>
  <div class="grid3">
    {% assign projects_sorted = site.projects | sort: "order" %}
    {% for project in projects_sorted %}
    <a href="{{ project.url | relative_url }}" class="card-link-wrapper animate-on-scroll" aria-label="Open {{ project.title }} details">
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

{% if site.writeups.size > 0 %}
<section id="writeups" class="section animate-on-scroll">
  <h2 style="font-size:18px">Writeups</h2>
  <p class="sub">How I solved it and what to detect next.</p>
  <div class="writeups">
    {% assign sorted = site.writeups | sort: "date" | reverse %}
    {% for post in sorted %}
    <div class="writeup animate-on-scroll">
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
<section id="experience" class="section animate-on-scroll">
  <h2>Experience</h2>
  <p class="sub">Lab work, competitions, and self-directed study.</p>
  <div class="timeline">
    {% assign exps = site.experience | sort: "order" %}
    {% for exp in exps %}
    <div class="timeline-item animate-on-scroll">
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
<section class="section animate-on-scroll">
  <h2>Skills</h2>
  <p class="sub">Tools used hands-on in labs and investigations.</p>
  <div class="skills">
    {% for group in site.data.skills %}
    <div class="skill-group animate-on-scroll"><h4>{{ group.group }}</h4><div class="pills">{% for item in group.items %}<span class="pill">{{ item }}</span>{% endfor %}</div></div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.certs.size > 0 %}
<section class="section animate-on-scroll">
  <h2>Certifications</h2>
  <p class="sub">Certifications with verification links where available.</p>
  <div class="certs">
    {% for cert in site.certs %}
    <div class="cert animate-on-scroll"><span class="badge">{{ cert.status }}</span><h4>{{ cert.title }}</h4><p>{{ cert.issued }}</p><a href="{{ cert.verify_url }}" class="verify">{{ cert.verify_label }}</a></div>
    {% endfor %}
  </div>
</section>
{% endif %}

{% if site.data.education %}
<section class="section animate-on-scroll">
  <h2>Education</h2>
  <p class="sub">Formal training — thesis and focus.</p>
  <div class="timeline">
    <div class="timeline-item animate-on-scroll"><h4>{{ site.data.education.degree }}</h4><p class="org">{{ site.data.education.school }}</p><p class="date mono">{{ site.data.education.period }} · {{ site.data.education.honor }}</p><ul><li>{{ site.data.education.thesis }}</li><li>{{ site.data.education.focus }}</li></ul></div>
  </div>
</section>
{% endif %}

<section id="contact" class="section animate-on-scroll">
  <h2>Contact</h2>
  <div class="contact">
    <div class="info">
      <p><b>Email</b><br><a class="mono" href="mailto:{{ site.data.contact.email }}">{{ site.data.contact.email }}</a></p>
      <p><b>GitHub</b><br><a class="mono" href="https://{{ site.data.contact.github }}">{{ site.data.contact.github }}</a></p>
      <p><b>LinkedIn</b><br><a class="mono" href="https://{{ site.data.contact.linkedin }}">{{ site.data.contact.linkedin }}</a></p>
      <p><b>TryHackMe</b><br><a class="mono" href="https://{{ site.data.contact.tryhackme }}">{{ site.data.contact.tryhackme }}</a> · Top 2%</p>
      <p><b>HackTheBox</b><br><a class="mono" href="https://{{ site.data.contact.hackthebox }}">{{ site.data.contact.hackthebox }}</a></p>
    </div>
    <div class="contact-form-wrap">
      <form id="contact-form" action="https://formspree.io/f/YOUR_FORMSPREE_ID" method="POST" novalidate>
        <input type="email" name="email" placeholder="Your email" required autocomplete="email">
        <input type="hidden" name="_subject" value="Portfolio contact">
        <input type="hidden" name="_captcha" value="false">
        <textarea name="message" placeholder="Message — e.g., Internship, SOC role" required rows="4"></textarea>
        <div id="form-status" class="mono" aria-live="polite"></div>
        <button type="submit" id="contact-btn" class="btn">Send message</button>
      </form>
      <p class="contact-fallback">Or email me directly at <a href="mailto:{{ site.data.contact.email }}">{{ site.data.contact.email }}</a></p>
    </div>
  </div>
</section>

<script>
(function(){
  const form=document.getElementById('contact-form'), btn=document.getElementById('contact-btn'), status=document.getElementById('form-status');
  if(!form) return;
  form.addEventListener('submit', async (e)=>{
    e.preventDefault();
    const email=form.email.value.trim(), msg=form.message.value.trim();
    if(!email || !msg){ status.textContent='Add email + message.'; status.style.color='var(--code-rust)'; return; }
    if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)){ status.textContent='Check email format.'; status.style.color='var(--code-rust)'; return; }
    btn.disabled=true; btn.textContent='Sending…'; status.textContent=''; 
    try {
      const res=await fetch(form.action, {method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({email,message:msg})});
      if(res.ok){ status.textContent='Message sent — I will reply soon.'; status.style.color='var(--code-teal)'; form.reset(); }
      else { status.textContent='Something went wrong. Try emailing directly.'; status.style.color='var(--code-rust)'; }
    } catch(err){ status.textContent='Network error. Try emailing directly.'; status.style.color='var(--code-rust)'; }
    btn.disabled=false; btn.textContent='Send message';
  });
})();
</script>

<template>
  <main>

    <!-- Hero -->
    <section class="section" id="hero">
      <p class="eyebrow">Software Engineer · Vancouver, BC</p>
      <h1>Akihito Sahashi</h1>
      <p class="hero-sub">8+ years building systems on AWS, Python, and Vue.js</p>
      <p class="summary">
        Experienced in large-scale log monitoring, cloud infrastructure, and full-stack
        development. Currently enrolled in the IT Co-op program in Vancouver — bringing
        Japanese engineering discipline to a Canadian work environment.
      </p>
      <div class="tags">
        <span class="tag accent">AWS</span>
        <span class="tag accent">Python</span>
        <span class="tag accent">Vue.js</span>
        <span class="tag">Kubernetes</span>
        <span class="tag">FastAPI</span>
        <span class="tag">Docker</span>
      </div>
      <!-- <a class="resume-link" href="/Akihito_Sahashi_Resume.pdf" download>Download resume</a> -->
    </section>

    <!-- Skills -->
    <section class="section" id="skills">
      <p class="section-label">Skills</p>
      <div class="skills-grid">
        <div v-for="group in skills" :key="group.title" class="skill-card">
          <p class="skill-card-title">{{ group.title }}</p>
          <ul>
            <li v-for="item in group.items" :key="item">{{ item }}</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Experience -->
    <section class="section" id="experience">
      <p class="section-label">Experience</p>
      <div class="timeline">
        <div v-for="job in jobs" :key="job.role" class="t-item">
          <div class="t-dot"></div>
          <div>
            <p class="t-period">{{ job.period }}</p>
            <p class="t-role">{{ job.role }}</p>
            <p class="t-company">{{ job.company }}</p>
            <p class="t-desc">{{ job.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section class="section" id="projects">
      <p class="section-label">Projects</p>
      <div class="proj-grid">
        <div v-for="proj in projects" :key="proj.name" class="proj-card">
          <p class="proj-name">{{ proj.name }}</p>
          <p class="proj-desc">{{ proj.desc }}</p>
          <div class="pills">
            <span v-for="tech in proj.techs" :key="tech" class="pill">{{ tech }}</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Education -->
    <section class="section" id="education">
      <p class="section-label">Education</p>
      <div v-for="edu in education" :key="edu.name" class="edu-item">
        <p class="edu-period">{{ edu.period }}</p>
        <p class="edu-school">{{ edu.school }}</p>
        <p class="edu-name">{{ edu.name }}</p>
        <p class="edu-degree">{{ edu.degree }}</p>
      </div>
    </section>

  </main>
</template>

<script setup>
const skills = [
  { title: 'Languages',     items: ['Python', 'JavaScript', 'Go', 'C/C++', 'Java', 'PHP'] },
  { title: 'Cloud & DevOps', items: ['AWS (EKS, S3, Lambda, EC2, DynamoDB)', 'Kubernetes', 'Docker'] },
  { title: 'Frameworks',    items: ['FastAPI', 'Vue.js', 'Node.js (Express)', 'Spring Boot'] },
  { title: 'Databases',     items: ['PostgreSQL', 'MySQL', 'SQL Server'] },
  { title: 'Tools',         items: ['Grafana', 'Graylog', 'Elasticsearch', 'Logstash', 'Fluent Bit', 'Git'] },
  { title: 'Languages',     items: ['Japanese (Native)', 'English (IELTS 6.0)'] },
]

const jobs = [
  {
    period: 'Apr 2020 – Jul 2024',
    role: 'System Engineer — Log Monitoring Platform',
    company: 'Systena Corporation · Osaka, Japan',
    desc: 'Administered a large-scale system processing 1 TB+ logs/day on AWS EKS. Rebuilt the platform with FastAPI and Pandas, projected to cut infrastructure costs by 50%.'
  },
  {
    period: 'Dec 2019 – Mar 2020',
    role: 'System Engineer — Gut Health Web Service',
    company: 'Systena Corporation · Osaka, Japan',
    desc: 'Developed a web app using Node.js and PostgreSQL to deliver personalized health insights based on examination kit data.'
  },
  {
    period: 'Apr 2019 – Nov 2019',
    role: 'System Engineer — Fall Detection System',
    company: 'Systena Corporation · Osaka, Japan',
    desc: 'Built a real-time fall-detection and alert system in C++ with camera monitoring for railway station platforms.'
  },
  {
    period: 'Feb 2018 – Mar 2019',
    role: 'System Engineer — Communication Robot',
    company: 'Systena Corporation · Osaka, Japan',
    desc: 'Developed an interactive robot in C/C++ with collision avoidance and person detection to support children\'s social learning.'
  },
  {
    period: 'Nov 2017 – Jan 2018',
    role: 'System Engineer — Wayfinding Signage',
    company: 'Systena Corporation · Osaka, Japan',
    desc: 'Built a wayfinding web app on digital signage alongside a humanoid robot, enabling tourists to search nearby landmarks and routes.'
  },
  {
    period: 'Sep 2017 – Oct 2017',
    role: 'System Engineer — Route Search Chatbot',
    company: 'Systena Corporation · Osaka, Japan',
    desc: 'Developed a chatbot on a messaging platform using PHP on Heroku, enabling users to search for landmark routes via chat.'
  },
]

const projects = [
  { name: 'Log Monitoring Platform', desc: '1 TB/day log pipeline on AWS EKS with real-time failure detection for 100+ users.', techs: ['Python', 'FastAPI', 'AWS EKS', 'Vue.js'] },
  { name: 'Gut Health Web Service', desc: 'Personalized health insights app delivering results based on examination kit data.', techs: ['Node.js', 'Express', 'PostgreSQL'] },
  { name: 'Fall Detection System', desc: 'Real-time fall-detection and alerts with camera monitoring for station platforms.', techs: ['C++', 'Camera API'] },
  { name: 'Communication Robot', desc: 'Interactive robot with collision avoidance and person detection for children\'s learning.', techs: ['C', 'C++', 'Embedded'] },
  { name: 'Wayfinding Signage', desc: 'Digital signage web app alongside a humanoid robot for tourist route search.', techs: ['HTML', 'CSS', 'JavaScript'] },
  { name: 'Route Search Chatbot', desc: 'Messaging platform chatbot for landmark route search, deployed on Heroku.', techs: ['PHP', 'Heroku'] },
]

const education = [
  { period: 'Oct 2025 – Sep 2027 (Expected)', school: 'Canadian College, Vancouver, BC, Canada', name: 'Information Technology and Co-op', degree: 'Diploma' },
  { period: 'Apr 2014 – Mar 2016', school: 'Kobe Institute of Computing-College of Computing, Hyogo, Japan', name: 'Information Technology', degree: 'Diploma' },
  { period: 'Apr 2010 – Mar 2014', school: 'Ryukoku University, Shiga, Japan', name: 'Sociology', degree: 'Bachelor' },
]
</script>
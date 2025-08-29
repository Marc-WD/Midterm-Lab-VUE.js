<script setup>
import profile from '../assets/profile.jpg'
import { reactive } from 'vue'

const data = reactive({
  header: { name: 'Marc Canlas', title: 'IT Web Developer', image: profile },
  personal: { name: 'Marc Canlas', age: 20, email: 'm4canlas@gmail.com', phone: '09278401426' },
  skills: ['HTML/CSS', 'JavaScript', 'Java', 'PHP'],
  education: [{ school: 'Holy Angel University', degree: '' }],
  experience: [{ role: '', company: '', desc: 'I am a passionate Web Developer with a strong foundation in building responsive, user-friendly websites and web applications. I enjoy turning ideas into functional and visually appealing digital experiences by combining clean code with creative design.' }]
})
</script>

<template>
  <div class="container">
    <div class="header">
      <div class="img-area"><img :src="data.header.image" alt="Profile" /></div>
      <h1>{{ data.header.name }}</h1>
      <h3>{{ data.header.title }}</h3>
    </div>

    <div class="main">
      <div class="left">
        <h2 class="section-title">Personal Information</h2>
        <p><strong>Name:</strong> {{ data.personal.name }}</p>
        <p><strong>Age:</strong> {{ data.personal.age }}</p>
        <p><strong>Email:</strong> {{ data.personal.email }}</p>
        <p><strong>Phone:</strong> {{ data.personal.phone }}</p>

        <h2 class="section-title">Skills</h2>
        <ul>
          <li v-for="(skill, i) in data.skills" :key="i">{{ skill }}</li>
        </ul>

        <h2 class="section-title">Education</h2>
        <div v-for="(e, i) in data.education" :key="i">
          <h3>{{ e.school }}</h3>
          <p v-if="e.degree">{{ e.degree }}</p>
        </div>
      </div>

      <div class="right">
        <h2 class="section-title">About Me</h2>
        <div v-for="(w, i) in data.experience" :key="i">
          <h3>{{ w.role }}</h3>
          <p>{{ w.company }}</p>
          <p>{{ w.desc }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

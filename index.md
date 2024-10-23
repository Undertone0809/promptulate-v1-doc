---
# https://vitepress.dev/reference/default-theme-home-page
layout: home

hero:
  name: "Promptulate v1" 
  text: "🚀Lightweight AI Native development framework."
  tagline: Build your LLM Agent Application in a pythonic way.
  image:
    src: /logo.png
    alt: Promptulate
  actions:
    - theme: brand
      text: What's pne
      link: /get_started/intro
    - theme: alt
      text: Quick Start
      link: /get_started/quick_start
    - theme: alt
      text: Github
      link: https://github.com/undertone0809/promptulate

features:
  - title: 📖 Easy to learn
    details: Consolidates all capabilities into a single, intuitive function, making it effortless to grasp and implement complex AI functionalities.
  - title: 🚀 Fast to code
    details: Employs straightforward logic and clear syntax, enabling rapid development and easy comprehension for efficient AI application building.
  - title: 🧰 Ready for production
    details: Offers seamless compatibility with popular language models and provides a comprehensive suite of production-ready components for robust, scalable AI solutions.
---

<script setup>
import { onMounted } from 'vue'
import { useData } from 'vitepress'

const { site, theme } = useData()

onMounted(() => {
  if (typeof window !== 'undefined') {
    const notification = document.createElement('div')
    notification.innerHTML = `
      🎉 Promptulate v2 has been released!
      <a href="https://www.promptulate.cn" style="color: #d47959; text-decoration: underline;">Check it out!</a>
      <span style="position: absolute; top: 5px; right: 10px; cursor: pointer; font-size: 18px;">&times;</span>
    `
    notification.style.cssText = `
      position: fixed;
      top: 80px;
      left: 50%;
      transform: translateX(-50%);
      background-color: white;
      color: #333;
      text-align: center;
      padding: 10px 15px;
      border-radius: 20px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      z-index: 1001;
      font-size: 14px;
      max-width: 300px;
    `

    document.body.appendChild(notification)

    // Close button functionality
    const closeButton = notification.querySelector('span')
    closeButton.onclick = function(e) {
      e.stopPropagation()
      notification.style.display = 'none'
    }

    // Redirect on clicking the notification (except for the close button)
    notification.onclick = function(e) {
      if (e.target !== closeButton) {
        window.location.href = 'https://www.promptulate.cn'
      }
    }
  }
})
</script>

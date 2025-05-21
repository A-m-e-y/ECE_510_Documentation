# 👋 Welcome to My Course Journal

Hi, I'm **Your Name**, and this is my learning journey for the course _"Course Title"_ taken during **Spring/Fall 2025**.

Here you'll find:

- 📘 Weekly Challenge Logs  
- 🚀 Project Journal Progress  

---

## 🧭 Navigate

<a href="weekly_challenges.html"><button>📘 Weekly Challenges</button></a>
<a href="project_journal.html"><button>🚀 Project Journal</button></a>

<script>
window.onload = function () {
  const btn = document.createElement('button');
  btn.innerHTML = '⬆️';
  btn.style.position = 'fixed';
  btn.style.bottom = '20px';
  btn.style.right = '20px';
  btn.style.padding = '10px 15px';
  btn.style.border = 'none';
  btn.style.borderRadius = '50%';
  btn.style.backgroundColor = '#007acc';
  btn.style.color = 'white';
  btn.style.fontSize = '20px';
  btn.style.cursor = 'pointer';
  btn.title = 'Scroll to top';

  btn.onclick = function () {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  };

  document.body.appendChild(btn);
}
</script>

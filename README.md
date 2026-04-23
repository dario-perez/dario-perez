<p align="center">
  <img src="https://github.com/dario-perez/dario-perez/blob/main/banner.png?raw=true" alt="Dario Perez - Backend & DevOps In Training" width="100%">
</p>

# Hi there! I'm Darío 👋

### 🛠️ Backend Developer Jr
Building APIs with Python & FastAPI | Exploring DevOps fundamentals.


<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=dario-perez&theme=radical" />
</p>


### Technical Focus
- 🐍 **Backend:** Working with Python (OOP, Automation & **Data Validation**).
- 📡 **APIs:** Learning RESTful design, CRUD operations, and **Pydantic** validation.
- 🐳 **DevOps:** Containerization with Docker & Environment Management.
- 🐧 **Systems:** Linux administration and Command Line proficiency.


### Featured Project
- **[Server Inventory API](https://github.com/dario-perez/backend-devops-pathway/tree/main/logic-exercises/backend-phase-1/01-fastapi-server-manager)**: **(New!)** My first API built with FastAPI. It manages a server database with full CRUD capabilities and professional directory structure.


### Featured Logic Exercises (Object-Oriented Programming)
Recently, I've been focusing on **Object-Oriented Programming** with these projects:
- [Server System](https://github.com/dario-perez/backend-devops-pathway/tree/main/logic-exercises/python/week-2/oop-basics): Managed server inheritance and automated reboots.
- [Infrastructure Manager](https://github.com/dario-perez/backend-devops-pathway/tree/main/logic-exercises/python/week-2/oop-practice/14-infrastructure-manager): Robust system with IP validation and error handling (Try/Except) for network integrity.

import os
import requests

def fetch_activity():
    username = "dario-perez"
    url = f"https://api.github.com/users/{username}/events/public"
    response = requests.get(url)
    if response.status_code != 200:
        return "⚠️ No se pudo obtener la actividad reciente."
    
    events = response.json()
    activity_lines = []
    
    # Procesar los últimos 5 eventos de commit
    count = 0
    for event in events:
        if event["type"] == "PushEvent" and count < 5:
            repo_name = event["repo"]["name"]
            # Obtener el mensaje del último commit en ese push
            commit_msg = event["payload"]["commits"][-1]["message"].split('\n')[0]
            repo_url = f"https://github.com/{repo_name}"
            
            line = f"- 🚀 **{repo_name}**: {commit_msg} ([view]({repo_url}))"
            activity_lines.append(line)
            count += 1
            
    return "\n".join(activity_lines) if activity_lines else "No hay actividad reciente."

def update_readme(new_activity):
    with open("README.md", "r", encoding="utf-8") as f:
        content = f.read()

    start_tag = ""
    end_tag = ""
    
    start_idx = content.find(start_tag) + len(start_tag)
    end_idx = content.find(end_tag)

    if start_idx == -1 or end_idx == -1:
        print("Error: No se encontraron los comentarios ancla en el README.")
        return

    new_content = content[:start_idx] + "\n" + new_activity + "\n" + content[end_idx:]
    
    with open("README.md", "w", encoding="utf-8") as f:
        f.write(new_content)

if __name__ == "__main__":
    activity = fetch_activity()
    update_readme(activity)


### My GitHub Stats
<p align="center">
  <img height="170em" src="https://github-readme-stats-psi-brown-29.vercel.app/api?username=dario-perez&show_icons=true&theme=radical&include_all_commits=true&hide_border=true&cache_seconds=86400" />
  <img height="170em" src="https://github-readme-stats-psi-brown-29.vercel.app/api/top-langs/?username=dario-perez&layout=compact&theme=radical&hide_border=true&cache_seconds=86400&hide=html,css" />
</p>


### How to reach me
- **LinkedIn:** [LinkedIn](https://www.linkedin.com/in/darioperez-dev/)
- **Email:** [darioperez.2105@gmail.com](mailto:darioperez.2105@gmail.com)


### Professional Goals
- 🇰🇷 Passionate about high-scale engineering cultures, with a particular interest in the South Korean tech ecosystem.
- 📈 Committed to continuous growth within international, high-performance backend teams.
- 🚀 Focused on mastering system reliability and scalable architecture.

---

> "Logic is the beginning of wisdom, not the end." 🖖

<!--
**dario-perez/dario-perez** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

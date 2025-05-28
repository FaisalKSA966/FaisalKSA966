<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Faisal | Developer Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #0f0f0f;
      --card: #1e1e1e;
      --accent: #00c2ff;
      --text: #eaeaea;
      --subtle: #aaa;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--bg);
      color: var(--text);
      padding: 40px 20px;
      display: flex;
      justify-content: center;
    }

    .container {
      max-width: 900px;
      width: 100%;
    }

    .profile {
      text-align: center;
      margin-bottom: 40px;
    }

    .profile img {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      border: 3px solid var(--accent);
      box-shadow: 0 0 15px #00c2ff50;
      margin-bottom: 20px;
    }

    .profile h1 {
      font-size: 2.8rem;
      font-weight: 800;
      color: var(--accent);
    }

    .meta {
      margin-top: 10px;
      color: var(--subtle);
      font-size: 1rem;
    }

    section {
      margin-bottom: 40px;
    }

    h2 {
      font-size: 1.8rem;
      border-bottom: 2px solid var(--accent);
      padding-bottom: 6px;
      margin-bottom: 15px;
      font-weight: 600;
    }

    ul {
      list-style: disc;
      padding-left: 20px;
      line-height: 1.8;
    }

    .tech-icons img {
      width: auto;
      max-height: 45px;
      margin: 8px 10px 0 0;
      vertical-align: middle;
    }

    .contact {
      background-color: var(--card);
      padding: 20px;
      border-radius: 12px;
      text-align: center;
    }

    .contact p {
      font-size: 1.2rem;
      color: var(--accent);
    }

    @media (max-width: 600px) {
      .profile h1 {
        font-size: 2rem;
      }

      h2 {
        font-size: 1.4rem;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="profile">
      <img src="https://avatars.githubusercontent.com/u/200758656?v=4" alt="Faisal Profile Photo" />
      <h1>Faisal</h1>
      <div class="meta">Age: 13 &nbsp;|&nbsp; Saudi &nbsp;|&nbsp; Eastern Province</div>
    </div>

    <section>
      <h2>About Me</h2>
      <p>
        I am a 13-year-old Saudi developer with a focus on JavaScript and backend technologies.
        I specialize in building Discord bots and actively explore areas such as full-stack web development,
        game development using Unreal Engine, and cybersecurity. I'm passionate about automation and AI tools that solve real problems efficiently.
      </p>
    </section>

    <section>
      <h2>Education</h2>
      <ul>
        <li>High-achieving student</li>
        <li>Member of the <strong>Mawhiba</strong> (Gifted Program), Saudi Arabia</li>
      </ul>
    </section>

    <section>
      <h2>Technical Skills</h2>
      <ul>
        <li>JavaScript (advanced)</li>
        <li>Node.js, Express, APIs</li>
        <li>Discord bot development</li>
        <li>Frontend & backend web development</li>
        <li>Game development using Unreal Engine</li>
        <li>Automation tools and scripting</li>
      </ul>
    </section>

    <section>
      <h2>Tech Stack</h2>
      <div class="tech-icons">
        <img src="https://skillicons.dev/icons?i=js,nodejs,html,css,git,github,unreal,vscode,linux" alt="Tech Stack Icons" />
      </div>
    </section>

    <section>
      <h2>Language Proficiency</h2>
      <ul>
        <li>Arabic: Native (Saudi dialect)</li>
        <li>English: Fluent (Scottish & American accents)</li>
        <li>Currently learning Russian and Spanish</li>
      </ul>
    </section>

    <section>
      <h2>Projects & Roles</h2>
      <ul>
        <li>Founder and lead developer of <strong>OpticAI</strong></li>
        <li>Owner of <strong>Flowline</strong> (startup in early development)</li>
      </ul>
    </section>

    <section class="contact">
      <h2>Contact</h2>
      <p>Discord: <strong>6j.</strong></p>
    </section>
  </div>
</body>
</html>

<h1 align = "center">We are IEEE-VIT. 🚀</h1>
<p align="center">
  <img src="https://github.com/IEEE-VIT/.github/blob/main/profile/IEEE%20Space.png">
</p>

<p align="center">
  <b><i>IDEATE. INNOVATE. INSPIRE.</i></b>  
</p>

<p align="center">
  IEEE VIT is a community comprising the most persevering of student developers, designers, and managers. Our ever growing arsenal of projects covers a range of domains and technologies, from Web Development and App Development to Machine Learning and Electronics.
</p>

<p align="center">
  We 💙 open-source development. If you're here, chances are you do too! Contribute to our <a href="https://github.com/orgs/IEEE-VIT/repositories">projects</a>!  
</p>

---

<div align="center">
  <img src="./october.png" alt="Happy October Meme" style="width: 50%; height: auto;">
  <br><br>IEEE offers a range of exciting projects across diverse disciplines, ready for your innovative touch in 2026! 🥳
</div>
<br>
<div align="center">
  <b>October @ IEEE VIT is about showing up, shipping, and getting a little braver with every pull request.</b>
</div>

<div align="center">
  <br>
  The leaves are turning, and the repos are wide open. Fresh contributors, first PRs, and old projects getting a second life.</br>

  <br>October is not about being fearless.</br>
  It's about doing the scary thing anyway.  
  The kind of month where you open the issue you've been avoiding, ask the question you thought was too basic, and push the commit before it feels perfect. Spooky? A little. Worth it? Always.
</div>

<div align="center">
  <br>
  <br>"Every great project starts as an open issue and a little courage.
  <br>Fork it. Break it. Fix it. Share it.
  <br>Open doors. Open source. Open minds.
  <br>Because the scariest code is the code that never gets written."
</div>

<div align='center'>

  <a href="https://www.youtube.com/watch?v=iggmiF7DNoM" target="_blank">🎃</a>
</div>

<div align="center">
 <h2>October's Project of the Month</h2>

  <b>
    <a href="https://github.com/IEEE-VIT/ParleyLab">ParleyLab</a>
  </b>

  <br>
  ParleyLab is an AI powered negotiation training simulator. Users practise realistic scenarios such as salary offers, freelance contracts, apartment leases, and equity splits against an AI opponent with its own hidden goals and walk away point. After every move, an independent critic agent coaches the user in real time using established negotiation theory, so people can rehearse high stakes conversations safely and learn concepts like anchoring and BATNA by actually using them.

  The core architectural decision is the decoupling of strategy from language: a trained PPO reinforcement learning policy decides what the opponent does (hold firm, concede, bluff, or walk away), and an LLM independently turns that decision into natural, persona specific dialogue. This keeps the opponent's behaviour principled and consistent while its conversation stays human.
  </br>
  <br>

## Features

* **RL driven opponent:** A Stable Baselines3 PPO agent, trained for 1M timesteps, picks one of five strategic actions every turn: hold firm, concede small, concede large, bluff, or walk away. The opponent follows a learned policy, not a script.
* **Strategy decoupled from language:** The RL policy decides what to do and the LLM decides how to say it. Strategy stays consistent while dialogue stays natural.
* **Real time critic feedback:** After every move, a critic agent returns structured feedback with strengths, weaknesses, an actionable suggestion, and a concept tag such as anchoring, concession pacing, or BATNA signalling.
* **Hidden state enforcement:** The opponent's target, BATNA, and persona are held server side and never sent to the client. They are revealed only at the end, alongside a score that blends outcome quality and move quality.
* **Plug and play scenarios:** Four built in scenarios ship as JSON files, with values randomised by ±15% per session and multi currency support. Adding a new scenario needs no code changes.
* **Pluggable, free LLM backends:** Gemini, Groq, and local Ollama are supported through a single router with template fallbacks. Opponent and critic calls run in parallel, cutting per turn latency by 3 to 5 seconds.
  </br>

</div>

<div align="center">
  <img src="./diagram.png" alt="ParleyLab Architecture Diagram" width="60%">
  <br><br>
  <b>Architecture Overview</b>
<br>
A Next.js frontend sends each negotiation move to a FastAPI backend, where an orchestrator runs a six stage turn pipeline. An LLM move parser converts the user's message into a structured move, which updates a 7 dimensional observation vector that the PPO policy uses to pick the opponent's strategic action in under a millisecond on CPU. The opponent agent, which voices that action, and the critic agent, which grades the user's move, then run in parallel through a shared LLM router (Gemini, Groq, or Ollama). Session state, including the opponent's hidden goals, lives in an in memory store and is exposed only through the end of session reveal and scoring.
</div>

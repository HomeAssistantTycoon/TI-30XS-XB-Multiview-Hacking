# TI-30XS/XB Multiview Hacking
Welcome to the only place on the internet where people are still trying to hack Texas Instruments scientific calculators!
## Contents
<details>
  <summary>Our Goal</summary>

  Our Goal is simple: To achieve arbitrary code execution (ACE) on the TI‑30XS/XB MultiView. This will allow the user to run their own code on the calculator. There are many steps on the road to ACE, generally involving a series of glitches. The most important part is understanding how the calculator’s memory and pointers behave when glitches occur, since that’s the key to turning harmless bugs into real control.
</details>

<details>
  <summary>Progress</summary>

  Currently, we've discovered a buffer‑overflow‑like glitch with the help of [ndeineko](https://github.com/ndeineko), which can be used to expose and use hidden calculator functions such as **lcm(** and **gcd(**—normally inaccessible on the TI‑30XS MultiView.
</details>

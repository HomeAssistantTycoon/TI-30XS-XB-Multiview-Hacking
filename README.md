# TI-30XS/XB Multiview Hacking
Welcome to the only place on the internet where people are still trying to hack Texas Instruments scientific calculators!
## Contents
<details>
  <summary>Our Goal</summary>

  Our Goal is simple: To achieve arbitrary code execution (ACE) on the TI‑30XS/XB MultiView. This will allow the user to run their own code on the calculator. There are many steps on the road to ACE, generally involving a series of glitches. The most important part is understanding how the calculator’s memory and pointers behave when glitches occur, since that’s the key to turning harmless bugs into real control.
</details>

<details>
  <summary>Progress</summary>

Currently, we’ve discovered a buffer‑overflow‑like glitch with the help of [ndeineko](https://github.com/ndeineko) , which can be used to expose and use hidden calculator functions such as lcm( and gcd(—normally inaccessible on the TI‑30XS MultiView. We’re now working to figure out if this same overflow can overwrite any RAM value that the firmware later interprets as a token ID, mode ID, or parser state, since those “pseudo‑pointers” are what the calculator uses to decide which internal routine to run. If any of those control‑flow values can be safely corrupted, it would open the door to deeper glitches and possibly the first real steps toward ACE.
</details>

Info

Currenty I am utilizing a glitch to explore characters by inputting their byte code. I found something strange when I input bytes 07 and 08 leading to an overflow error, and thus making very wierd and unintended characters to appear on the screen, including a complete sentence. This creates a very glitchy state, and it often leads to the calculator freezing. I am going to continue exploring this strange glitch and I will try to determine certain triggers in it.

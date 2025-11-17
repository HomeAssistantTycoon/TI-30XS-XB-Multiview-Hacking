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

Currenty I am utilizing a glitch to explore characters by inputting their byte code. I found something strange when I input bytes 07 and 08 leading to an overflow error, and thus making very wierd and unintended characters to appear on the screen, including a complete sentence. This creates a very glitchy state, and it often leads to the calculator freezing. I am going to continue exploring this strange glitch and I will try to determine certain triggers in it. For anyone who wants to replicate this and study it, follow this modified guide originally provided by ndeineko: 

"Below is a procedure for accessing the overflow glitch. In the unlikely case that the constant value is already enabled (the letter K is displayed at the top of the screen), it must be disabled before executing the steps. This procedure seems reliable, but there might still be unforeseen side effects, so if the screen freezes, pressing on and clear simultaneously can always "reset" the calculator.

Step 1 : access column 3, row 61 of the data editor

Press on to turn on the calculator.
Press data to access the data editor.
Press ◀.
(40 times) Press 0 enter.
At this point, the bottom of the screen should show L3(41)=    . If it's not the case, insert or delete the right amount of cells to get 40 lines of zeros.
Press ◀ sto▸ data 3 enter ▲ 0 enter ▶ 0 enter 0 enter enter.
(18 times) Press 0 enter.
At this point, the bottom of the screen should show L3(61)=    .
Step 2 : overwrite the constant value

Press 1 0 0 0 0 0 0 7 0 8 π to write 1000000708π in that cell. Make sure there are 6 zeros before 708.
Press enter.
Step 3 : clear the data editor

Press data 4.
Step 4 : extract the error

Press 2nd ÷ delete enter enter clear.
Step 5 : clear the constant value

Press 2nd ÷ 2nd ÷ clear enter.
Step 6 : See the wierd junk

Type in any math problem i.e. 1+1 and press enter and then scroll through the junk characters.
Enjoy!"


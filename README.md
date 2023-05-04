Download Link: https://assignmentchef.com/product/solved-csci-2312-001-object-oriented-programming-assignment-1
<br>
<strong>Assignment 1</strong>




Read the following description of the Battleship game and do a ROC(k)ET decomposition.  For the Test phase, describe what testing you would need to do on each function to feel like the major threads of the function were tested properly.




<strong>Background</strong>

For your CSCI 2312 Project, you will develop a simple battleship game. Battleship is a <a href="https://en.wikipedia.org/wiki/Guessing_game">guessing game</a> for two players. It is played on four grids.  Two grids (one for each player) are used to mark each players’ fleets of ships (including battleships). The locations of the fleet (these first two grids) are concealed from the other player so that they do not know the locations of the opponent’s ships. Players alternate turns by ‘firing torpedoes’ at the other player’s ships. The objective of the game is to destroy the opposing player’s entire fleet. In our game, ‘firing a torpedo’ will be allowing the player to take a guess at where on the grid their opponent may have placed a ship.  For the Project, you will develop a single player Battleship game where the human player will play against the computer.







<strong>Simplified Requirements for this assignment (The Project will have more detailed requirements)</strong>




For this assignment, we will only be doing a ROC(K)ET analysis of the game setup portion of Battleship which includes setting up the game board (2 grids must be created to place ships on) and allowing the players to place their ships.




The game setup uses one grid for each player to ‘secretly’ place their ships. The grids are 10 by 10.  The individual squares in the grid are identified by the x coordinate (indicated by a letter) followed by the y coordinate (indicated by a number).




Before play begins, each player secretly arranges their ships on their grid.  This will be done by prompting the player for the location and the orientation of each type of ship.

Each ship occupies a certain number of consecutive squares on the grid (sizes of ships are in the following table), arranged either horizontally or vertically. The number of squares for each ship is determined by the type of the ship. The ships cannot overlap so only one ship can occupy any given square in the grid.  The types and numbers of ships allowed are the same for each player and consist of 1 of each of the following:




<table>

 <tbody>

  <tr>

   <td width="169">Ship Type</td>

   <td width="125">Number of Grid Squares</td>

  </tr>

  <tr>

   <td width="169">Carrier</td>

   <td width="125">5</td>

  </tr>

  <tr>

   <td width="169">Battleship</td>

   <td width="125">4</td>

  </tr>

  <tr>

   <td width="169">Cruiser</td>

   <td width="125">3</td>

  </tr>

  <tr>

   <td width="169">Submarine</td>

   <td width="125">3</td>

  </tr>

  <tr>

   <td width="169">Destroyer</td>

   <td width="125">2</td>

  </tr>

 </tbody>

</table>







The following is an example of a game setup for one of the players with a Carrier placed at location B3 in the horizontal direction, a Battleship placed at J5 in the vertical direction, a Cruiser placed at A10 in the horizontal direction, a Submarine at location C6 in the vertical direction, and a Destroyer placed at location I4 with a horizontal direction.










A       B      C      D        E         F       G       H        I        J

<table>

 <tbody>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32">C</td>

   <td width="34">C</td>

   <td width="36">C</td>

   <td width="36">C</td>

   <td width="36">C</td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36">D</td>

   <td width="36">D</td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36">B</td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34">S</td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36">B</td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34">S</td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36">B</td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34">S</td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36">B</td>

  </tr>

  <tr>

   <td width="37"> </td>

   <td width="32"> </td>

   <td width="34"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

  </tr>

  <tr>

   <td width="37">Cr</td>

   <td width="32">Cr</td>

   <td width="34">Cr</td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

   <td width="36"> </td>

  </tr>

 </tbody>

</table>




1




2




3




4




5




6




7




8




9




10










<strong>ROCkET Analysis</strong>

(R)ead the Entire Problem

(O)utline

(C)ode a small functionality

(E)valuate small functionality

(T)est entire program

<strong> </strong>

Remember that this is an iterative process with a focus on breaking into small manageable components.  For this assignment, your outline will be placed in //line comments. Think of individual functions for your high-level outline. Instead of Code, you will place pseudocode (in line or block comments) tabbed a level in from the outline. Describe your parameters (inputs) and expected output.  Give enough information to describe the functionality of each outlined functionality. For the Evaluate portion, write a test plan, on how you will evaluate this functionality (and what you will do with major errors). Focus more on plain English or pseudocode instead of C++ syntax.

Example:

//Print Fleet Grid

//PARAMETERS: Fleet Grid

//RETURN VALUE: None

/*Start at top corner.

For each column

For each row

print value of cell

print a tab

print a newline /*

/*TEST PLAN:

Write a 2X2 grid on paper. Fill with ‘A’,’B’ in first row, ‘C’, ‘D’ in second row

Test function with those inputs

Validate through print statements (and later debugging) that rows and columns are as expected




<strong>Grading Rubric</strong>

Hand in a single .cpp file. Ensure your name is on <u>every</u> file. You may (and are encouraged to) discuss general strategy with classmates (or other help) but you MUST document all extra help other than the textbook (including web sites) with comments. Failure to document extra help may result in a zero for the assignment. While you should help your classmates, stop short of giving exact lines of code or pseudocode. If we can’t determine who shared and who copied, we may give you both a zero for the assignment.

<strong> </strong>

<table>

 <tbody>

  <tr>

   <td width="312">Outline Framework</td>

   <td width="48">5</td>

  </tr>

  <tr>

   <td width="312">Pseudocode</td>

   <td width="48">10</td>

  </tr>

  <tr>

   <td width="312">Test Plan</td>

   <td width="48">5</td>

  </tr>

 </tbody>

</table>






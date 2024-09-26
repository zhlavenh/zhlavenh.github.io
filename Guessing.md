```mermaid
flowchart TD
subgraph MM[Main Menu]
Rules([How to Play?])
Start([Start new game])
end



subgraph HTP[How to Play]
A([Go back to main menu])
Start1([Start new game])
end

subgraph GP[Gameplay]
Name[Prompt for player's nickname]
Name --> validName{isValid}
validName --No--> Error1[Too many characters] & Error2[No special characters allowed]
validName --Yes--> Answer{Generate number}
Error1 & Error2 --> Name
Answer --> Guess[Prompt for player's guess]
Guess --> validGuess{isValid?}
validGuess -- Yes --> TL & TH & CG
validGuess -- No --> range{out fo range?} & nonNumber{not a number?}
TL[Dispaly low guess message]
TH[Dispaly high guess message]
CG[Dispaly correct guess message] --> PA([Play again?])-- Yes --> Answer
range --> Error3[Display range message]
nonNumber --> Error4[Display only numbers message]
Error3 & Error4 --Click continue--> Guess

TL & TH--> TA([Try again?])
TA -- Yes --> Guess




end

Rules --> HTP
Start --> GP
A --> MM
Start1 --> GP
CG -- click exit --> MM
TA & PA -- click exit --> MM
Error3 & Error4 --click exit--> MM
```

Description
---

#### Main Menu
- Starting point to game
- User can go to how to play page
- User can start new game

#### How to Play
- Displays rules
  - Number between 1 and 100
  - No negatives
- User can start a new game
- User can go back to main menu

#### Gameplay
-Start of new game
1. User is prompted for a nickname
  - If not valid message is displayed and user can click continue to re-enter  
    *Invaild entries*
    - More than 15 characters
    - Non-numbers and non-letters
2. Generates a random number
3. User is prompted for a guess
  1. Guess too high  
    - Display high message  
    - User can try again  
    - User can exit game to main menu  
  2. Guess too low  
    - Display low message  
    - User can try again  
    - User can exit game to main menu
  3. Guess is not valid  
    - Display not valid message  
    - Press continue to re-enter a number  
    - User can exit to main menu  
  4. Guess is correct  
    - Display correct message  
    - User can play agian --> Game generates new number  
    - User can exit to main menu  
  5. User can exit to main menu

  

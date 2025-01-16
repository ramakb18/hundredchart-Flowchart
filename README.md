flowchart TD
    start["Start Game"] --> ChooseMode{"Select Difficulty Level: Easy, Medium, Hard"}
    ChooseMode --> Generate["Generate Random Number"]
    Generate --> DisplayGUI["Display Number on GUI"]
    Generate --> Timer["Start Timer"]
    DisplayGUI --> UserInput["Prompt User to Enter ?+10, -10, +1, -1"]
    UserInput --> Evaluate["Evaluate User's Answers"]
    Evaluate -- Correct --> PlaySoundCorrect["Play Success Sound"]
    Evaluate -- Incorrect --> PlaySoundIncorrect["Play Error Sound"]
    PlaySoundCorrect --> FeedbackCorrect["Provide Positive Feedback"]
    PlaySoundIncorrect --> FeedbackIncorrect["Provide Corrective Feedback"]
    FeedbackCorrect --> CheckHighscore{"Is it a highscore?"}
    FeedbackIncorrect --> ShowTimer["Stop Timer and Show Time"]
    CheckHighscore -- Yes --> UpdateHighscore["Update Highscore Table"]
    CheckHighscore -- No --> continue["Play Again?"]
    UpdateHighscore --> continue
    ShowTimer --> continue
    continue -- Yes --> ChooseMode
    continue -- No --> End["End Game"]

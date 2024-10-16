# hundredchart-Flowchart
flowchart TD
    start["Start Game"] -->ChooseMode{"Select Difficulty Level: Easy, Medium, Hard"}
    ChooseMode --> Generate["Generate Random Number"]
    Generate --> DisplayGUI["Display Number on GUI"] & Timer["Start Timer"] 
    DisplayGUI -->UserInput["Promt User to Enter ?+10, -10, +1, -1"]
    UserInput -->Evaluate["Evaluate User's Answers"]
    Evaluate -- Correct --> PlaySoundCorrect["Play success Sound"]
    Evaluate -- Incorrect --> PlaySoundIncorrect["Play Error Sound"]
    PlaySoundCorrect --> FeedbackCorrect["Provide Positive Feedback"]
    PlaySoundIncorrect --> FeedbackIncorrect["Provide Correctivev Feedback"]
    FeedbackCorrect --> CheckHighscore{"Is it a highscore?"}
    FeedbackIncorrect --> ShowTimer["Stop timer and Show time"]
    CheckHighscore -- Yes --> UpdateHighscore["Update Highscore Table"]
    CheckHighscore -- No --> continue["Play Again?"]
    UpdateHighscore --> continue
    ShowTimer --> continue
    continue -- Yes --> ChooseMode
    continue -- No --> End["End Game"]

# Keystroke-Essay-Score-Prediction

This is an independent prediction project using data from this database: https://www.kaggle.com/competitions/linking-writing-processes-to-writing-quality/overview

The goal is to analyze key and mouse stroke patterns and predict an essay score assigned by graders, indicative of the writing's quality. I chose this project because:
1. I'm interested in keystrokes as biometric verification & for verification of academic integrity, and this is a good way to familizarize myself with methods to analyze this kind of data
2. I would like to work on prediction projects where I must generate features myself from raw data

The jupyter notebook contains sections of code organized into exploratory data analysis, rudimentary prediction, and a final pipeline that uses various machine learning models, followed by a concluding analysis of prediction accuracy from each of the methods. A pdf report will be uploaded from overleaf at the project's conclusion.

## Data dictionary 


**Events**

| Column             | Definition                                                                |
| ------------------ | ------------------------------------------------------------------------- |
| essay_id_comp      | The unique ID of the essay                                                |
| event_id           | The index of the event, ordered chronologically                           |
| down_time          | The time of the down event in milliseconds                                |
| up_time            | The time of the up event in milliseconds                                  |
| action_time        | The duration of the event (the difference between down_time and up_time)  |
| activity           | The category of activity which the event belongs to                       |
| down_event         | The name of the event when the key/mouse is pressed                       |
| up_event           | The name of the event when the key/mouse is released                      |
| text_change        | The text that changed as a result of the event (if any)                   |
| cursor_position    | The character index of the text cursor after the event                    |
| word_count         | The word count of the essay after the event                               |

**Activities**

| Activity Name                  | Definition                                                                                 |
| ------------------------------ | ------------------------------------------------------------------------------------------ |
| Nonproduction                  | The event does not alter the text in any way                                               |
| Input                          | The event adds text to the essay                                                           |
| Remove/Cut                     | The event removes text from the essay                                                      |
| Paste                          | The event changes the text through a paste input                                           |
| Replace                        | The event replaces a section of text with another string                                   |
| Move From [x1, y1] To [x2, y2] | The event moves a section of text spanning character index x1, y1 to a new location x2, y2 |

**Scores**

| Column         | Definition                                                                        |
| -------------- | --------------------------------------------------------------------------------- |
| essay_id_comp  | The unique ID of the essay                                                        |
| score          | The score the essay received out of 6 (the prediction target for the competition) |


# Breezy Landing Page

This repository contains the Breezy marketing homepage matching the provided design challenge.


## Run locally

1. Clone this repository to your machine.
2. Open your terminal and navigate into the project directory using: cd breezy
3. Start the local server using Python: python3 -m http.server 8000
4. Open your browser and navigate to http://localhost:8000


What I Built:

I built an interactive Breezy Air Type Quiz that recommends a personalized air type based on the user's preferences.

I chose this feature because the existing website already promotes a "Take Our Quiz" experience, but the quiz was not implemented. I wanted to turn this existing product concept into a functional feature.

How It Works:

Users answer four multiple choice questions.
JavaScript tracks the current question and stores the user's answers temporarily.
Each answer contributes points toward different air types.
The air type with the highest score will be reccomended to the user
The result includes an explanation of why the air type matches the user's preferences.
Users can navigate backward, restart the quiz, or explore Breezy's plans.

Technical Approach:

The feature was built using HTML, CSS, and JavaScript.

I used JavaScript to manage the quiz state, dynamically update the DOM, and calculate the recommendation. 
I used a rule based scoring system rather than machine learning because the feature does not require a training dataset or backend.

The quiz is entirely frontend based, so user responses are only held temporarily in JavaScript and are not stored externally.

Data and Security:
Only preference based information is collected.
No personally identifiable or sensitive information is required.
No external APIs or third party services are used.
User responses are not persisted in the current implementation.
Setup

No additional setup is required. Open the HTML file in a browser to use the feature.

Future Improvements

If I had more time, I would:

Store user preferences in a database so returning users could access their personalized air type.
Improve the recommendation algorithm with more nuanced scoring, such as adding weights to the questions for more/less importance. 

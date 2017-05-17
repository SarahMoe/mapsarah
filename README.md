# Jouw toepassing online


## Algemeen: wij gaan hiervoor Heroku gebruiken

Website: heroku.com
https://devcenter.heroku.com/articles/deploying-nodejs
https://devcenter.heroku.com/articles/getting-started-with-nodejs#introduction

## Stappen:

Beginnen met een gratis account aanmaken op Heroku.com / signup.heroku.com

=> email checken

=> bevestigen, inloggen en daarna aangeven dat je een node.js ontwikkelaar bent.

Daarna vraagt men om een korte tutorial te volgen:

https://devcenter.heroku.com/articles/getting-started-with-nodejs#introduction (zie hierboven)

Je leert er hoe de Heroku CLI (command line interface) te installeren => DOEN

In de terminal:

heroku login

git clone https://github.com/heroku/node-js-getting-started.git

cd node-js-getting-started

=> je gaat daarmee een voorbeeld app downloaden

heroku create

git push heroku master

heroku ps:scale web=1

heroku open

Logs bekijken: heroku logs --tail
=> als er zaken bijkomen in de logs dan komen ze erbij tot je stopt met Control+```

Een procfile definiëren:

"Use a Procfile, a text file in the root directory of your application, to explicitly declare what command should be executed to start your app.
The Procfile in the example app you deployed looks like this:"
"This declares a single process type, web, and the command needed to run it. The name web is important here. It declares that this process type will be attached to the HTTP routing stack of Heroku, and receive web traffic when deployed.
Procfiles can contain additional process types. For example, you might declare one for a background worker process that processes items off of a queue."

web: node index.js

Scale the app
Right now, your app is running on a single web dyno. Think of a dyno as a lightweight container that runs the command specified in the Procfile.
You can check how many dynos are running using the ps command:

heroku ps

https://devcenter.heroku.com/articles/free-dyno-hours
https://devcenter.heroku.com/articles/scaling

heroku ps:scale web=0
heroku ps:scale web=1

Package.json bestand
"Declare app dependencies"

"When an app is deployed, Heroku reads this file and installs the appropriate node version together with the dependencies using the npm install command.
Run this command in your local directory to install the dependencies, preparing your system for running the app locally"


Run the app locally
-------------------

heroku local web


Just like Heroku, heroku local examines the Procfile to determine what to run.
Open http://localhost:5000 with your web browser. You should see your app running locally.
To stop the app from running locally, in the CLI, press Ctrl+C to exit.

Push local changes
------------------

Aanpassingen maken

Daarna lokaal toevoegen aan Git

git add .

git commit -m "Demo"

git push heroku master

TOT AAN DE ADD-ONS = genoeg voor deze week!

Volgende week: onze eigen github repository

http://codepen.io/admkrm/pen/ENRNyg

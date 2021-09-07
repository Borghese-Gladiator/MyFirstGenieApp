# My First Genie App
First Genie app written in Julia

## Technologies
- Julia - new programming language for Data Science to replace Python - https://julialang.org/learning/
- Genie - Julia web framework (like Django)
- Heroku CLI 

## Step by Step Process
1. Learned "Introduction to Julia" through JuliaAcademy
2. Downloaded Julia here - https://julialang.org/downloads/
3. Opened terminal and navigated to ```C:/Users/<user>/Documents/GitHub```
4. Ran ```julia```
5. Typed ```"]"``` - Opened package manager
6. Ran ```add Genie#master```
7. Ran ```using Genie```
8. Ran ```Genie.newapp_webservice("MyGenieApp")``` - generated routes & template for new app
9. Ran ```heroku create first-julia-genie-app --buildpack https://github.com/Optomatica/heroku-buildpack-julia.git```
- uses heroku-buildpack-julia to install all project dependencies in build time based on Project.toml & Manifest.toml
10. Added Procfile  - ```web: julia --project src/MyFirstGenieApp.jl $PORT```
11. After renaming app, reset Heroku git branch - ```heroku git:remote -a first-julia-genie-app```
12. ```git push heroku main```
- Encountered error - hard coded 8000 port & server host in read-only file initializers
13. Deleted apps & recreated app using their example (https://github.com/milesfrain/GenieOnHeroku)
14. Activate virtual env by goingn to package manager & typing ```activate .``` to use Project.toml
15. Reinstall to fix error: "header of cache file appears to be corrupted"
- ```add Genie#master```

## References
Genie Intro - https://genieframework.github.io/Genie.jl/dev/
Genie on Heroku - https://github.com/milesfrain/GenieOnHeroku

## GenieOnHeroku README
This project hosts a minimal [Genie.jl](https://github.com/GenieFramework/Genie.jl) web app on Heroku using a [julia buildpack](https://github.com/Optomatica/heroku-buildpack-julia).


Steps:
```
git clone https://github.com/milesfrain/GenieOnHeroku.git
cd GenieOnHeroku
HEROKU_APP_NAME=my-app-name
heroku create $HEROKU_APP_NAME --buildpack https://github.com/Optomatica/heroku-buildpack-julia.git
git push heroku master
heroku open -a $HEROKU_APP_NAME
heroku logs -tail -a $HEROKU_APP_NAME
```

I was previously attempting to host on heroku by uploading docker containers, but encountered lots of issues. Moved that troubleshooting effort to a [separate branch](https://github.com/milesfrain/GenieOnHeroku/tree/dockerfile) in this repo.

### GUI Guide (no terminal)

Here's a [guide](https://gist.github.com/fonsp/38965d7595a5d1060e27d6ca2084778d) on how to deploy to Heroku without any of the above CLI commands. Thanks to [@fonsp](https://github.com/fonsp) for the writeup.

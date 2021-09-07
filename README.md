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

## References
Genie Intro - https://genieframework.github.io/Genie.jl/dev/
Genie on Heroku - https://github.com/milesfrain/GenieOnHeroku
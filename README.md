![Star Badge](https://img.shields.io/static/v1?label=%F0%9F%8C%9F&message=If%20Useful&style=style=flat&color=BC4E99)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)

# Data Explorer Web App <img src="/img/computer.jpg" align="right" width="120" />

## đšī¸ Demo

![demo](/img/demo.gif)

## đ ī¸ Description
In this project, our group will develop an interactive web application using Streamlit that will read a provided CSV file by the user and perform some exploratory data analysis on it. The web application needs to be containerised with Docker and will be running using python 3.8.2.

## đ¤ Authors

* [Leah Nguyen](https://github.com/ndleah)
* [Cartier Zhi](https://github.com/cartierz)
* [Jia Ping Cai](https://github.com/caijiaping)
* [Laura Sofia Bayona](https://github.com/Laurabayonaf)

## đī¸ Program Structure

### âī¸ Program flow chart

![flowchart](/img/flowchart.png)

### đ File Structure & Description

```
./
â
âââ .github/
â   âââ ISSUE_TEMPLATE       
â   â   âââ bug_report.md        <- GitHub issue template for reporting bugs  
â   â   âââ feature_request.md   <- GitHub issue template for requesting improvement features
â   â
â   âââ PULL_REQUEST_TEMPLATE.md <- GitHub template for pull request
â
âââ app/
â   âââ streamlit_app.py         <- main script used for displaying the final application in the Docker container
â
âââ img/                         <- contains image(s) used in README.md 
â
âââ src/
â   âââ test
â   â   âââ test_data.py         <- python script for testing code from data.py
â   â   âââ test_datetime.py     <- python script for testing code from datetime.py
â   â   âââ test_numeric.py      <- python script for testing code from numeric.py
â   â   âââ test_text.py         <- python script for testing code from text.py
â   â
â   âââ __init__.py              <- turns src folder into a package for importing in main script
â   âââ data.py                  <- contains the code for displaying the "Overall information" section
â   âââ datetime.py              <- contains the code for displaying the "Information on each datetime" section
â   âââ numeric.py               <- contains the code for displaying the "Information on each numeric column" section
â   âââ text.py                  <- contains the code for displaying the "Information on each text column" section
â   
âââ .dockerignore                <- avoids unecessary files added up in the process of setting up Docker
âââ .gitignore                   <- avoids unecessary files pushed to the repository
âââ Dockerfile                   <- file used to build a Docker image
âââ docker-compose.yml           <- a YAML file to configure the application's services
âââ Pipfile                      <- contain information for the dependencies of the project
âââ Pipfile.lock                 <- specify, based on the packages present in Pipfile
âââ README.md                    <- a markdown file containing student details, a description of this project and instructions for running the application
```

## âī¸ Instructions

Clone the repository

```bash
git clone https://github.com/ndleah/Data_Explorer_Web_App.git
cd Data_Explorer_Web_App
```

Run the Docker container with docker compose

```bash
docker-compose up -d --build
```

The container will start in detached mode and can now be accessed via [http://localhost:8501](http://localhost:8501). 

Whenever you change the app/streamlit_app.py the steamlit application will update too. If you want to build upon that example, just add your dependencies to the Dockerfile and rebuild the image using docker-compose.

After you are done, and you want to tear down the application, either

```bash
docker-compose stop
```

to stop the application, or use 

```bash
docker-compose down --rmi all
```

to stop the application, remove the stopped containers and optionally `--rmi all` / remove all images associated in the docker-compose.yml file.
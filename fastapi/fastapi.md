# INSTALL FASTAPI
- ## install with python pip3 in command line
  - ``` pip3 install fastapi uvicorn ```
---
---
# RUN A FASTAPI APP
- ## go into the directory where the app file is located
  - ``` cd /path/to/app.py ```
- ## start the uvicorn application
  - ## uvicorn [filename(without ext)]:[fastapi object name]
  - ``` uvicorn dns_verfication_api:app --reload ```
  - ## ***"app"*** is the name of the app object in the python file and **NOT** the name of the file


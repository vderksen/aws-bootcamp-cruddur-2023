FROM python:3.10-slim-buster

# INSIDE CONTAINER 
# Make new folder inside the container
WORKDIR /backend-flask

# OUTSIDE CONTAINER -> INSIDE CONTAINER 
# Copy requirements.txt file which contains the libraries we want to install to run the app 
COPY requirements.txt requirements.txt

# INSIDE CONTAINER
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# OUTSIDE CONTAINER -> INSIDE CONTAINER 
# . mean everythin gin the current directory
# first period . - /backend-flask (outside container)
# secondperiod . - /backend-flask (inside container)
COPY . .

# INSIDE CONTAINER
# Set Enviroment Variables (Env Vars)
ENV FLASK_ENV=development

# python3 -m flask run --host=0.0.0.0 --port=4567
EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
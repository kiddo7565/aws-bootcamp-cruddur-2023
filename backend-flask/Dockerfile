FROM python:3.10-slim-buster

# Inside Container
# Make a new folder inside container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# This contains the libraries want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Contianter
# . means everything in the current directory
# first period . - /backend-flask (outside container)
# second period . /backend-flask (inside container)
COPY . .

# Set environment Variables (Env Vars)
# Inside Containter and will remain set when the containter is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
# -m (.    module)
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
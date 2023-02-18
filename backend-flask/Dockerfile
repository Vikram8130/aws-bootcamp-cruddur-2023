FROM python:3.10-slim-buster

# Inside the container [ make a new folder inside the container]
WORKDIR /backend-flask

# Outside the Container -> Inside the Container 
# this contains the libraries we want to installto run the app
COPY requirements.txt requirements.txt

# Outside the Container
# Install the python libraries  used for the app
RUN pip3 install -r requirements.txt

# Outside the Container -> Inside the Container 
# . means everything in the current directory
# first period . means /backend-flask (Outside the Container)
# Second period . means /backend-flask (Inside the Container)
COPY . .

# Set Environment Variables [Env Vars]
# Inside container and will remain set when container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

#
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
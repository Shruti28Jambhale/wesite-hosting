 **Flask App with Docker**

This is a simple Flask application that returns a "Hello from Flask & Docker" message when accessed at the root URL (`/`). It is designed to demonstrate the basics of setting up a Flask app and deploying it using Docker.

**Prerequisites**

To run this application, you will need the following:

* Python 3.6 or later
* pip
* Docker

**Installation**

1. Clone this repository to your local machine.

```
git clone https://github.com/username/flask-docker-app.git
```

2. Change into the project directory.

```
cd flask-docker-app
```

3. Install the required Python dependencies.

```
pip install -r requirements.txt
```

**Running the App**

To run the Flask app, simply execute the following command:

```
python app.py
```

This will start the Flask development server on port 5000. You can access the app by visiting `http://localhost:5000` in your web browser.

**Dockerizing the App**

To dockerize the app, follow these steps:

1. Create a `Dockerfile` in the project directory.

```
FROM python:3.6

WORKDIR /usr/src/app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "app.py"]
```

This `Dockerfile` defines a Docker image based on the official Python 3.6 image. It copies the project files into the image, installs the required Python dependencies, and sets the command to run the Flask app.

2. Build the Docker image.

```
docker build -t flask-docker-app .
```

This command will build the Docker image and tag it as `flask-docker-app`.

3. Run the Docker container.

```
docker run -p 5000:5000 flask-docker-app
```

This command will run the Docker container and expose port 5000 inside the container to port 5000 on the host machine. You can now access the app by visiting `http://localhost:5000` in your web browser.

**Conclusion**

This simple Flask application demonstrates the basics of setting up a Flask app and deploying it using Docker.


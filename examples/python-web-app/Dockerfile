FROM ubuntu

# Set the working directory to /app
WORKDIR /app

# Copy the requirements.txt and devops directory into /app
COPY requirements.txt /app
COPY devops /app

# Install Python and virtualenv
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv

# Create a virtual environment and install dependencies
RUN python3 -m venv venv && \
    . venv/bin/activate && \
    pip install --upgrade pip && \
    pip install -r requirements.txt

# Set the working directory to /app/devops
WORKDIR /app/devops

# Set the default command to use the virtual environment Python
ENTRYPOINT ["/app/venv/bin/python", "manage.py", "runserver", "0.0.0.0:8000"]






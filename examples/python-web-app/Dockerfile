FROM ubuntu

# Set working directory
WORKDIR /app

# Copy requirements.txt and devops directory
COPY requirements.txt devops/ ./

# Install Python 3, pip, and create a virtual environment
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /venv && \
    /venv/bin/pip install --upgrade pip && \
    /venv/bin/pip install -r requirements.txt

# Define entrypoint
ENTRYPOINT ["/venv/bin/python"]

# Run the Django server
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





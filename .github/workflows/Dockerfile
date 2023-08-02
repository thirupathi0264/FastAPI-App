# Base image
FROM python:3.8-slim

# Keeps Python from generating .pyc files in the container
ENV PYTHONDONTWRITEBYTECODE=1

# Turns off buffering for easier container logging
ENV PYTHONUNBUFFERED=1

# Install pip requirements
COPY requirements.txt .
RUN python -m pip install -r requirements.txt

# Copy the necessary files to the container
COPY ApiIntegration.py .
COPY unit.py .

# Run unit tests
RUN python -m unittest unit.py

# Set the working directory
WORKDIR /home/support/NEW_FOLDER/New_Folder5
COPY . /home/support/NEW_FOLDER/New_Folder5

# Expose the necessary port (if applicable)
EXPOSE 9009

# Command to run the application
CMD ["uvicorn", "ApiIntegration:app", "--host", "0.0.0.0", "--port", "9009"]

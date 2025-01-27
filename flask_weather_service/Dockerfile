# Use the official Python image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Copy requirements and install them
COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application
COPY . .

# Expose the port Flask will run on
EXPOSE 5000

# Define the command to run the app
CMD ["python", "app.py", "--port", "5000"]

# Use the official Python image
FROM python:3.14-alpine

# Set the working directory
WORKDIR /app

RUN apk add --no-cache gcc musl-dev libffi-dev
# Copy requirements and install them
COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application
COPY . .

# Expose the port Flask will run on
EXPOSE 5000

# Define the command to run the app
CMD ["python", "app.py", "--port", "5000"]

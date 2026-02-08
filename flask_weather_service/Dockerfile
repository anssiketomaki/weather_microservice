# Use the official Python image
FROM python:3.14-alpine AS builder
WORKDIR /app

# Install build tools (needed for some pip packages)
RUN apk add --no-cache gcc musl-dev libffi-dev

# Install requirements into a specific folder
COPY requirements.txt .
RUN pip install --user --no-cache-dir -r requirements.txt

# STAGE 2: Runtime
FROM python:3.14-alpine
WORKDIR /app

# Copy ONLY the installed packages from the builder
COPY --from=builder /root/.local /root/.local
COPY . .

# Ensure the app can find the moved packages
ENV PATH=/root/.local/bin:$PATH

EXPOSE 5000
CMD ["python", "app.py", "--port", "5000"]

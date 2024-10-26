# Start from the official Python image
FROM python:3.11

# Set environment variables to prevent Python from writing .pyc files and to buffer output for easier debugging
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Install git so we can clone the repository
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*

# Set up the working directory inside the container
WORKDIR /app

# Clone the repository directly
RUN git clone https://github.com/thisiswhom/Learning_Django.git /app

# Copy only the requirements file to cache dependencies
WORKDIR /app
RUN pip3 install --upgrade pip && \
    pip3 install django

# Expose the port Django runs on
EXPOSE 8000

# Command to run the Django development server
CMD ["python", "./password_generator-project/manage.py", "runserver", "0.0.0.0:8001"]

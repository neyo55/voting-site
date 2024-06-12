# Use the official Python image as base
FROM python:3.11-alpine3.19

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set the working directory in the container
WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the Django project into the container
COPY . .

# Run database migrations and collect static files
RUN python manage.py migrate
RUN python manage.py collectstatic --noinput

# Run the Django development server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]








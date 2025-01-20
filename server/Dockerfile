# Step 1: Add a base image (Python 3.12-slim in this case)
FROM python:3.12.0-slim

# Step 2: Set environment variables to prevent Python from buffering output
ENV PYTHONBUFFERED 1

# Step 3: Set the working directory inside the container
WORKDIR /app

# Step 4: Add the requirements.txt file (assuming it's already in the server directory)
COPY requirements.txt /app/

# Step 5: Install and update Python dependencies from requirements.txt
RUN pip install --upgrade pip && pip install -r requirements.txt

# Step 6: Expose the port your app will run on (default Django port is 8000)
EXPOSE 8000

# Step 7: Copy all files from the local project to the container's working directory
COPY . /app/

# Step 8: Command to run the application (using gunicorn to serve a Django app in this example)
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "your_project_name.wsgi:application"]

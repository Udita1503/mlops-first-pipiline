#Start with a lightweight python image
#This gives our container a Python runtime
FROM python:3.14-slim

#Set the working directory inside the container
WORKDIR /app

#Copy the dependancy list before copying application code
COPY requirements.txt .

#Avoid retaining pip's download cache in the image
RUN pip install --no-cache-dir -r requirements.txt

#Copy the application code and saved model into /app
COPY . .

#Document the port used by the FASTAPI application
EXPOSE 8000

#Start the API server when the container launches
# 0.0.0.0 allows connections through the container's network interface
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]


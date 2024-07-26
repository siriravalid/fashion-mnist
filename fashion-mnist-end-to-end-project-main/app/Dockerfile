# Use an appropriate base image
FROM python:3.10

# Set the working directory
WORKDIR /app

# Install system dependencies for HDF5
RUN apt-get update && apt-get install -y \
    libhdf5-dev \
    && rm -rf /var/lib/apt/lists/*

# Copy the requirements file into the container
COPY requirements.txt .

# Print the contents of requirements.txt for debugging
RUN cat requirements.txt

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application files into the container
COPY . .

# Verify installation
RUN pip list

# Set the command to run the application
CMD ["streamlit", "run", "main.py"]

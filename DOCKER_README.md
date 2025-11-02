# Docker Setup for P.R.I.S.M Blood Group Prediction

## Prerequisites
- Docker installed on your system
- Docker Compose (optional, but recommended)

## Quick Start

### Option 1: Using Docker Compose (Recommended)

```bash
# Build and run the container
docker-compose up --build

# Run in detached mode (background)
docker-compose up -d --build

# Stop the container
docker-compose down
```

### Option 2: Using Docker Commands

```bash
# Build the Docker image
docker build -t blood-group-prediction .

# Run the container
docker run -p 8501:8501 blood-group-prediction

# Run in detached mode
docker run -d -p 8501:8501 --name prism-app blood-group-prediction

# Stop the container
docker stop prism-app

# Remove the container
docker rm prism-app
```

## Access the Application

Once the container is running, open your browser and navigate to:
```
http://localhost:8501
```

## Container Details

- **Base Image**: Python 3.10 slim
- **Exposed Port**: 8501
- **Application**: Streamlit web app
- **Model**: Pre-trained CNN model (model.pth)

## Troubleshooting

### Port already in use
If port 8501 is already in use, you can map to a different port:
```bash
docker run -p 8080:8501 blood-group-prediction
```
Then access at `http://localhost:8080`

### View logs
```bash
# For docker-compose
docker-compose logs -f

# For docker run
docker logs -f prism-app
```

### Rebuild after changes
```bash
docker-compose up --build --force-recreate
```

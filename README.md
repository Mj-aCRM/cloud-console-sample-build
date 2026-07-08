# Cloud Console Sample Build

> A simple hello-world application demonstrating Google Cloud Build container image creation

## 📌 About

This repository provides a minimal example of how to build a Docker container image using **Google Cloud Build**. It's designed as a starting point for learning and experimenting with Google Cloud's container building capabilities.

## ✨ Features

- **Simple Dockerfile**: Minimal Alpine-based container
- **Cloud Build Configuration**: Ready-to-use `cloudbuild.yaml`
- **Hello World Script**: Basic shell script demonstrating container execution
- **Google Cloud Integration**: Automatically pushes to Google Container Registry

## 🚀 Getting Started

### Prerequisites

- [Google Cloud SDK](https://cloud.google.com/sdk/docs/install) installed
- Google Cloud project with Cloud Build API enabled
- Docker installed locally (for testing)

### Quick Start

#### 1. Clone the repository

```bash
git clone https://github.com/Mj-aCRM/cloud-console-sample-build.git
cd cloud-console-sample-build
```

#### 2. Build locally (optional)

```bash
# Build the Docker image locally
docker build -t helloworld-image .

# Run the container
docker run helloworld-image
```

#### 3. Deploy to Google Cloud

```bash
# Set your Google Cloud project
gcloud config set project YOUR_PROJECT_ID

# Submit the build to Google Cloud Build
gcloud builds submit --tag gcr.io/YOUR_PROJECT_ID/helloworld-image
```

## 📂 Project Structure

```
cloud-console-sample-build/
├── cloudbuild.yaml         # Google Cloud Build configuration
├── Dockerfile              # Docker container definition
├── helloworld.sh           # Main application script
├── CONTRIBUTING.md         # Contribution guidelines
├── LICENSE                 # Apache License 2.0
└── README.md               # This file
```

## 📝 Usage

### Using the built container

```bash
# Run the container
docker run gcr.io/YOUR_PROJECT_ID/helloworld-image

# Expected output:
# Hello, world! The time is [current date and time].
```

### Customizing the build

Edit `helloworld.sh` to change the output message:

```bash
#!/bin/sh
echo "Hello from my custom container! The time is $(date)."
```

Then rebuild and redeploy:

```bash
gcloud builds submit --tag gcr.io/YOUR_PROJECT_ID/helloworld-image
```

## 🔧 Configuration

### cloudbuild.yaml

The build configuration includes:

- **Single build step**: Uses the Docker image to build your container
- **Automatic image push**: Built images are automatically pushed to Google Container Registry
- **Tags**: Organized with the tag `gcp-cloud-build-sample-build`

### Dockerfile

- **Base image**: Alpine Linux (minimal and secure)
- **Copy**: Adds `helloworld.sh` to the container
- **Command**: Runs the shell script when the container starts

## 📚 Learn More

- [Google Cloud Build Documentation](https://cloud.google.com/build/docs)
- [Building Container Images](https://cloud.google.com/build/docs/building/build-containers)
- [Google Container Registry](https://cloud.google.com/container-registry)

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

## 📄 License

This project is licensed under the **Apache License 2.0** - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

- **Email**: contact@mj-acrm.com
- **Website**: https://mj-acrm.com
- **GitHub**: https://github.com/Mj-aCRM

---

<sub>Built with ❤️ by [Mj-aCRM](https://github.com/Mj-aCRM)</sub>

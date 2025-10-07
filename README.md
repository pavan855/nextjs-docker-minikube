This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started
Frontend Framework: Next.js 15

Language: TypeScript

Containerization: Docker

CI/CD: GitHub Actions

Deployment: Minikube (Kubernetes)

Registry: GitHub Container Registry (GHCR)

First, run the development server:

npm install
npm run dev


Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

Docker Setup
docker build -t my-nextjs-app . (Build Docker image)
docker run -p 3000:3000 my-nextjs-app  (Run Docker container)

GitHub Actions (CI/CD)

Each push to the main branch triggers a GitHub Actions workflow that:

Builds the Docker image using your Dockerfile.

Tags the image as
ghcr.io/pavan855/nextjs-docker-minikube:latest

Pushes it to GitHub Container Registry (GHCR).

Deploying to Minikube (Kubernetes)
minikube start (start mimikube)

Build the image inside Minikube
eval $(minikube docker-env)
docker build -t my-nextjs-app:local .

Apply Kubernetes Manifests
kubectl apply -f k8s/deployment.yml
kubectl apply -f k8s/service.yml

Verify Pods and Services
kubectl get pods
kubectl get svc

Access the Application
minikube service nextjs-service
http://127.0.0.1:30000            (Url)

GHCR Docker Image

The built image is publicly available at (ghcr.io/pavan855/nextjs-docker-minikube:latest)

CI/CD DevOps Prototype

This project demonstrates a CI/CD pipeline for deploying a Python application using modern DevOps tools.
Project Structure

ci_cd_devops_prototype/
├── Dockerfile               # Docker configuration for containerizing the application
├── Jenkinsfile              # Jenkins CI/CD pipeline configuration
├── deployment.yaml          # Kubernetes deployment configuration
├── service.yaml             # Kubernetes service configuration
├── llama.py                 # Python application source code
├── requirements.txt         # Python dependencies
├── test_llama.py            # Automated test cases
├── terraform/               # Infrastructure as Code (Terraform)
│   ├── main.tf              # Terraform configuration file
│   └── variables.tf         # Terraform variables

Execution Steps
Step 1: Clone the Repository

git clone https://github.com/janavi90/ci_cd_devops_prototype.git
cd ci_cd_devops_prototype

Step 2: Install Dependencies

Install Python dependencies for the application:

pip install -r requirements.txt

Step 3: Run the Application Locally

Start the Streamlit application:

streamlit run llama.py

Step 4: Dockerize the Application

Build and run the Docker container:

# Build Docker image
docker buildx build -t janavi90/llama:latest .

# Run Docker container
docker run -p 8501:8501 janavi90/llama:latest

Step 5: Deploy to Kubernetes

Deploy the application to Kubernetes:

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

Retrieve the external IP:

kubectl get svc llama-service

Step 6: CI/CD Pipeline with Jenkins

    Configure Jenkins with the provided Jenkinsfile.
    Set up credentials for DockerHub and Kubernetes.
    Trigger a build to automate the process.

Step 7: Automated Testing

Run tests with pytest:

pytest test_llama.py

Step 8: Infrastructure as Code (Terraform)

Provision resources with Terraform:

cd terraform
terraform init
terraform apply

Notes

    Ensure Kubernetes and Docker are properly configured.

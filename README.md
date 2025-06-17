# 🚀 n8n on Render

[![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-blue.svg)](https://n8n.io/)
[![Render](https://img.shields.io/badge/Render-Cloud%20Platform-black.svg)](https://render.com/)
[![Docker](https://img.shields.io/badge/Docker-Container-blue.svg)](https://www.docker.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)](https://github.com/yourusername/n8n-render-deployment)
[![Deploy](https://img.shields.io/badge/Deploy%20to%20Render-Instant%20Deploy-brightgreen.svg)](https://render.com/deploy)


<div align="center">
 ![image](https://github.com/user-attachments/assets/de996384-52c5-4572-93e4-838dbe4fa307)
  
  <em>Deploy n8n workflow automation platform on Render with ease</em>
</div>

---

A ready-to-deploy repository for hosting n8n on Render's cloud platform. This repository provides a simple and efficient way to deploy n8n as a web service, enabling you to create, manage, and execute automated workflows in the cloud.

## ✨ Features

- **🚀 One-Click Deployment**: Deploy n8n to Render with minimal configuration
- **🐳 Docker-Based**: Containerized deployment for consistency and reliability
- **🔒 Secure**: Environment-based configuration for sensitive data
- **📈 Scalable**: Built on Render's scalable cloud infrastructure
- **🔄 Persistent Storage**: Data persistence across deployments
- **🌐 Web Interface**: Access n8n through a web browser
- **⚡ Fast Setup**: Get up and running in minutes

## 🛠️ Tech Stack

- **n8n**: Workflow automation platform
- **Docker**: Containerization technology
- **Render**: Cloud hosting platform
- **PostgreSQL**: Database (optional, for persistent storage)
- **Redis**: Caching layer (optional, for performance)

## 📋 Prerequisites

Before deploying, ensure you have:

- A [Render](https://render.com/) account
- Basic knowledge of n8n workflows
- Environment variables ready (if using external services)

## 🚀 Quick Start

### Option 1: One-Click Deploy (Recommended)

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

1. Click the "Deploy to Render" button above
2. Connect your GitHub account
3. Configure your environment variables
4. Deploy!

### Option 2: Manual Deployment

1. **Fork this repository** to your GitHub account
2. **Create a new Web Service** on Render
3. **Connect your forked repository**
4. **Configure the service** with the following settings:

#### Render Service Configuration

```yaml
Name: n8n-workflow-automation
Environment: Docker
Region: Choose your preferred region
Branch: main
Root Directory: ./
Docker Command: docker run -p $PORT:5678 n8nio/n8n
```


## 📁 Project Structure

```
n8n-render-deployment/
├── Dockerfile             # Docker configuration for n8n
├── .dockerignore          # Local development setup
├── README.md              # This file
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| `N8N_BASIC_AUTH_ACTIVE` | Enable basic authentication | Yes | `true` |
| `N8N_BASIC_AUTH_USER` | Username for basic auth | Yes | - |
| `N8N_BASIC_AUTH_PASSWORD` | Password for basic auth | Yes | - |
| `N8N_ENCRYPTION_KEY` | 32-character encryption key | No | Auto-generated |
| `N8N_HOST` | Your Render app URL | No | Auto-detected |
| `N8N_PORT` | Port n8n runs on | No | `5678` |
| `N8N_PROTOCOL` | Protocol (http/https) | No | `https` |

### Database Configuration

For persistent storage, you can add a PostgreSQL database:

1. **Create a PostgreSQL service** on Render
2. **Add database environment variables** to your n8n service
3. **Restart the service** to apply changes

## 🐳 Docker Configuration

### Dockerfile

```dockerfile
FROM n8nio/n8n:latest

# Set working directory
WORKDIR /home/node/.n8n

# Expose port
EXPOSE 5678

# Start n8n
CMD ["n8n"]
```

### Docker Compose (Local Development)

```yaml
version: '3.8'
services:
  n8n:
    image: n8nio/n8n:latest
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=password
    volumes:
      - n8n_data:/home/node/.n8n
    restart: unless-stopped

volumes:
  n8n_data:
```

## 📊 Usage

### Accessing n8n

1. **Navigate to your Render app URL**
2. **Enter your credentials** (configured in environment variables)
3. **Start creating workflows** using n8n's visual interface

### Creating Your First Workflow

1. **Click "Add Workflow"** in the n8n interface
2. **Choose a trigger** (e.g., HTTP Request, Schedule, etc.)
3. **Add nodes** to process your data
4. **Test and activate** your workflow

### Example Workflows

- **Email Automation**: Send emails based on triggers
- **Data Processing**: Transform and analyze data
- **API Integration**: Connect different services
- **File Operations**: Handle file uploads and processing

## 🔒 Security Considerations

- **Use strong passwords** for basic authentication
- **Generate a unique encryption key** for production
- **Enable HTTPS** (automatic on Render)
- **Regular updates** to the latest n8n version
- **Monitor access logs** for suspicious activity

## 🚨 Troubleshooting

### Common Issues

1. **Service won't start**
   - Check environment variables
   - Verify Docker configuration
   - Review Render logs

2. **Authentication issues**
   - Ensure basic auth is properly configured
   - Check username/password in environment variables

3. **Database connection errors**
   - Verify database credentials
   - Check network connectivity
   - Ensure database service is running

### Getting Help

- Check the [n8n documentation](https://docs.n8n.io/)
- Review [Render documentation](https://render.com/docs)
- Open an issue in this repository
- Join the [n8n community](https://community.n8n.io/)

## 🔄 Updates and Maintenance

### Updating n8n

1. **Update the Docker image tag** in your configuration
2. **Redeploy the service** on Render
3. **Test your workflows** after the update

### Backup and Recovery

- **Export workflows** regularly from n8n interface
- **Backup database** if using PostgreSQL
- **Document configurations** for easy recovery

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to the branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Development Setup

```bash
# Clone the repository
git clone https://github.com/Abhi-Dev-coder/n8n-on-render.git
cd n8n-render-deployment

# Run with Docker Compose
docker-compose up -d
```

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [n8n](https://n8n.io/) - The amazing workflow automation platform
- [Render](https://render.com/) - The cloud platform that makes deployment easy
- [Docker](https://www.docker.com/) - Containerization technology

## 📞 Support

- **Documentation**: [n8n Docs](https://docs.n8n.io/)
- **Community**: [n8n Community](https://community.n8n.io/)
- **Issues**: [GitHub Issues](https://github.com/yourusername/n8n-render-deployment/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/n8n-render-deployment/discussions)

---

<div align="center">
  <strong>Happy Workflow Automation! 🚀</strong>
  <br/>
  <em>Built with n8️n for the n8n community</em>
</div>

# Kandeel Static Website

A modern static website built with HTML, CSS, and JavaScript, deployed using Docker and GitHub Actions CI/CD.

## 🚀 Features

- **Modern Design**: Clean, responsive design with smooth animations
- **Docker Deployment**: Containerized with Nginx for production
- **CI/CD Pipeline**: Automated testing and deployment with GitHub Actions
- **Security**: Security headers and best practices
- **Performance**: Optimized with gzip compression and caching

## 📁 Project Structure

```
PowerGym-Website/
├── .github/
│   └── workflows/
│       └── ci.yml          # GitHub Actions workflow
├── sites-available/
│   └── kandeel.conf           # Nginx site configuration
├── index.html                 # Main HTML file
├── style.css                 # CSS styles
├── nginx.conf                 # Nginx main configuration
├── Dockerfile                 # Docker configuration
└── README.md                  # This file
```

## 🛠️ Local Development

### Prerequisites

- Docker
- Git

### Running Locally

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd kandeel-website
   ```

2. **Build the Docker image**
   ```bash
   docker build -t kandeel-website .
   ```

3. **Run the container**
   ```bash
   docker run -d --name kandeel -p 8080:80 kandeel-website
   ```

4. **Access the website**
   - Open your browser and go to `http://localhost:8080`
   - Or add to your hosts file: `127.0.0.1 kandeel.local` and visit `http://kandeel.local:8080`

### Development without Docker

Simply open `index.html` in your browser for local development.

## 🔧 Configuration

### Nginx Configuration

The website uses a custom Nginx configuration optimized for static sites:

- **Security headers** for protection
- **Gzip compression** for performance
- **Caching** for static assets
- **Health check** endpoint at `/health`

### Docker Configuration

- **Multi-stage build** for optimized image size
- **Health checks** for container monitoring
- **Security** with non-root user (nginx)
- **Alpine Linux** base for minimal footprint

## 🚀 CI/CD Pipeline

The GitHub Actions workflow includes:

### Test Job
- HTML validation
- CSS validation
- Docker build test
- Container health check

### Build and Push Job
- Multi-platform Docker builds (AMD64, ARM64)
- Docker Hub image publishing
- Cache optimization

### Deploy Job
- Ready for production deployment
- Can be extended with cloud provider integrations

## 🔐 Security Features

- **Security Headers**: X-Frame-Options, X-XSS-Protection, etc.
- **Content Security Policy**: Prevents XSS attacks
- **Hidden File Protection**: Denies access to dotfiles
- **Non-root Container**: Runs as nginx user

## 📈 Performance Optimizations

- **Gzip Compression**: Reduces file sizes
- **Static Asset Caching**: 1-year cache for static files
- **HTML Caching**: 1-hour cache for HTML files
- **Alpine Linux**: Minimal base image

## 🌐 Deployment Options

### Docker Hub
1. Set up Docker Hub secrets in GitHub:
   - `DOCKER_USERNAME`
   - `DOCKER_PASSWORD`

2. Push to main branch to trigger deployment

### Other Platforms
- **Vercel**: Connect GitHub repo for automatic deployments
- **Netlify**: Drag and drop or Git integration
- **AWS S3 + CloudFront**: For scalable static hosting
- **GitHub Pages**: For simple static hosting

## 🛠️ Customization

### Adding New Pages
1. Create new HTML files in the root directory
2. Update navigation in `index.html`
3. Add corresponding CSS in `styles.css`

### Styling Changes
- Modify `styles.css` for design changes
- The CSS uses modern features like CSS Grid and Flexbox
- Responsive design included

### JavaScript Features
- Smooth scrolling navigation
- Active section highlighting
- Fade-in animations
- Mobile menu support (if needed)

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📞 Support

For support, email contact@kandeel.local or create an issue in the repository.


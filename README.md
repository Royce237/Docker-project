# Docker Project - Educational Website

A containerized web application for an educational platform featuring course listings, blog functionality, and contact management. This project demonstrates modern web development practices with Docker containerization.

## 🚀 Features

- **Responsive Design** - Mobile-first approach with modern CSS
- **Course Management** - Multiple course grid layouts (2, 3, and 4 column views)
- **Blog System** - Blog listing and individual post pages
- **Contact System** - Contact form with PHP backend processing
- **Teacher Profiles** - Dedicated teacher showcase pages
- **Pricing Information** - Course pricing and package details
- **About Section** - Comprehensive about page with company information

## 📁 Project Structure

```
Docker-project/
├── .github/workflows/     # GitHub Actions CI/CD pipeline
├── css/                   # Stylesheets and CSS files
├── fonts/                 # Web fonts and typography assets
├── images/                # Image assets and media files
├── js/                    # JavaScript files and scripts
├── dockerfile-html        # Docker configuration file
├── Dockerfile            # Legacy Docker configuration
├── index.html            # Main landing page
├── about.html            # About us page
├── blog.html             # Blog listing page
├── blog-single.html      # Individual blog post template
├── contact.html          # Contact form page
├── contact.php           # Contact form PHP handler
├── course-grid-2.html    # 2-column course layout
├── course-grid-3.html    # 3-column course layout
├── course-grid-4.html    # 4-column course layout
├── teachers.html         # Teacher profiles page
├── pricing.html          # Pricing and packages page
└── style.css             # Main stylesheet
```

## 🐳 Docker Setup

### Prerequisites

- Docker installed on your system
- Docker Compose (optional, for advanced setups)

### Quick Start

1. **Clone the repository:**
```bash
git clone https://github.com/Royce237/Docker-project.git
cd Docker-project
```

2. **Build the Docker image:**
```bash
docker build -f dockerfile-html -t educational-website .
```

3. **Run the container:**
```bash
docker run -d -p 8080:80 --name edu-site educational-website
```

4. **Access the application:**
Open your browser and navigate to `http://localhost:8080`

### Advanced Docker Commands

**Build with custom tag:**
```bash
docker build -f dockerfile-html -t educational-website:v1.0.0 .
```

**Run with volume mounting (for development):**
```bash
docker run -d -p 8080:80 -v $(pwd):/usr/share/nginx/html --name edu-site-dev educational-website
```

**View container logs:**
```bash
docker logs edu-site
```

**Stop and remove container:**
```bash
docker stop edu-site
docker rm edu-site
```

## 🛠️ Development

### Local Development Setup

1. **Without Docker:**
   - Serve files using any web server (Apache, Nginx, or simple HTTP server)
   - For PHP functionality, ensure PHP is installed and configured

2. **With Docker (recommended):**
   - Use the Docker setup above for consistent environment
   - Changes can be made and container rebuilt for testing

### File Organization

- **HTML Files**: Main pages and templates
- **CSS Directory**: Stylesheets, responsive design rules
- **JS Directory**: Interactive features, form validation, animations
- **Images Directory**: Logos, banners, course thumbnails, team photos
- **Fonts Directory**: Custom web fonts and typography assets

## 🔧 Configuration

### Web Server Configuration

The application is designed to work with standard web servers. Key considerations:

- **Document Root**: Set to project root directory
- **PHP Support**: Required for contact form functionality (`contact.php`)
- **File Permissions**: Ensure web server can read all static assets
- **URL Rewriting**: Optional, for clean URLs

### Environment Variables

You can customize the Docker container with environment variables:

```bash
docker run -d -p 8080:80 \
  -e NGINX_PORT=80 \
  -e NGINX_HOST=localhost \
  --name edu-site educational-website
```

## 🚦 CI/CD Pipeline

The project includes GitHub Actions workflow located in `.github/workflows/`. This automates:

- **Code Quality Checks** - Linting and validation
- **Docker Image Building** - Automated image creation
- **Testing** - Automated testing pipeline
- **Deployment** - Automated deployment to staging/production

### Workflow Triggers

- Push to main branch
- Pull request creation
- Manual workflow dispatch

## 📱 Features Overview

### Course Management
- **Multiple Layout Options**: 2, 3, and 4 column grid layouts
- **Course Categories**: Organized course browsing
- **Responsive Design**: Optimized for all device sizes

### Blog System
- **Blog Listing**: Overview of all blog posts
- **Individual Posts**: Detailed blog post pages
- **Categories and Tags**: Content organization

### Contact System
- **Contact Form**: User inquiry submission
- **PHP Processing**: Server-side form handling
- **Validation**: Client and server-side validation

### Teacher Profiles
- **Team Showcase**: Professional teacher profiles
- **Qualifications**: Educational background display
- **Contact Information**: Direct teacher contact options

## 🔒 Security Considerations

- **Input Validation**: All form inputs are validated
- **XSS Protection**: Output encoding implemented
- **CSRF Protection**: Token-based request validation
- **File Upload Security**: Restricted file types and sizes

## 🌐 Browser Compatibility

- **Chrome**: Full support (latest versions)
- **Firefox**: Full support (latest versions)  
- **Safari**: Full support (latest versions)
- **Edge**: Full support (latest versions)
- **Internet Explorer**: Limited support (IE11+)

## 📊 Performance Optimization

- **Minified Assets**: CSS and JS files optimized
- **Image Optimization**: Compressed images for faster loading
- **Caching Headers**: Browser caching configuration
- **CDN Ready**: Static assets optimized for CDN delivery

## 🤝 Contributing

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature-name`
3. **Make your changes**: Update HTML, CSS, or JS files
4. **Test thoroughly**: Ensure all functionality works
5. **Commit changes**: `git commit -am 'Add new feature'`
6. **Push to branch**: `git push origin feature-name`
7. **Submit pull request**: Create PR with detailed description

### Contribution Guidelines

- Follow existing code style and structure
- Test changes across different browsers
- Update documentation for new features
- Ensure Docker build still works after changes

## 📋 Testing

### Manual Testing Checklist

- [ ] All pages load correctly
- [ ] Navigation works across all pages
- [ ] Contact form submits successfully
- [ ] Responsive design works on mobile devices
- [ ] Images and fonts load properly
- [ ] JavaScript functionality works as expected

### Docker Testing

```bash
# Test Docker build
docker build -f dockerfile-html -t test-build .

# Test container startup
docker run -d -p 8081:80 --name test-container test-build

# Verify application accessibility
curl http://localhost:8081

# Cleanup test container
docker stop test-container && docker rm test-container
```

## 🐛 Troubleshooting

### Common Issues

**Container won't start:**
```bash
docker logs edu-site
# Check for port conflicts or permission issues
```

**PHP forms not working:**
- Ensure PHP is enabled in your web server
- Check file permissions for `contact.php`
- Verify PHP configuration for form processing

**Images not loading:**
- Check file paths in HTML files
- Ensure images directory has proper permissions
- Verify image file extensions are correct

**Styling issues:**
- Clear browser cache
- Check CSS file paths
- Verify CSS syntax

## 📚 Resources

- **Docker Documentation**: [https://docs.docker.com/](https://docs.docker.com/)
- **HTML5 Specification**: [https://html.spec.whatwg.org/](https://html.spec.whatwg.org/)
- **CSS Guidelines**: [https://cssguidelin.es/](https://cssguidelin.es/)
- **JavaScript Best Practices**: [https://jstherightway.org/](https://jstherightway.org/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🏆 Contributors

- **Royce237** - Project maintainer and primary developer
- **tifynk** - Contributor

## 📈 Roadmap

- [ ] Add user authentication system
- [ ] Implement course enrollment functionality
- [ ] Add payment integration
- [ ] Create admin dashboard
- [ ] Implement search functionality
- [ ] Add multi-language support
- [ ] Mobile app development
- [ ] API development for third-party integrations

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Royce237/Docker-project/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Royce237/Docker-project/discussions)
- **Email**: Contact through the website contact form

---

**Built with 🎓 for educational excellence**

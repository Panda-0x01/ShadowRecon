# 🔍 Web Vulnerability Scanner

A comprehensive web-based vulnerability scanner that detects common security vulnerabilities in web applications including XSS, SQL Injection, and CSRF attacks.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/flask-2.3.3-green.svg)

## ⚠️ Legal Disclaimer

**IMPORTANT: This tool is designed for educational purposes and authorized security testing only.**

- ✅ **Authorized Use**: Only use on systems you own or have explicit written permission to test
- ❌ **Prohibited Use**: Do not use on systems without proper authorization
- ⚖️ **Legal Responsibility**: Users are responsible for compliance with local laws and regulations
- 🎓 **Educational Purpose**: Intended for learning web security concepts and ethical hacking

## 🚀 Features

### 🔍 Vulnerability Detection
- **Cross-Site Scripting (XSS)**: Detects reflected XSS vulnerabilities
- **SQL Injection**: Identifies potential SQLi vulnerabilities across multiple database types
- **CSRF Protection**: Checks for missing CSRF tokens in POST forms

### 🌐 Web Interface
- **Modern UI**: Clean, responsive web interface
- **Real-time Updates**: Live progress tracking and logging
- **Interactive Dashboard**: Visual scan progress and statistics
- **Report Generation**: Downloadable vulnerability reports

### 🔧 Advanced Features
- **Smart Crawling**: Recursive website crawling with depth control
- **Rate Limiting**: Configurable request delays to avoid overwhelming targets
- **Multi-threaded**: Background scanning with real-time status updates
- **Pattern Matching**: Advanced error detection patterns for multiple database types

## 📁 Project Structure

```
vulnerability-scanner/
├── app.py                 # Flask backend server
├── scanner_engine.py      # Core vulnerability scanning logic
├── requirements.txt       # Python dependencies
├── README.md             # Project documentation
├── static/
│   ├── css/
│   │   └── style.css     # Main stylesheet
│   ├── js/
│   │   └── main.js       # Frontend JavaScript
│   └── assets/
│       └── logo.png      # Optional project logo
└── templates/
    └── index.html        # Main HTML template
```

## 🛠️ Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Modern web browser

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/vulnerability-scanner.git
cd vulnerability-scanner
```

### Step 2: Create Virtual Environment (Recommended)
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Run the Application
```bash
python app.py
```

The application will start on `http://localhost:5000`

## 🎯 Usage

### Web Interface

1. **Open Browser**: Navigate to `http://localhost:5000`
2. **Configure Scan**: 
   - Enter target URL (e.g., `http://testphp.vulnweb.com`)
   - Set crawl depth (1-4 levels)
   - Choose request delay (0.5-3.0 seconds)
   - Select vulnerability types to test
3. **Start Scan**: Click "Start Scan" button
4. **Monitor Progress**: Watch real-time logs and progress updates
5. **Review Results**: Analyze discovered vulnerabilities
6. **Download Report**: Export detailed vulnerability report

### Command Line Interface

You can also run the core scanner directly:

```bash
python scanner_engine.py http://target-website.com
```

## 🔧 Configuration Options

### Scan Depth
- **Level 1**: Surface scan (homepage and direct links)
- **Level 2**: Medium depth (recommended for most scans)
- **Level 3**: Deep scan (more comprehensive but slower)
- **Level 4**: Very deep scan (thorough but time-consuming)

### Request Delay
- **0.5s**: Fast scanning (may trigger rate limiting)
- **1.0s**: Normal speed (recommended)
- **2.0s**: Slow scanning (respectful to target servers)
- **3.0s**: Very slow (minimal server impact)

### Vulnerability Types
- **XSS**: Cross-Site Scripting detection
- **SQLi**: SQL Injection vulnerability testing
- **CSRF**: Cross-Site Request Forgery protection checks

## 🧪 Testing Environments

For safe testing and learning, use these intentionally vulnerable applications:

### Recommended Test Targets
- **DVWA** (Damn Vulnerable Web Application)
- **WebGoat** (OWASP WebGoat)
- **Mutillidae II**
- **bWAPP** (Buggy Web Application)
- **VulnHub VMs**

### Example Test Commands
```bash
# Test against DVWA (if running locally)
python app.py
# Then navigate to http://localhost:5000 and scan http://localhost/dvwa

# Test against online vulnerable app
# Target: http://testphp.vulnweb.com (designed for security testing)
```

## 📊 Understanding Results

### Vulnerability Severity Levels
- **🔴 HIGH**: Critical vulnerabilities requiring immediate attention
- **🟡 MEDIUM**: Important security issues that should be addressed
- **🔵 LOW**: Minor security concerns or informational findings

### Common Vulnerability Types

#### SQL Injection
```
Risk Level: HIGH
Description: Allows attackers to manipulate database queries
Impact: Data theft, data manipulation, system compromise
```

#### Cross-Site Scripting (XSS)
```
Risk Level: HIGH
Description: Allows injection of malicious scripts
Impact: Session hijacking, credential theft, defacement
```

#### CSRF (Cross-Site Request Forgery)
```
Risk Level: MEDIUM
Description: Missing CSRF protection on forms
Impact: Unauthorized actions on behalf of users
```

## 🔒 Security Best Practices

### For Scanner Usage
1. **Authorization**: Always obtain written permission before scanning
2. **Rate Limiting**: Use appropriate delays to avoid DoS conditions
3. **Scope Limitation**: Only scan agreed-upon targets and paths
4. **Data Handling**: Securely handle and dispose of scan results

### For Developers
1. **Input Validation**: Sanitize all user inputs
2. **Parameterized Queries**: Use prepared statements for database queries
3. **CSRF Tokens**: Implement CSRF protection on all state-changing operations
4. **Security Headers**: Implement proper security headers (CSP, X-Frame-Options, etc.)

## 🐛 Troubleshooting

### Common Issues

#### Connection Errors
```bash
# Error: Connection refused
# Solution: Check if target URL is accessible and properly formatted
curl -I http://target-website.com
```

#### Permission Denied
```bash
# Error: Permission denied when saving reports
# Solution: Check file permissions or run with appropriate privileges
chmod 755 ./
```

#### Memory Issues
```bash
# Error: Memory error during large scans
# Solution: Reduce scan depth or increase delay between requests
```

### Debug Mode
Enable debug mode for detailed error information:
```bash
export FLASK_DEBUG=1
python app.py
```

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

### Development Setup
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Add tests if applicable
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

### Code Style
- Follow PEP 8 for Python code
- Use meaningful variable and function names
- Add docstrings for functions and classes
- Include error handling for network operations

### Testing
```bash
# Run basic tests
python -m pytest tests/

# Test with different Python versions
tox
```

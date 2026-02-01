<div align="center">

[![en](https://img.shields.io/badge/lang-en-blue.svg)](README.md)
[![pt-br](https://img.shields.io/badge/lang-pt--br-green.svg)](README.pt.md)

# AppFlowy · Coolify

### Deploy your workspace. Own your data.

*A seamless way to self-host AppFlowy using Coolify*

<br>

[Getting Started](#getting-started) · [Features](#features) · [Requirements](#requirements)

<br>
<br>

</div>

---

<br>

## Overview

AppFlowy meets Coolify. Experience the freedom of a self-hosted collaborative workspace with the simplicity of modern deployment.

This repository provides everything you need to deploy AppFlowy—an open-source, privacy-first alternative to Notion—on your own infrastructure using Coolify's elegant platform-as-a-service.

<br>

### Why This Matters

**Privacy First**  
Your data stays on your servers. No third parties. No compromises.

**Simplicity Built In**  
One-click deployment. Automatic SSL. Zero DevOps complexity.

**Complete Control**  
Own your workspace. Scale on your terms. Customize without limits.

<br>
<br>

## Features

<table>
<tr>
<td width="50%">

### 🎯 One-Click Deploy
Launch AppFlowy with a single action. Coolify handles the complexity.

</td>
<td width="50%">

### 🔒 Enterprise Security
Automatic SSL certificates, secure defaults, and full data isolation.

</td>
</tr>
<tr>
<td width="50%">

### 📦 Container Native
Built on Docker. Portable, reproducible, and battle-tested.

</td>
<td width="50%">

### 🚀 Production Ready
Optimized configurations for stability, performance, and scale.

</td>
</tr>
</table>

<br>
<br>

## Getting Started

### Requirements

Before you begin, ensure you have:

- A server with Docker installed (Linux recommended)
- Coolify installed and running ([Get Coolify](https://coolify.io))
- Domain name with DNS configured (optional, recommended for SSL)
- Minimum 2GB RAM, 2 CPU cores

<br>

### Quick Deploy

**1. Access Your Coolify Dashboard**

Navigate to your Coolify instance at `https://your-coolify-domain.com`

<br>

**2. Create a New Service**

```
Dashboard → Add New Resource → Docker Compose
```

<br>

**3. Configure AppFlowy**

Point to the AppFlowy Docker image:
```
appflowyinc/appflowy_cloud
```

Configure environment variables as needed for your setup.

<br>

**4. Deploy**

Click deploy. Coolify orchestrates everything—containers, networking, storage, SSL.

Your workspace launches in minutes.

<br>

**5. Access AppFlowy**

Open your configured domain or IP address. Create your first workspace.

<br>
<br>

## Configuration

### Essential Settings

**Database**  
PostgreSQL recommended. Coolify can provision this automatically.

**Storage**  
Configure persistent volumes for user data and attachments.

**Domain & SSL**  
Set your custom domain. Coolify handles SSL certificates via Let's Encrypt.

**Resources**  
Adjust memory and CPU limits based on your team size.

<br>

### Environment Variables

Customize your deployment with these key variables:

| Variable | Description | Default |
|----------|-------------|---------|
| `DATABASE_URL` | PostgreSQL connection string | Required |
| `GOTRUE_URL` | Authentication service URL | Required |
| `STORAGE_PATH` | Persistent storage location | `/data` |

<br>
<br>

## Support

### Resources

- [AppFlowy Documentation](https://docs.appflowy.io)
- [Coolify Documentation](https://coolify.io/docs)
- [AppFlowy Community](https://discord.gg/appflowy)

<br>

### Get Help

Found an issue? Have a question?

Open an issue in this repository or reach out to the communities above.

<br>
<br>

---

<div align="center">
<br>

**Built with care for teams who value privacy and control**

<br>

*AppFlowy · Coolify · Docker*

<br>
<br>

</div>
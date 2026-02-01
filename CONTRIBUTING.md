# Contributing to AppFlowy Coolify

Thank you for considering contributing to this project! This document provides guidelines for contributing.

## How to Contribute

### Reporting Issues

If you find a bug or have a feature request:

1. Check if the issue already exists in the [Issues](https://github.com/tech3br/appflowy-coolify/issues) page
2. If not, create a new issue with:
   - Clear title and description
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Your environment (OS, Docker version, etc.)

### Submitting Changes

1. **Fork the repository**
2. **Create a new branch** from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes**
4. **Test your changes** locally
5. **Commit your changes** with clear commit messages:
   ```bash
   git commit -m "Add: brief description of what you added"
   ```
6. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```
7. **Open a Pull Request** with:
   - Description of changes
   - Link to related issue (if any)
   - Testing steps

### Testing Your Changes

Before submitting a PR, please:

1. Test the Docker Compose configuration:
   ```bash
   docker compose config
   ```

2. Verify services start correctly:
   ```bash
   docker compose up -d
   docker compose ps
   docker compose logs
   ```

3. Check that all services are healthy:
   ```bash
   docker compose ps
   ```

### Coding Guidelines

- Follow existing code style
- Keep changes minimal and focused
- Update documentation for any configuration changes
- Test in a clean environment

### Documentation

- Update README.md for any user-facing changes
- Add comments for complex configurations
- Update .env.example for new environment variables

## Development Setup

1. Clone your fork:
   ```bash
   git clone https://github.com/YOUR-USERNAME/appflowy-coolify.git
   cd appflowy-coolify
   ```

2. Copy environment file:
   ```bash
   cp .env.example .env
   ```

3. Start services:
   ```bash
   docker compose up -d
   ```

## Questions?

Feel free to open an issue for any questions or clarifications needed.

## License

By contributing, you agree that your contributions will be licensed under the same license as the project.

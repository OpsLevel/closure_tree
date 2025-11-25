# Contributing to Closure Tree

Thank you for considering contributing to Closure Tree! This document outlines the process for contributing to this project.

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a new branch for your changes
4. Make your changes
5. Test your changes
6. Submit a pull request

## Development Setup

1. Install dependencies:
   ```bash
   bundle install
   ```

2. Run tests:
   ```bash
   bundle exec rspec
   ```

## Making Changes

### Code Style

- Follow the existing code style in the project
- Write clear, descriptive commit messages
- Keep commits focused and atomic

### Testing

- Add tests for any new functionality
- Ensure all tests pass before submitting a PR
- Run the full test suite: `bundle exec rspec`

## Changelog Management with Changie

This project uses [Changie](https://changie.dev/) for automated changelog management. **All pull requests must include a changie entry.**

### Installing Changie

You can install changie using one of the following methods:

**Via Homebrew (macOS/Linux):**
```bash
brew tap miniscruff/changie https://github.com/miniscruff/changie
brew install changie
```

**Via Go:**
```bash
go install github.com/miniscruff/changie@latest
```

**Via Direct Download:**
Download the appropriate binary for your platform from the [releases page](https://github.com/miniscruff/changie/releases).

### Adding a Changie Entry

When you make a change, create a changie entry by running:

```bash
changie new
```

This will interactively prompt you for:
- **Kind**: The type of change (Breaking Changes, Features, Bug Fixes, etc.)
- **Body**: A description of your change
- **Author**: Your GitHub username (e.g., @username)
- **Issue**: Related issue or PR number (e.g., #123)

The command will create a new file in `.changes/unreleased/` with your changelog entry.

### Changie Entry Examples

**For a bug fix:**
```bash
changie new
# Select: Bug Fixes
# Body: Fix issue with deterministic ordering for namespaced models
# Author: @yourusername
# Issue: #123
```

**For a new feature:**
```bash
changie new
# Select: Features
# Body: Add support for custom hierarchy table names
# Author: @yourusername
# Issue: #124
```

### Manual Changie Entry

If you prefer to create the entry manually, create a file in `.changes/unreleased/` with the following format:

```yaml
kind: Bug Fixes
body: Fix issue with deterministic ordering for namespaced models
time: 2024-01-15T10:30:00Z
custom:
  Author: "@yourusername"
  Issue: "#123"
```

## Pull Request Process

1. **Create your feature branch**
   ```bash
   git checkout -b feature/my-new-feature
   ```

2. **Make your changes and commit them**
   ```bash
   git commit -am "Add some feature"
   ```

3. **Add a changie entry** (see above)

4. **Push to your fork**
   ```bash
   git push origin feature/my-new-feature
   ```

5. **Submit a Pull Request**
   - Fill out the PR template completely
   - Ensure you've checked all items in the checklist
   - Confirm you've added a changie entry
   - Link any related issues

6. **Address review feedback**
   - Make requested changes
   - Push additional commits to your branch
   - The PR will automatically update

## Code Review

- All submissions require review before merging
- Reviewers may request changes or improvements
- Be open to feedback and willing to make changes
- Discussion and iteration are normal parts of the process

## Release Process

Releases are managed by maintainers. When a release is made:

1. Changie merges all entries from `.changes/unreleased/` into `CHANGELOG.md`
2. A new version is tagged
3. The gem is published to RubyGems

## Questions?

If you have questions about contributing, feel free to:
- Open an issue for discussion
- Reach out to the maintainers
- Check existing issues and pull requests for similar questions

Thank you for contributing to Closure Tree! 🎉

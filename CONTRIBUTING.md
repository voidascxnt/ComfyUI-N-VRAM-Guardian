# Contributing to ComfyUI VRAM Guardian

First off, thanks for taking the time to contribute! 🎉

The following is a set of guidelines for contributing to ComfyUI VRAM Guardian. These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [I Don't Want to Read This Whole Thing I Just Have a Question!](#i-dont-want-to-read-this-whole-thing-i-just-have-a-question)
- [How Can I Contribute?](#how-can-i-contribute)
- [Styleguides](#styleguides)
- [Additional Notes](#additional-notes)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to creating a welcoming environment. By participating, you are expected to uphold this standard.

## I Don't Want to Read This Whole Thing I Just Have a Question!

> **Note:** Please don't file an issue to ask a question. You'll get faster results by using the resources below.

If you have questions about using ComfyUI VRAM Guardian:

- Check the [README](README.md) first
- Look through existing [Issues](https://github.com/YOUR_USERNAME/ComfyUI-VRAM-Guardian/issues)
- Ask in ComfyUI community forums or Discord

## How Can I Contribute?

### Reporting Bugs

This section guides you through submitting a bug report for ComfyUI VRAM Guardian. Following these guidelines helps maintainers and the community understand your report, reproduce the behavior, and find related reports.

**Before Submitting A Bug Report:**

- Check if you can reproduce the problem in the latest version
- Check if the problem has already been reported by searching existing issues

**How Do I Submit A (Good) Bug Report?**

Bugs are tracked as GitHub issues. Create an issue and provide the following information:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples** to demonstrate the steps
- **Describe the behavior you observed** and **explain which behavior you expected**
- **Include system information:**
  - GPU model and VRAM amount
  - ComfyUI version
  - Operating system
  - Python version

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

- **Use a clear and descriptive title**
- **Provide a step-by-step description** of the suggested enhancement
- **Provide specific examples** to demonstrate the feature
- **Describe the current behavior** and **explain which behavior you expected**
- **Explain why this enhancement would be useful** to most VRAM Guardian users

### Your First Code Contribution

Unsure where to begin contributing? You can start by looking through these `beginner` and `help-wanted` issues:

- **Beginner issues**: Issues which should only require a few lines of code
- **Help wanted issues**: Issues which should be a bit more involved than beginner issues

### Pull Requests

Please follow these steps to have your contribution considered by the maintainers:

1. **Fork** the repository and create your branch from `main`
2. **Follow the styleguides**
3. **Test your changes** with different VRAM scenarios
4. **Update documentation** if needed
5. **Create a pull request** with a clear title and description

## Styleguides

### Git Commit Messages

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests liberally after the first line

### Python Styleguide

- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guide
- Use meaningful variable names
- Add docstrings to functions and classes
- Include type hints where appropriate
- Keep functions focused and small

### JavaScript Styleguide

- Use camelCase for variable names
- Use const for variables that don't change
- Use arrow functions where appropriate
- Add comments for complex logic
- Follow existing code formatting

### Documentation Styleguide

- Use [Markdown](https://daringfireball.net/projects/markdown/) for documentation
- Reference functions and classes in backticks: `function_name()`
- Include examples where helpful
- Keep explanations clear and concise

## Additional Notes

### Issue and Pull Request Labels

This section lists the labels we use to help us track and manage issues and pull requests:

- **bug**: Something isn't working
- **enhancement**: New feature or request
- **documentation**: Improvements or additions to documentation
- **good first issue**: Good for newcomers
- **help wanted**: Extra attention is needed
- **question**: Further information is requested

### Development Setup

To set up your development environment:

1. Fork and clone the repository
2. Install ComfyUI in development mode
3. Install project dependencies: `pip install -r requirements.txt`
4. Create a test workflow to verify functionality
5. Make your changes and test thoroughly

### Testing Guidelines

- Test with different VRAM usage scenarios
- Verify UI responsiveness under load
- Test emergency termination methods
- Ensure compatibility with various ComfyUI workflows
- Check performance impact on normal operations

Thank you for contributing to ComfyUI VRAM Guardian! 🛡️
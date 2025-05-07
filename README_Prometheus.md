# Manticore: A Lightweight Python Static Site Generator

## Project Overview

Manticore is a lightweight and flexible static site generator built with Python, designed to simplify the process of creating static websites from markdown content. It provides an efficient solution for developers and content creators who want to generate clean, responsive websites with minimal configuration.

### Core Purpose
The project addresses the need for a simple, straightforward static site generation tool that supports multiple content types, such as blog posts and resumes, with an emphasis on ease of use and minimal complexity.

### Key Features
- **Markdown-Driven Content**: Easily create and manage website content using markdown files
- **Flexible Templates**: Supports multiple template types (blog and resume)
- **Command-Line Interface**: Simple CLI for generating sites with just a few commands
- **Responsive Design**: Utilizes Skeleton CSS and Normalize CSS for mobile-friendly layouts
- **Multi-Purpose**: Can generate different types of static sites from the same framework

### Benefits
- Rapid website development with minimal setup
- No database or complex backend required
- Lightweight and fast site generation
- Separation of content and presentation
- Easy to version control and maintain

## Getting Started, Installation, and Setup

### Prerequisites

- Python 3.6 or higher
- pip package manager

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/manticore.git
   cd manticore
   ```

2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Quick Start

#### Generate a Blog
1. Add markdown files in the `content/default` directory
2. Generate the blog:
   ```bash
   python build.py --default default
   ```
3. The generated site will be in the `output` folder

#### Generate a Resume
1. Add a markdown file in the `content/resume` directory
2. Generate the resume:
   ```bash
   python build.py --resume resume
   ```
3. The generated resume will be in the `output` folder

### Command-Line Options

Use the following command to see available options:
```bash
python build.py --help
```

Available options:
- `-d, --default`: Generate the default blog template
- `-r, --resume`: Generate a resume template

### Development Notes

- Ensure all content is written in markdown format
- Place blog posts in `content/default`
- Place resume content in `content/resume`
- The generator uses Jinja2 templates from the `templates` directory

### Troubleshooting

- Verify Python version: `python --version`
- Ensure all dependencies are installed correctly
- Check that markdown files are formatted properly

## Customization Guide

Manticore is designed to be easily customizable for different static site needs. Here's how you can modify and adapt the project:

### Content Customization
- Place your markdown files in specific content directories:
  - `/content/default/`: For blog posts and general articles
  - `/content/resume/`: For creating resume/CV pages

### Template Customization
You can customize templates located in the `templates/` directory:
- `templates/layout.html`: Main HTML layout for all pages
- `templates/default/home.html`: Homepage template for blog/articles
- `templates/default/post.html`: Individual post/article template
- `templates/resume/home.html`: Resume page template

#### Styling Modifications
- Current templates use Skeleton CSS and Normalize CSS via CDN
- Modify the inline styles in `templates/layout.html` to adjust page layout
- Replace CDN links to use custom CSS frameworks or local stylesheets

### Markdown Content Guidelines
- Use standard markdown formatting in your content files
- Files should have appropriate metadata or front matter as required by the parsing logic
- Supported file locations: 
  - `content/default/` for blog posts
  - `content/resume/` for resume content

### Templating with Jinja2
Templates use Jinja2 templating language, allowing dynamic content rendering:
- Use `{% block title %}` for page titles
- Use `{% block body %}` for main page content
- Customize template inheritance as needed

### Command-Line Generation Options
Use `build.py` with different flags to generate site variations:
- `python build.py --default default`: Generate blog site
- `python build.py --resume resume`: Generate resume site

### Extensibility Notes
- Project supports easy addition of new templates
- Future releases may include more template types (portfolio, landing page)

## Use Cases

Manticore is a versatile static site generator ideal for various lightweight web publishing needs:

### Personal Blogging
Quickly create and manage a static blog using markdown files. Perfect for developers, writers, and content creators who prefer a simple, text-based workflow.

### Professional Resume Websites
Generate a clean, professional single-page resume website with minimal configuration. Ideal for job seekers and professionals looking to showcase their skills online.

### Rapid Prototyping
Quickly spin up simple websites with minimal overhead. Great for:
- Portfolio showcases
- Documentation sites
- Personal project pages

### Learning and Experimentation
An excellent tool for:
- Students learning web development
- Developers exploring static site generation
- Individuals wanting a lightweight alternative to complex content management systems

### Technical Writing
Ideal for technical writers and documentation specialists who prefer writing in markdown and want a straightforward way to publish content.

### Key Advantages
- Simple markdown-based content creation
- Minimal setup and configuration
- Fast generation of static websites
- Flexible templating with Jinja2
- Responsive design using Skeleton CSS

## Project Structure

The project is organized into several key directories and files to support the static site generation process:

#### Root Directory
- `build.py`: The main script for generating static sites, providing command-line interface for site generation
- `parse.py`: Likely handles parsing of markdown content
- `render.py`: Responsible for rendering templates
- `requirements.txt`: Lists Python dependencies for the project
- `LICENSE`: Project licensing information

#### Content Directory
Stores source markdown files for different types of sites:
- `content/default/`: Contains markdown files for blog posts
  - `article.md`
  - `newarticle.md`
- `content/resume/`: Contains markdown for resume generation
  - `resume.md`

#### Templates Directory
Houses HTML templates for site generation:
- `templates/default/`: Templates for default blog site
  - `home.html`: Main page template
  - `post.html`: Individual post template
- `templates/resume/`: Templates specific to resume generation
  - `home.html`: Resume page template
- `templates/layout.html`: Likely a base layout template used across different site types

The project is designed to be modular, allowing easy generation of different types of static sites (blog, resume) through a flexible template and content management system.

## Technologies Used

### Programming Language
- Python 3

### Core Libraries and Frameworks
- Click (v7.1.1): Command-line interface and option parsing
- Jinja2 (v2.11.3): Template rendering engine
- Markdown2 (v2.3.8): Markdown parsing and conversion
- MarkupSafe (v1.1.1): HTML templating safety library

### Development Tools
- Logging: Built-in Python logging module for application logging

### Templating
- HTML templates for rendering content
- Markdown for content authoring

### Key Components
- Custom parsing modules for blog posts and resume
- Modular rendering system
- Command-line build interface

## Additional Notes

### Performance Considerations

The static site generator is designed to be lightweight and efficient, processing Markdown files into static HTML pages with minimal overhead. It supports two primary generation modes: blog posts and resume templates.

### Security Notes

- Ensure markdown files in the `content` directory are from trusted sources, as the parser directly reads and converts these files.
- The generator creates an `output` directory, which should be used as the root for web hosting.

### Compatibility

- Works best with Python 3.6 and above
- Requires external dependencies listed in `requirements.txt`
- Cross-platform compatible (Windows, macOS, Linux)

### Limitations

- Currently supports only two template types: blog and resume
- No built-in support for complex site structures or multiple blogs
- Metadata in markdown files is crucial for proper rendering

### Future Roadmap

As noted in the project's upcoming feature considerations:
- Potential implementation of custom category/tag systems
- Exploration of additional static site templates (portfolio, landing pages)

### Recommended Hosting Platforms

While specific deployment solutions are still in development, static site hosting platforms like Netlify, GitHub Pages, or Vercel are recommended for hosting the generated static files.

## Contributing

We welcome contributions to Manticore! This section outlines how you can help improve the project.

### Ways to Contribute

- Report bugs and suggest features by opening GitHub issues
- Submit pull requests with bug fixes or new features
- Improve documentation
- Enhance existing code or add new functionality

### Contribution Process

1. Fork the repository
2. Create a new branch for your feature or bugfix
3. Make your changes
4. Write or update tests as needed
5. Ensure all tests pass
6. Submit a pull request with a clear description of your changes

### Code Guidelines

#### Python Code Style
- Follow PEP 8 guidelines for Python code
- Use meaningful variable and function names
- Write clear, concise comments
- Keep functions and methods focused and modular

#### Testing
- Add tests for new functionality
- Ensure existing tests continue to pass
- Use `pytest` for running tests

### Development Setup

- Use Python 3.6 or higher
- Create a virtual environment
- Install dependencies: `pip install -r requirements.txt`
- Run tests before submitting a pull request

### Reporting Issues

When reporting issues, please include:
- Detailed description of the problem
- Steps to reproduce
- Expected vs. actual behavior
- Python version
- Operating system

### Code of Conduct

Be respectful, inclusive, and considerate of others. Harassment and discrimination are not tolerated.

## License

This project is licensed under the MIT License. 

### License Details
- Full license text is available in the [LICENSE](LICENSE) file
- Copyright (c) 2019 Blaze

The MIT License is a permissive open-source license that allows you to:
- Use the software commercially
- Modify the software
- Distribute the software
- Use the software privately
- Use the software for private use

The only conditions are:
- Include the original copyright notice
- Include the original license text

The software is provided "as is", without warranties of any kind.
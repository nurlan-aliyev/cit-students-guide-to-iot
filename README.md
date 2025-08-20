# CIT Student's Guide to IoT

A comprehensive guide for Construction Information Technology (CIT) students learning about Internet of Things (IoT) and Arduino programming, with a focus on applications in Civil Engineering.

## 📖 About

This documentation project serves as an educational resource for MSc Construction Information Technology Engineering students at the Technical University. It covers the fundamentals of IoT technology, Arduino programming, and microcontroller applications in civil engineering contexts.

## 🌟 Features

- **Comprehensive Coverage**: From basic IoT concepts to advanced Arduino programming
- **Student-Focused**: Tailored specifically for CIT engineering students
- **Practical Examples**: Real-world code examples and applications
- **Interactive Documentation**: Built with MkDocs Material for modern, responsive design
- **Automatic Deployment**: GitHub Actions CI/CD pipeline for seamless updates

## 📚 Documentation Contents

| Section | Description | Topics Covered |
|---------|-------------|----------------|
| **Introduction** | Arduino and IoT fundamentals | History, microcontrollers, hardware basics |
| **Getting Started** | Setup and installation | Arduino IDE, hardware connections, troubleshooting |
| **Programming Basics** | Core programming concepts | Sketch structure, setup/loop functions, variables |
| **I/O Operations** | Input/Output operations | Digital/analog pins, pinMode, digitalRead/Write |
| **Essential Functions** | Key Arduino functions | delay(), millis(), random(), min/max functions |
| **Useful Links** | External resources | Official documentation, tutorials, references |

## 🚀 Quick Start

### Viewing the Documentation

The documentation is automatically deployed to GitHub Pages and can be viewed at:
```
https://nurlan-aliyev.github.io/cit-students-guide-to-iot/
```

### Building Locally

To build and preview the documentation locally:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/nurlan-aliyev/cit-students-guide-to-iot.git
   cd cit-students-guide-to-iot
   ```

2. **Install dependencies**:
   ```bash
   pip install mkdocs-material
   ```

3. **Serve locally**:
   ```bash
   mkdocs serve
   ```
   
   The documentation will be available at `http://localhost:8000`

4. **Build static site**:
   ```bash
   mkdocs build
   ```

## 📁 Project Structure

```
cit-students-guide-to-iot/
├── docs/                     # Documentation source files
│   ├── index.md             # Home page
│   ├── introduction.md      # Arduino and IoT introduction
│   ├── getting-started.md   # Setup and installation guide
│   ├── programming-basics.md # Core programming concepts
│   ├── io-operations.md     # Input/Output operations
│   ├── necessary-functions.md # Essential Arduino functions
│   └── useful-links.md      # External resources
├── .github/
│   └── workflows/
│       └── ci.yml           # GitHub Actions deployment
├── mkdocs.yml               # MkDocs configuration
├── .gitignore              # Git ignore rules
└── README.md               # This file
```

## 🔧 Technology Stack

- **Documentation Generator**: [MkDocs](https://www.mkdocs.org/)
- **Theme**: [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- **Deployment**: GitHub Actions + GitHub Pages
- **Content Format**: Markdown
- **Syntax Highlighting**: Pygments with C/C++ support

## 🚀 Deployment

The project uses GitHub Actions for automatic deployment:

- **Trigger**: Push to `main` or `master` branch
- **Process**: Install dependencies → Build documentation → Deploy to GitHub Pages
- **URL**: Documentation is available at the GitHub Pages URL

The deployment workflow is defined in `.github/workflows/ci.yml`.

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes to the documentation files in the `docs/` folder
4. Test locally with `mkdocs serve`
5. Commit your changes (`git commit -am 'Add new content'`)
6. Push to the branch (`git push origin feature/improvement`)
7. Create a Pull Request

### Content Guidelines

- Write clear, concise explanations suitable for students
- Include practical code examples where applicable
- Follow the existing markdown formatting style
- Test all code examples before submitting
- Update the navigation in `mkdocs.yml` if adding new pages

## 👨‍💻 Author

**Nurlan Aliyev**
- GitHub: [@nurlan-aliyev](https://github.com/nurlan-aliyev)
- LinkedIn: [Nurlan Aliyev](https://www.linkedin.com/in/nurlan-aliyev-18b023220/)

## 📄 License

This project is created for educational purposes. Please refer to the repository settings for license information.

## 🎯 Learning Objectives

After following this guide, students will be able to:

- Understand IoT fundamentals and applications in civil engineering
- Set up and configure Arduino development environment
- Write basic to intermediate Arduino programs
- Implement digital and analog input/output operations
- Apply Arduino programming to solve engineering problems
- Access and utilize additional resources for continued learning

## 📞 Support

For questions, issues, or suggestions:

1. **Issues**: Open an issue on GitHub for bugs or feature requests
2. **Discussions**: Use GitHub Discussions for general questions
3. **Contact**: Reach out to the author via GitHub or LinkedIn

---

*Made with ❤️ for CIT students learning IoT and Arduino programming*
# 🎵 AI Music Composer

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)](https://streamlit.io/)
[![LangChain](https://img.shields.io/badge/LangChain-0.1+-green.svg)](https://langchain.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Transform your musical ideas into reality with AI-powered composition**

An intelligent music composition system that leverages Large Language Models (LLMs) to generate melodies, harmonies, and rhythms based on natural language descriptions. Built with Streamlit for an intuitive web interface and powered by Groq's lightning-fast LLM inference.

## ✨ Features

- 🎼 **AI-Generated Melodies**: Create unique musical sequences from text descriptions
- 🎹 **Harmony Generation**: Automatically generate chord progressions for your melodies
- 🥁 **Rhythm Creation**: Get rhythmic patterns and timing suggestions
- 🎭 **Style Adaptation**: Transform compositions into different musical styles (Jazz, Romantic, Sad, Happy, Extreme)
- 🔊 **Audio Synthesis**: Convert musical notation to playable audio files
- 🌐 **Web Interface**: Beautiful Streamlit-based UI for easy interaction
- 🐳 **Docker Ready**: Containerized for easy deployment
- ☸️ **Kubernetes Support**: Production-ready orchestration

## 🚀 Quick Start

### Prerequisites

- Python 3.11 or higher
- Groq API key ([Get one here](https://console.groq.com/))
- Basic understanding of music theory (optional but helpful)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Sak245/AI-Music-Composer.git
   cd AI-Music-Composer
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**
   ```bash
   # Create a .env file
   echo "GROQ_API_KEY=your_groq_api_key_here" > .env
   ```

4. **Run the application**
   ```bash
   streamlit run app.py
   ```

5. **Open your browser** and navigate to `http://localhost:8501`

## 🎯 How It Works

### 1. **Melody Generation**
The AI analyzes your text input and generates a sequence of musical notes in standard notation (e.g., "C4 D4 E4 F4").

### 2. **Harmony Creation**
Based on the generated melody, the system creates complementary chord progressions using harmonic analysis.

### 3. **Rhythm Development**
AI suggests rhythmic patterns and note durations that complement your melody and harmony.

### 4. **Style Adaptation**
Transform your composition into different musical styles while maintaining the core musical structure.

### 5. **Audio Synthesis**
Convert the musical notation into playable audio using digital synthesis techniques.

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Streamlit UI  │───▶│   MusicLLM      │───▶│   Groq LLM      │
│                 │    │   (Orchestrator)│    │   (llama-3.1)   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Audio Output  │    │   Music Utils   │    │   Music21       │
│   (WAV Files)   │    │   (Synthesis)   │    │   (Notation)    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 📁 Project Structure

```
AI-Music-Composer/
├── app/
│   ├── __init__.py          # Package initialization
│   ├── main.py              # Core MusicLLM class
│   └── utils.py             # Audio synthesis utilities
├── app.py                   # Streamlit web application
├── requirements.txt         # Python dependencies
├── setup.py                # Package configuration
├── Dockerfile              # Container configuration
├── kubernetes-deployment.yaml # K8s deployment specs
├── FULL_DOCUMENTATION.md   # Detailed deployment guide
└── README.md               # This file
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GROQ_API_KEY` | Your Groq API key for LLM access | Yes |

### Musical Parameters

- **Temperature**: Controls creativity vs. consistency (default: 0.7)
- **Sample Rate**: Audio quality (default: 44100 Hz)
- **Waveform**: Synthesis type (default: Sine wave)

## 🐳 Docker Deployment

### Build the image
```bash
docker build -t ai-music-composer .
```

### Run the container
```bash
docker run -p 8501:8501 -e GROQ_API_KEY=your_key ai-music-composer
```

## ☸️ Kubernetes Deployment

1. **Apply the deployment**
   ```bash
   kubectl apply -f kubernetes-deployment.yaml
   ```

2. **Check deployment status**
   ```bash
   kubectl get pods
   kubectl get services
   ```

3. **Access the application**
   ```bash
   kubectl port-forward service/llmops-service 8080:80
   ```

## 🎵 Usage Examples

### Basic Melody Generation
```
Input: "A peaceful morning in the forest"
Output: C4 D4 E4 F4 G4 A4 B4 C5
```

### Style Adaptation
```
Input: "Transform to jazz style"
Output: [Jazz-adapted composition with swing rhythms and extended harmonies]
```

### Complex Composition
```
Input: "A dramatic battle scene with rising tension"
Output: [Full composition with melody, harmony, rhythm, and dramatic styling]
```

## 🛠️ Development

### Local Development Setup
```bash
# Install in development mode
pip install -e .

# Run tests (when implemented)
python -m pytest

# Format code
black app/ *.py
```

### Adding New Features
1. Extend the `MusicLLM` class in `app/main.py`
2. Add utility functions in `app/utils.py`
3. Update the Streamlit interface in `app.py`
4. Test thoroughly with different musical inputs

## 📚 Dependencies

### Core Libraries
- **Streamlit**: Web application framework
- **LangChain**: LLM orchestration and prompting
- **Groq**: High-performance LLM inference
- **Music21**: Music notation and analysis
- **Synthesizer**: Digital audio synthesis

### Audio Processing
- **SciPy**: Scientific computing and signal processing
- **NumPy**: Numerical computing
- **IO**: File and buffer operations

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Workflow
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Groq** for providing fast LLM inference
- **LangChain** for LLM orchestration tools
- **Music21** for music theory and notation support
- **Streamlit** for the beautiful web interface framework

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Sak245/AI-Music-Composer/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Sak245/AI-Music-Composer/discussions)
- **Email**: your.email@example.com

## 🔮 Roadmap

- [ ] **MIDI Export**: Save compositions as MIDI files
- [ ] **Multi-Instrument Support**: Generate compositions for different instruments
- [ ] **Real-time Collaboration**: Collaborative composition sessions
- [ ] **Music Theory Validation**: Ensure generated music follows proper theory
- [ ] **Style Transfer**: More sophisticated style adaptation algorithms
- [ ] **Mobile App**: Native mobile application
- [ ] **API Endpoints**: RESTful API for integration

---

<div align="center">

**Made with ❤️ by V3817**

*Transform your musical imagination into reality*

[![GitHub stars](https://img.shields.io/github/stars/Sak245/AI-Music-Composer?style=social)](https://github.com/Sak245/AI-Music-Composer)
[![GitHub forks](https://img.shields.io/badge/GitHub-Forks-blue)](https://github.com/Sak245/AI-Music-Composer)

</div>

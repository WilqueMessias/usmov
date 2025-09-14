# USMOV 🎬

**AI-Powered Automatic Video Generator**

A complete system for generating short videos automatically using artificial intelligence. Just provide a topic or keywords and the system automatically generates script, narration, images, subtitles and background music.

## ✨ Key Features

- 🤖 **Automatic script generation** using AI models (OpenAI, Gemini, DeepSeek, etc.)
- 🎙️ **Voice synthesis** with multiple options (Edge TTS, Azure Cognitive Services)
- 🎬 **Automatic video assembly** with high-quality materials
- 📝 **Automatic subtitles** with font and position customization
- 🎵 **Background music** with volume control
- 📱 **Multiple formats** - Vertical (9:16) and Horizontal (16:9)
- 🌐 **Intuitive Web Interface** + Complete REST API
- ⚡ **Batch processing** to generate multiple videos

## 🚀 How to Use

### Prerequisites
- Python 3.11+
- FFmpeg installed on system
- ImageMagick (Windows: static version)

### Quick Installation

```powershell
# Clone repository
git clone https://github.com/WilqueMessias/usmov.git
cd usmov

# Create virtual environment
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt
```

### Configuration

1. Copy `config.example.toml` to `config.toml`
2. Configure your API keys in `config.toml` file
3. Adjust video settings as needed

### Run

#### Web Interface (Streamlit)
```powershell
.\webui.bat
```
Access: http://localhost:8501

#### REST API
```powershell
python main.py
```
Documentation: http://127.0.0.1:8080/docs

## 📐 Supported Formats

- **Vertical**: 1080x1920 (ideal for TikTok, Instagram Stories, YouTube Shorts)
- **Horizontal**: 1920x1080 (ideal for YouTube, Facebook)

## 🎨 Customization

### Fonts
Add your fonts to `resource/fonts/`

### Background Music
Place MP3 files in `resource/songs/`

### Video Materials
The system automatically searches for relevant materials or you can provide your own files.

## 🔧 API Endpoints

- `POST /api/v1/videos` - Generate complete video
- `POST /api/v1/audio` - Generate audio only
- `POST /api/v1/subtitle` - Generate subtitles only
- `GET /api/v1/tasks/{id}` - Query task status
- `GET /api/v1/musics` - List available music

## ⚙️ Advanced Settings

### Supported AI Models
- OpenAI GPT-4/3.5
- Google Gemini
- DeepSeek
- Moonshot
- Azure OpenAI
- Ollama (local)
- And others...

### Voice Synthesis
- Microsoft Edge TTS (free)
- Azure Cognitive Services (premium)
- Multiple voices and languages

## 📝 Usage Example

```python
import requests

# Generate video via API
response = requests.post("http://127.0.0.1:8080/api/v1/videos", json={
    "topic": "Benefits of meditation",
    "video_aspect": "9:16",
    "voice_name": "en-US-JennyNeural",
    "background_music": "relaxing.mp3"
})

task_id = response.json()["data"]["task_id"]
print(f"Video being generated: {task_id}")
```

## 🛠️ Development

```powershell
# Activate development environment
.\.venv\Scripts\Activate.ps1

# Run tests
python -m pytest test/

# Run with auto-reload
python main.py --reload
```

## 📊 Project Status

- ✅ AI script generation
- ✅ Voice synthesis
- ✅ Video assembly
- ✅ Web interface
- ✅ REST API
- ✅ Automatic subtitles
- 🔄 Material selection improvements
- 🔄 Automatic upload to platforms
- 🔄 More customization options

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the project
2. Create a branch for your feature (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Open a Pull Request

## 📄 License

This project is under the MIT license. See the `LICENSE` file for more details.

## 🆘 Support

Found a problem? Open an [issue](https://github.com/WilqueMessias/usmov/issues) or get in touch.

---

**Made with ❤️ by [Wilque Messias](https://github.com/WilqueMessias)**

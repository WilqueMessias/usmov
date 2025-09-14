# USMOV 🎬

**Gerador Automático de Vídeos com IA**

Um sistema completo para geração automática de vídeos curtos usando inteligência artificial. Fornece apenas um tópico ou palavras-chave e o sistema gera automaticamente roteiro, narração, imagens, legendas e música de fundo.

## ✨ Características Principais

- 🤖 **Geração automática de roteiro** usando modelos de IA (OpenAI, Gemini, DeepSeek, etc.)
- 🎙️ **Síntese de voz** com múltiplas opções (Edge TTS, Azure Cognitive Services)
- 🎬 **Montagem automática** de vídeo com materiais de alta qualidade
- 📝 **Legendas automáticas** com personalização de fonte e posição
- 🎵 **Música de fundo** com controle de volume
- 📱 **Múltiplos formatos** - Vertical (9:16) e Horizontal (16:9)
- 🌐 **Interface Web** intuitiva + API REST completa
- ⚡ **Processamento em lote** para gerar múltiplos vídeos

## 🚀 Como Usar

### Pré-requisitos
- Python 3.11+
- FFmpeg instalado no sistema
- ImageMagick (Windows: versão estática)

### Instalação Rápida

```powershell
# Clone o repositório
git clone https://github.com/WilqueMessias/usmov.git
cd usmov

# Crie ambiente virtual
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# Instale dependências
pip install -r requirements.txt
```

### Configuração

1. Copie `config.example.toml` para `config.toml`
2. Configure suas chaves de API no arquivo `config.toml`
3. Ajuste configurações de vídeo conforme necessário

### Executar

#### Interface Web (Streamlit)
```powershell
.\webui.bat
```
Acesse: http://localhost:8501

#### API REST
```powershell
python main.py
```
Documentação: http://127.0.0.1:8080/docs

## 📐 Formatos Suportados

- **Vertical**: 1080x1920 (ideal para TikTok, Instagram Stories, YouTube Shorts)
- **Horizontal**: 1920x1080 (ideal para YouTube, Facebook)

## 🎨 Personalização

### Fontes
Adicione suas fontes em `resource/fonts/`

### Música de Fundo
Coloque arquivos MP3 em `resource/songs/`

### Materiais de Vídeo
O sistema busca automaticamente materiais relevantes ou você pode fornecer seus próprios arquivos.

## � API Endpoints

- `POST /api/v1/videos` - Gerar vídeo completo
- `POST /api/v1/audio` - Gerar apenas áudio
- `POST /api/v1/subtitle` - Gerar apenas legendas
- `GET /api/v1/tasks/{id}` - Consultar status da tarefa
- `GET /api/v1/musics` - Listar músicas disponíveis

## ⚙️ Configurações Avançadas

### Modelos de IA Suportados
- OpenAI GPT-4/3.5
- Google Gemini
- DeepSeek
- Moonshot
- Azure OpenAI
- Ollama (local)
- E outros...

### Síntese de Voz
- Microsoft Edge TTS (gratuito)
- Azure Cognitive Services (premium)
- Múltiplas vozes e idiomas

## 📝 Exemplo de Uso

```python
import requests

# Gerar vídeo via API
response = requests.post("http://127.0.0.1:8080/api/v1/videos", json={
    "topic": "Os benefícios da meditação",
    "video_aspect": "9:16",
    "voice_name": "pt-BR-AntonioNeural",
    "background_music": "relaxing.mp3"
})

task_id = response.json()["data"]["task_id"]
print(f"Vídeo sendo gerado: {task_id}")
```

## 🛠️ Desenvolvimento

```powershell
# Ativar ambiente de desenvolvimento
.\.venv\Scripts\Activate.ps1

# Executar testes
python -m pytest test/

# Executar com recarga automática
python main.py --reload
```

## 📊 Status do Projeto

- ✅ Geração de roteiro com IA
- ✅ Síntese de voz
- ✅ Montagem de vídeo
- ✅ Interface web
- ✅ API REST
- ✅ Legendas automáticas
- 🔄 Melhorias na seleção de materiais
- 🔄 Upload automático para plataformas
- 🔄 Mais opções de personalização

## 🤝 Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para:

1. Fazer fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abrir um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 🆘 Suporte

Encontrou um problema? Abra uma [issue](https://github.com/WilqueMessias/usmov/issues) ou entre em contato.

---

**Feito com ❤️ por [Wilque Messias](https://github.com/WilqueMessias)**

# DeepSeek-R1 on Ollama using Open-WebUI Docker Deployment
Deploying Open-WebUI with Ollama using Docker Compose (CPU-only setup) provides a streamlined way to run AI models locally without GPU hardware. This implementation uses a custom entrypoint script to download the deepseek-r1:8b model automatically when a container is launched. Here's an implementation guide:

## 📋 Prerequisites
- Docker Engine v20.10.10+
- Docker Compose v2.20.0+
- 8GB RAM minimum (16GB recommended for larger models)
- 20GB+ free disk space
- Linux/macOS/WSL2 (Windows)

## 🚀 Quick Start
1. **Clone the repo**
```bash
git clone https://github.com/ntalekt/deepseek-r1-docker-compose.git
```
2. **Start Services**
```bash
docker compose up -d
```
3. **Verify Installation**
```bash
docker compose ps
```
Expected Output:
| NAME | COMMAND | SERVICE | STATUS | PORTS |
|------|---------|---------|--------|-------|
| ollama | "/bin/ollama serve" | ollama | running | 0.0.0.0:11434->11434/tcp |
| open-webui | "bash start.sh" | open-webui | running | 0.0.0.0:3000->8080/tcp |

4. **Check Logs**
```bash
docker compose logs -f ollama
docker compose logs -f open-webui
```

5. **Uninstall**
```bash
docker compose down --volumes --rmi all
```

## 🌐 Access the Web UI
1. Open browser to `http://localhost:3000`
2. Create admin account
3. Start chatting!
### Thinking
![Thinking](https://i.imgur.com/zLog1Gc.png)
### Answer
![Answer](https://i.imgur.com/nN4GnjT.png)

---

📄 **License**: MIT  
❗ **Note**: CPU inference will be significantly slower than GPU-accelerated setups. For production use, consider GPU-enabled hardware.

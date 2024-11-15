# DuckDuckGo Searchbot

# Downloading Ollama models

1. First Deploy Ollama from the compose file using the command:
```bash
docker compose up -d
```

2. Download the models
```bash
# embedding model
docker compose exec ollama ollama pull nomic-embed-text

# chat model
docker compose exec ollama ollama pull mistral:7b
```

3. Verify
```bash
# using curl on GNU/Linux or macOS
curl http://localhost:11434/v1/models

# on PowerShell on Windows
Invoke-WebRequest -Uri http://localhost:11434/v1/models
```

The output should be:
```json
{
	"object": "list",
	"data": [
		{
			"id": "mistral:7b",
			"object": "model",
			"created": 1731306883,
			"owned_by": "library"
		},
		{
			"id": "nomic-embed-text:latest",
			"object": "model",
			"created": 1731306482,
			"owned_by": "library"
		}
	]
}
```

# Chain Diagram

![chain](./graph.png)

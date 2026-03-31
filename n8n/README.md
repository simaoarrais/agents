# How to run
1. Run docker compose.
```bash
docker compose up -d
```

2. Pull Ollama model.
```bash
docker exec -i ollama ollama pull llama3.2:1b
```

3. Open n8n page [http://localhost:5678](http://localhost:5678)

4. Setup an owner account with whatever you want, this is just for testing purposes.

5. Click "Get started" and "skip".

6. Import workflows and refresh page.
```bash
docker exec -i n8n n8n import:workflow --separate --input=//workflows
```

7. Open a workflow, click in the Ollama Chat Model node and under "Credential", create a new one with the following url (you only need to do this once) and replace the ID in the journeys:
```text
http://ollama:11434
```
curl http://localhost:11434/api/generate -d '{
"model": "llama3.2:1b",
"prompt":"Why is the sky blue?"
}'

curl http://localhost:11434/api/chat -d '{
"model": "llama3.2:1b",
"messages": [
{ "role": "user", "content": "why is the sky blue?" }
]
}'

# Chat with your Data

The project motto is to develop low latency chatbot applications for any kind of data available. The implementation should/must use free open source tools. 

## Features

- [PDF chatbot] Upload docs in PDF format and have conversation with the chatbot. 

## Tech Stack used

- [Chroma](https://github.com/chroma-core/chroma/) as the vector store.
- [Ollama](https://ollama.ai/) to run an LLM locally and expose it to the web app.
- [LangChain.js](https://js.langchain.com) to call the models, perform retrieval, and generally orchestrate all the pieces.
- [Transformers.js](https://huggingface.co/docs/transformers.js/index) to run embeddings in the browser.
- [Docker](https://www.docker.com/products/docker-desktop/) to run chroma server.
- [Next.js](https://nextjs.org) to build web application.
- [TailwindCSS](https://tailwindcss.com) for design.
- [Vercel](https://vercel.com/) for hosting.

## Setup

### Clone/Fork

- Clone this repo by running `https://github.com/cosaimoSH/DataBot.git`
- Move to the root directory by running `cd DataBot`
- Install all dependencies by running `yarn install` 

### Install Ollama

Users will need to download and set up [Ollama](https://ollama.ai), then run the following commands to
allow the site access to a locally running Mistral instance:

```bash
$ OLLAMA_ORIGINS=https://pdf-chatter-beta.vercel.app/ OLLAMA_HOST=127.0.0.1:11435 ollama serve
```
Then, in another terminal window:

```bash
$ OLLAMA_HOST=127.0.0.1:11435 ollama pull mistral
```

### Install Docker

Download and set up [Docker](https://www.docker.com/products/docker-desktop/) to run chroma server.

### Setup Chroma

- Clone the repo [Chroma]() by running `git clone https://github.com/chroma-core/chroma`.
- Move to the directory by running `cd chroma`
- Before running the server, go to `docker-compose.yml` file and add this line under `environment` to resolve CORS issue during development `- CHROMA_SERVER_CORS_ALLOW_ORIGINS=["https://pdf-chatter-beta.vercel.app"]`
- Run docker command: `docker-compose up -d --build`

### Live version

Go to [PDFChatter](https://pdf-chatter-beta.vercel.app/) deployed at vercel.

### Upload your data [PDF] and Embed

Upload PDF document either by clicking or drag and drop.

<img width="1372" alt="Screenshot 2024-01-26 at 6 15 05 AM" src="https://github.com/cosmo3769/PDFChatter/assets/53268607/9fd61bbf-9546-448e-95e6-5941403ffbd9">

Click on embed.

<img width="1372" alt="Screenshot 2024-01-26 at 6 28 41 AM" src="https://github.com/cosmo3769/PDFChatter/assets/53268607/81a67416-798a-45b2-bcfb-66be0c0795df">

### Chat with your Doc

Ask your questions and have a conversation.

<img width="1375" alt="Screenshot 2024-01-26 at 6 46 16 AM" src="https://github.com/cosmo3769/PDFChatter/assets/53268607/b266230d-6482-4bb1-8e1a-dd76554c8a36">

## Future Scope
 
- [ ] Web scraper
- [ ] Persist data
- [ ] New chat
- [ ] Pop up button for 3rd party application
- [ ] New browser api for non-technical web end-users where a web app can request access to a locally running LLM, e.g. via a popup.

## Reference

* [Jacob Lee's local pdf chatbot](https://github.com/jacoblee93/fully-local-pdf-chatbot/tree/main)

CalorieSnap Pro — Versão pronta (Português) - gerado em 2025-11-11 23:50 UTC

Arquivos incluidos:
- index.html  -> arquivo principal do site (interface em português, vídeo de fundo, slideshow fallback, MobileNet para identificar alimentos, chat UI que se conecta a /api/chat).
- assets/     -> pasta sugerida para colocar: background.mp4, img1.jpg, img2.jpg, img3.jpg, img4.jpg (não incluídas no ZIP para economizar espaço).

INSTRUÇÕES RÁPIDAS PARA PUBLICAR (GitHub Pages):
1) Crie um repositório no GitHub (ex: nutriadryan-pro).
2) Extraia este ZIP e faça upload do conteudo (index.html e a pasta assets) em: Add file -> Upload files.
   - Importante: coloque o video 'background.mp4' na pasta 'assets' e as imagens (img1.jpg...img4.jpg) na mesma pasta.
3) Commit changes. Depois vá em Settings -> Pages e escolha Branch 'main' e / (root). Salve.
4) Aguarde alguns minutos e abra o link: https://SEU_USUARIO.github.io/NOME_DO_REPOSITORIO/

COMO CONFIGURAR O CHAT (ChatGPT) - REQUER BACKEND (EXPICAÇÃO SIMPLES):
- Por segurança, você NÃO deve colocar sua chave da OpenAI no código front-end. Crie uma função serverless (Netlify Functions, Vercel Serverless ou um pequeno endpoint em um VPS).
- Endpoint esperado: POST /api/chat
  Recebe: {"message":"texto do usuário"}
  Retorna JSON: {"reply":"texto do assistente"}

- Exemplo rápido (Node.js + Express) - NÃO coloque sua chave diretamente num repositório público:
  ```js
  // server.js (exemplo)
  const express = require('express');
  const fetch = require('node-fetch');
  const app = express();
  app.use(express.json());
  app.post('/api/chat', async (req,res)=>{
    const msg = req.body.message || '';
    // chame a API do OpenAI aqui com sua chave em variável de ambiente
    // exemplo: const response = await fetch('https://api.openai.com/v1/chat/completions', {...})
    // res.json({reply: assistant_text});
    res.json({reply: 'Este é um exemplo. Configure seu backend para usar OpenAI.'});
  });
  app.listen(3000);
  ```

- Plataformas recomendadas: Vercel, Netlify, Render. Todas têm docs para criar serverless functions facilmente e armazenar variáveis de ambiente (sua OPENAI_API_KEY).

OBS: MobileNet roda no navegador e precisa de internet para baixar os arquivos TF.js/MobileNet (CDN).

QUER QUE EU:
A) Gere um exemplo de função serverless pronta para deploy (Netlify/Vercel) que chama a OpenAI? (Eu gero o código do backend já pronto - você só precisa colocar a sua chave em variável de ambiente).
B) Adicione imagens/video ao ZIP (posso incluir imagens de exemplo e um vídeo leve se quiser — pode aumentar o tamanho do ZIP).
C) Personalize textos, nomes e cores (me diga o texto exato e o telefone/WhatsApp se quiser botão).

Me diz qual das opções (A / B / C) você quer agora e eu já gero.
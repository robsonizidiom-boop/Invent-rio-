# Controle de Bobinas — GitHub Pages

Aplicativo inicial para fotografar/importar etiquetas, executar OCR no navegador, revisar campos, salvar registros localmente e consolidar pesos por lote.

## Recursos
- Interface adaptada a celular e computador.
- Foto pela câmera ou seleção de imagem.
- OCR via Tesseract.js (Português + Inglês).
- Preenchimento automático experimental de lote, bobina, material e peso.
- Conferência manual obrigatória antes de salvar.
- IndexedDB no dispositivo, sem conta ou servidor de banco.
- Soma de pesos e quantidade de bobinas por lote.
- Filtros, alerta de possível duplicidade, exportação CSV e backup/restauração JSON.
- Manifesto e service worker básicos para permitir instalação/cache da interface.

## Publicar no GitHub Pages
1. Crie um repositório no GitHub, por exemplo `controle-bobinas`.
2. Extraia todos os arquivos deste ZIP e envie `index.html`, `manifest.json`, `sw.js` e `README.md` para a raiz do repositório.
3. Abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**, escolha `main` e `/ (root)`, e salve.
5. Aguarde a publicação e abra a URL fornecida pelo GitHub Pages.
6. No celular, abra a URL no navegador e use “Adicionar à Tela de Início”, se disponível.

## Importante
- Os dados ficam no IndexedDB do navegador e não são sincronizados entre dispositivos ou navegadores.
- Faça backups JSON frequentes. Limpar os dados do site/navegador pode apagar os registros.
- O OCR usa Tesseract.js por CDN e pode precisar de internet para baixar a biblioteca e os modelos de idioma na primeira vez. O cache básico não garante OCR offline completo.
- A extração automática de campos é heurística e depende da qualidade e do layout da etiqueta. Confirme cada campo, especialmente peso e lote.
- Para uso industrial crítico, teste com etiquetas reais, defina regras de validação e faça conferência independente.
- Se o repositório for público, o código será público. Não coloque fotos, etiquetas ou dados reais no repositório.
- O site não envia imagens nem registros para o GitHub; a biblioteca OCR é carregada de um CDN externo. Se precisar que nenhum recurso seja carregado de terceiros, hospede também a biblioteca e os modelos OCR localmente.

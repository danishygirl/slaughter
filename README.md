# SLAUGHTER — SITE

Home, Episódios e Anuário. HTML, CSS e JavaScript sem framework e sem etapa de build.

## GitHub + Cloudflare Workers
1. Extraia o ZIP e envie o CONTEÚDO da pasta slaughter à raiz do repositório GitHub.
2. Na Cloudflare, crie um Worker conectado a esse repositório.
3. Diretório raiz: / (a raiz do repositório). Comando de build: deixe vazio. Comando de deploy: npx wrangler deploy.
4. O arquivo wrangler.jsonc aponta para public. Não coloque package.json ou wrangler.jsonc dentro de public.
5. Commits na branch conectada atualizarão o site pela integração de build da Cloudflare.

## Alternativa: Cloudflare Pages
Conecte o repositório, selecione framework None, deixe o comando de build vazio e indique public como diretório de saída. Não use o comando wrangler deploy no Pages.

## Editar
- public/data.js: menu, descrição, personagens e episódios. Duplique objetos dos arrays para incluir novos registros. Os registros iniciais são exemplos, não personagens oficiais.
- public/style.css: variáveis no início controlam cores, fontes, largura do menu e bordas. As regras responsivas estão no final.
- public/index.html: Home e títulos sobre o pôster.
- public/assets/poster.webp: substitua pelo pôster sem textos, preferencialmente horizontal (1120×540 ou maior).
- public/assets/logo.webp: recorte da logo fornecida. Pode substituir por PNG transparente ou WEBP e alterar a extensão em cada HTML.
- public/assets/portrait-1.webp e portrait-2.webp: recortes ilustrativos da referência, repetidos nos cartões. Substitua por fotos de cada personagem e altere image em data.js. Use 480×600 ou proporção 4:5.
- public/assets/background.webp: referência escurecida por camada CSS. Para removê-la, edite body:before.

As imagens da primeira versão foram extraídas da referência enviada. O pôster contém a tipografia incorporada na imagem original; caso queira trocar títulos, substitua o pôster por arte limpa e edite hero-title em index.html.

## Nova página
Copie episodios.html, altere title e conteúdo; inclua {label:'Nome',href:'nome.html'} em menu de data.js. O menu aumenta automaticamente. Páginas extras com conteúdo estático podem usar data-page='custom'.

## Interações e desempenho
Anuário: hover e foco mostram sobreposição, clique/toque abre ficha; Esc ou botão X fecha. Busca por nome. Episódios abrem narração. Imagens WEBP locais, carregamento tardio fora da Home, sem bibliotecas, sem blur, animações curtas respeitando movimento reduzido. Não há cadastro nem banco de dados.

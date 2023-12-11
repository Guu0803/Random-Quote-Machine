# Random Quote Generator

Este é um aplicativo simples de geração de citações aleatórias desenvolvido por Gustavo Nogueira. O aplicativo consome a API Ninja Quotes para obter citações aleatórias em várias categorias.

## Funcionalidades
- Apresenta uma citação aleatória em uma interface atraente.
- A cor de fundo da janela muda a cada nova citação para proporcionar uma experiência visual dinâmica.
- Possui botão para gerar uma nova citação.
- Oferece links para compartilhar a citação no Twitter e Tumblr.

## Tecnologias Utilizadas
- **Vue.js:** O aplicativo é construído usando o framework Vue.js para a camada de visualização.
- **Axios:** Utilizado para fazer solicitações HTTP à API Ninja Quotes.
- **Font Awesome:** Ícones de redes sociais são provenientes da biblioteca Font Awesome.
- **CSS:** Estilização usando CSS, com efeitos de transição para uma experiência suave.

## Como Usar
1. Clone o repositório.
2. Instale as dependências usando o comando `npm install`.
3. Execute o aplicativo com `npm run serve`.
4. Abra o navegador e acesse o aplicativo em [http://localhost:8080](http://localhost:8080) (ou a porta que estiver em uso).

## Configuração
- A chave da API Ninja Quotes é configurada no cabeçalho da solicitação HTTP.
- A cor de fundo da janela e o efeito de hover são controlados por variáveis CSS personalizadas.

## Desenvolvimento
- O código é estruturado em um único componente Vue para manter a simplicidade.
- As citações são obtidas da API ao carregar o componente e ao pressionar o botão "New Quote".
- As cores dinâmicas são aplicadas usando variáveis CSS personalizadas.

## Autor
- **Gustavo Nogueira:** Desenvolvedor Front-end

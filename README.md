# <img src="https://github.com/Teyzinho/Next.js/assets/103509649/6c586ed8-13ae-466e-881d-911292a4f8eb" width="50px">Next.js
O Next.js é um framework de desenvolvimento web React de última geração, que permite a criação de aplicativos web modernos e escaláveis. Ele combina as melhores práticas do React com funcionalidades avançadas, como renderização do lado do servidor (SSR), geração de páginas estáticas e roteamento dinâmico.

## **Por que usar o Next.js?**

1. ****Possibilidade de criação de back-end de aplicações**** 
    
    **Como o Next.js funciona com um servidor Node.js rodando no lado back-end,** você pode criar uma estrutura, por mais simples que ela seja, para simular a conexão entre as partes de front-end e back-end de seu aplicativo. Além disso, o Next.js traz facilidades na hora de fazer conexões com a base de dados de sua aplicação.
    
2. ****Server-side rendering:****
    
     O Next.js permite que você renderize suas páginas no lado do servidor, o que melhora a velocidade de carregamento e o desempenho do seu aplicativo. Isso é especialmente útil para páginas com conteúdo dinâmico ou que requerem acesso a dados externos.
    
3. ****Geração de sites estáticos:****
    
     Com o Next.js, você pode gerar páginas estáticas no momento da construção, o que oferece um desempenho ainda melhor, reduzindo o tempo de carregamento. Isso é ideal para sites com conteúdo estático ou páginas que não precisam ser atualizadas com frequência.
    
4. ****Sistema de roteamento Dinâmico:****
    
    O Next.js facilita a criação de rotas dinâmicas para o seu aplicativo, permitindo que você crie URLs amigáveis e personalizadas. Isso é especialmente útil quando você tem várias páginas com estruturas semelhantes, como postagens de blog ou produtos em um site de comércio eletrônico.
    
    **Podemos criar rotas dinâmicas nesse framework, criando arquivos com o nome entre colchetes ([]), no lugar de criarmos um nome para a rotas dinâmicas.** Os arquivos podem ser criados dessa forma:
    ![image](https://github.com/Teyzinho/Next.js/assets/103509649/f612686a-2aeb-4bba-bc3b-de4192eee5f2)
5. ****Fast Refresh****
    
    **Esse recurso permite que seja feita a atualização dos elementos da página sem necessitar do recarregamento do navegador,** um recurso comum em aplicações que utilizem frameworks JavaScript.
    
6. P****ré configurado****
    
    **O pacote do framework disponível para utilizarmos no desenvolvimento já possui todas as configurações necessárias para bibliotecas como Webpack, Babel, Gulp, dentre outras.** Ou seja, não precisamos se preocupar em configurar nada para desenvolvermos um aplicativo.
    
7. **Recursos avançados de otimização:** 
    
    O Next.js oferece uma série de recursos de otimização, como carregamento sob demanda, pré-busca de dados e otimização de imagens. Essas funcionalidades ajudam a melhorar a experiência do usuário e a otimizar o desempenho do seu aplicativo.
    
8. ****Presença de CSS modularizado****
    
    **Podemos trabalhar com várias bibliotecas de estilo no desenvolvimento com o Next.js, tais como:**
    
    - styled-components;
    - Sass;
    - CSS comum;
    - TailwindCSS.
    
    A escolha de qual biblioteca será utilizada cabe a você. Verifique qual será a melhor para seu projeto.
    
9. ****Internacionalização****
    
    **Permite que seja criada a aplicação em um idioma e, ela ser traduzida para vários outros idiomas em tempo real**, utilizando a internacionalização.
    
10. ****Divisão do código****
    
    **Ao criar o React.js para um projeto, os arquivos dele são gerados em uma única pasta,** enquanto, com o Next.js, ele possui suporte com a divisão de arquivos, quando lidamos com roteamento.
    
11. **Ecossistema React:** 
    
    O Next.js é construído em cima do React, o que significa que você pode aproveitar todo o ecossistema React existente, incluindo a vasta coleção de bibliotecas e componentes disponíveis.
    
12. ****Divisão de código (code splitting)****
    
    **Ao criar o React.js para um projeto, os arquivos são gerados em uma única pasta,** enquanto que, com o Next.js, o suporte com a divisão de arquivos, quando lidamos com roteamento, ocorre como a pasta **api**, a pasta **pages**.
    
    ## Como Instalar

Para criar o projeto, digitamos o seguinte comando no teminal:

```
npx create-next-app@latest
```

Na instalação, irá seguir o seguinte Prompt:
![image](https://github.com/Teyzinho/Next.js/assets/103509649/f4972ffd-faa6-45cb-8626-6613643b56df)
### **[Execute o Servidor de Desenvolvimento](https://nextjs.org/docs/getting-started/installation#run-the-development-server)**

1. Execute `npm run dev` para iniciar o servidor de desenvolvimento.
2. Acesse `http://localhost:3000` para visualizar sua aplicação.
3. Edite `app/layout.tsx` ou `app/page.tsx` e salve para ver o resultado atualizado em seu navegador.

# ****Routing Fundamentals**** (**Fundamentos de Rotas)**

## **[Terminologia](https://nextjs.org/docs/app/building-your-application/routing#terminology)**

Primeiro, você verá esses termos sendo usados em toda a documentação. Aqui está uma referência rápida:
![image](https://github.com/Teyzinho/Next.js/assets/103509649/ca268257-adef-4fbe-946a-6d71752cad4d)
- **Tree:** Uma convenção para visualização de uma estrutura hierárquica. Por exemplo, uma árvore de componentes com componentes pai e filhos, uma estrutura de pastas, etc.
- **Subtree:** Parte de uma árvore, começando em uma nova raiz (primeira) e terminando nas folhas (última).
- **Root**: O primeiro nó em uma árvore ou sub-árvore, como um layout raiz.
- **Leaf:** Nodes em uma subárvore que não possuem filhos, como o último segmento em um caminho de URL.
![image](https://github.com/Teyzinho/Next.js/assets/103509649/249344f7-ff1a-446a-8f09-06e44d1d7275)
- **URL Segment:** Parte do caminho do URL delimitado por barras.
- **URL Path:** Parte da URL que vem após o domínio (composta de segmentos).

## **[Convenções de Arquivos](https://nextjs.org/docs/app/building-your-application/routing#file-conventions)**

O Next.js fornece um conjunto de arquivos especiais para criar UI com comportamento específico em rotas aninhadas:
![image](https://github.com/Teyzinho/Next.js/assets/103509649/998a95c3-4e09-4845-a253-90683fa2e172)

É bom saber: as extensões de arquivo .js, .jsx ou .tsx podem ser usadas para arquivos especiais.


## **Hierarquia de componentes**

**Os componentes React definidos em arquivos especiais de um segmento de rota são renderizados em uma hierarquia específica:**

- `layout.js`
- `template.js`
- `error.js` (React error boundary)
- `loading.js` (React suspense boundary)
- `not-found.js` (React error boundary)
- `page.js` or nested `layout.js`
![image](https://github.com/Teyzinho/Next.js/assets/103509649/e346b1d7-7e29-4f41-8831-e4d8a149937a)

## **[Colocação](https://nextjs.org/docs/app/building-your-application/routing#colocation)**

Além dos arquivos especiais, você tem a opção de colocar seus próprios arquivos (por exemplo, componentes, estilos, testes etc) dentro de pastas no diretório `app`.

Isso ocorre porque, embora as pastas definam rotas, somente o conteúdo retornado por `page.js` ou `route.js` é publicamente acessível.
![image](https://github.com/Teyzinho/Next.js/assets/103509649/43888b93-a230-42cd-ab70-f94c7ca88c18)
Você pode ver mais sobre Next.js na documentação oficial: https://nextjs.org

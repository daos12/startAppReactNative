# Introdução ao React Native com Expo

Projeto desenvolvido com finalidade educacional, seguindo uma abordagem prática e passo a passo para aprender os principais fundamentos do desenvolvimento de aplicações utilizando **React Native, Expo e TypeScript**.

O objetivo é compreender desde a preparação do ambiente e criação do primeiro projeto até conceitos importantes como componentes, estilização, propriedades, estados e navegação.

---

## Objetivo do Projeto

Este projeto tem como objetivo apresentar os fundamentos necessários para iniciar o desenvolvimento de aplicações mobile com React Native.

Durante o desenvolvimento são trabalhados conceitos como:

- Introdução ao React Native;
- Utilização do Expo;
- Criação e configuração de projetos;
- Estrutura de pastas;
- JSX e TSX;
- Componentes;
- Componentização;
- Propriedades (Props);
- Estados;
- Eventos;
- Estilização;
- Flexbox;
- Navegação com Expo Router;
- Execução no Android, iOS e Web;
- Testes utilizando Expo Go;
- Organização e boas práticas de código.

---

## Tecnologias Utilizadas

O projeto utiliza as seguintes tecnologias:

- React Native
- React
- Expo
- Expo Router
- TypeScript
- JavaScript
- Node.js
- NPM
- Visual Studio Code

---

## Pré-requisitos

Antes de iniciar, é recomendado possuir instalado:

### Node.js

O Node.js será utilizado para executar as ferramentas necessárias para criação e gerenciamento do projeto.

Verifique a instalação utilizando:

```bash
node --version
```

Também verifique o NPM:

```bash
npm --version
```

### Visual Studio Code

Será utilizado como editor para desenvolvimento e organização dos arquivos do projeto.

### Expo Go

Para executar o projeto diretamente em um dispositivo físico, poderá ser utilizado o aplicativo **Expo Go**.

O computador e o smartphone deverão, preferencialmente, estar conectados à mesma rede.

---

## Criando o Projeto

Para criar um novo projeto utilizando Expo:

```bash
npx create-expo-app@latest
```

Também é possível informar diretamente o nome:

```bash
npx create-expo-app@latest meu-app
```

Depois da criação, acesse a pasta:

```bash
cd meu-app
```

Para abrir o projeto no Visual Studio Code:

```bash
code .
```

---

## Executando o Projeto

Para iniciar o servidor de desenvolvimento:

```bash
npx expo start
```

Será apresentado no terminal o ambiente de desenvolvimento do Expo.

Durante a execução, alguns comandos poderão ser utilizados:

```text
a → Abrir no Android
i → Abrir no iOS
w → Abrir na Web
r → Recarregar aplicação
Ctrl + C → Encerrar
```

---

## Executando com Expo Go

Também é possível executar o projeto diretamente em um smartphone.

1. Instale o **Expo Go** no celular.
2. Execute o projeto:

```bash
npx expo start
```

3. Aguarde a geração do QR Code.
4. Abra o Expo Go ou utilize a câmera do smartphone.
5. Leia o QR Code.
6. Aguarde o carregamento da aplicação.

As alterações realizadas no código poderão ser refletidas durante o desenvolvimento, facilitando os testes.

---

## Organização do Projeto

Uma possível organização utilizada durante os estudos é:

```text
projeto/
│
├── assets/
│
├── src/
│   │
│   ├── app/
│   │   └── index.tsx
│   │
│   └── components/
│       └── Button/
│           ├── index.tsx
│           └── styles.ts
│
├── node_modules/
├── app.json
├── package.json
├── package-lock.json
├── tsconfig.json
└── README.md
```

### `src`

Concentra os arquivos desenvolvidos para a aplicação.

### `app`

Pode concentrar as páginas e rotas utilizadas pela aplicação.

### `components`

Utilizada para armazenar componentes reutilizáveis.

### `assets`

Armazena recursos como imagens, ícones e outros arquivos utilizados pela aplicação.

---

## Componentes

Uma das principais características do React Native é a utilização de componentes.

Um componente pode representar uma parte da interface, como:

- Botão;
- Cabeçalho;
- Card;
- Campo de formulário;
- Menu;
- Tela;
- Lista;
- Item de uma lista.

Exemplo:

```tsx
import { Text, View } from "react-native";

export default function Index() {
  return (
    <View>
      <Text>Hello World!</Text>
    </View>
  );
}
```

Os componentes permitem dividir a aplicação em pequenas partes reutilizáveis e de manutenção mais simples.

---

## Estilização

No React Native podemos utilizar `StyleSheet` para organizar a estilização dos componentes.

```tsx
import { StyleSheet, Text, View } from "react-native";

export default function Index() {
  return (
    <View style={styles.container}>
      <Text style={styles.title}>React Native</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
    padding: 32,
  },

  title: {
    fontSize: 24,
    fontWeight: "bold",
  },
});
```

A sintaxe possui várias semelhanças com CSS, porém propriedades compostas utilizam **camelCase**.

No CSS:

```css
background-color: blue;
font-size: 20px;
```

No React Native:

```tsx
backgroundColor: "blue",
fontSize: 20,
```

---

## Flexbox

O React Native utiliza Flexbox para organização dos elementos da interface.

Algumas propriedades importantes:

```tsx
flex: 1
```

```tsx
justifyContent: "center"
```

```tsx
alignItems: "center"
```

```tsx
flexDirection: "row"
```

Diferentemente do CSS tradicional para Web, o Flexbox já faz parte naturalmente do sistema de layout utilizado pelo React Native.

---

## Componentização

Podemos criar nossos próprios componentes para evitar repetição de código.

Exemplo de estrutura:

```text
components/
└── Button/
    ├── index.tsx
    └── styles.ts
```

Essa estratégia permite separar estrutura, comportamento e estilização.

Além disso, facilita a reutilização do mesmo componente em diferentes telas.

---

## Props

As **Props** permitem enviar informações para um componente.

Exemplo:

```tsx
<Button title="Entrar" />
<Button title="Cadastrar" />
<Button title="Salvar" />
```

Assim, um único componente poderá apresentar diferentes conteúdos dependendo das propriedades recebidas.

Isso aumenta a reutilização do código.

---

## Estados

Os estados são utilizados quando determinada informação precisa mudar durante a execução da aplicação.

Um dos principais recursos utilizados para isso é o `useState`.

Exemplo:

```tsx
import { useState } from "react";
import { Button, Text, View } from "react-native";

export default function Index() {
  const [contador, setContador] = useState(0);

  return (
    <View>
      <Text>{contador}</Text>

      <Button
        title="Adicionar"
        onPress={() => setContador(contador + 1)}
      />
    </View>
  );
}
```

Sempre que o estado for atualizado, o React poderá atualizar a interface de acordo com o novo valor.

---

## Navegação

Projetos Expo podem utilizar o **Expo Router** para organização da navegação.

A navegação baseada em arquivos permite que os próprios arquivos e diretórios representem as rotas da aplicação.

Exemplo:

```text
app/
├── index.tsx
├── login.tsx
└── profile.tsx
```

Cada arquivo poderá representar uma tela ou rota diferente.

---

## Dependências

As bibliotecas utilizadas pelo projeto são registradas no arquivo:

```text
package.json
```

Caso o projeto seja baixado ou clonado do GitHub, as dependências podem ser instaladas utilizando:

```bash
npm install
```

ou:

```bash
npm i
```

Isso recriará a pasta:

```text
node_modules
```

Por esse motivo, normalmente a pasta `node_modules` não é enviada ao GitHub.

---

## Clonando o Projeto

Para baixar este projeto utilizando Git:

```bash
git clone URL_DO_REPOSITORIO
```

Entre na pasta:

```bash
cd NOME_DO_PROJETO
```

Instale as dependências:

```bash
npm install
```

Depois execute:

```bash
npx expo start
```

---

## Comandos Principais

```bash
# Criar projeto
npx create-expo-app@latest

# Entrar na pasta
cd nome-do-projeto

# Instalar dependências
npm install

# Iniciar aplicação
npx expo start

# Abrir no Visual Studio Code
code .
```

Durante a execução do Expo:

```text
a → Android
i → iOS
w → Web
r → Recarregar
Ctrl + C → Encerrar
```

---

## Conceitos Trabalhados

Ao concluir este projeto, espera-se compreender os fundamentos de:

**React Native → Expo → TypeScript → JSX/TSX → Componentes → Props → Estados → Eventos → Estilização → Flexbox → Componentização → Navegação**

Esses conceitos formam uma base importante para avançar no desenvolvimento de aplicações mobile mais completas.

---

## Finalidade Educacional

Este repositório foi desenvolvido com finalidade **educacional**, como material de apoio para aulas práticas de desenvolvimento de aplicações.

A proposta é permitir que os conteúdos sejam construídos progressivamente, acompanhando cada etapa diretamente no código e observando o resultado durante a execução da aplicação.

O código poderá ser adaptado e expandido durante as aulas para criação de novos exercícios e projetos.

---

## Material de Referência

O projeto foi desenvolvido acompanhando e estudando o conteúdo apresentado no vídeo:

**React Native — aula sobre fundamentos e desenvolvimento com Expo**

YouTube:

https://www.youtube.com/watch?v=20WH5xB54Hc

O conteúdo foi utilizado como referência de estudo, com organização e complementações para utilização didática.

---

## Uso em Sala de Aula

Material utilizado para fins de aprendizagem e demonstração prática dos fundamentos do desenvolvimento mobile.

Os alunos poderão utilizar o projeto para:

- acompanhar a construção da aplicação;
- analisar a estrutura do React Native;
- modificar componentes;
- experimentar diferentes estilos;
- trabalhar com Props e estados;
- criar novas telas;
- implementar navegação;
- desenvolver novos recursos a partir da estrutura inicial.

---

## Licença

Projeto destinado principalmente para **estudo e fins educacionais**.

---

**Desenvolvido para fins educacionais e aprendizagem de React Native com Expo.**

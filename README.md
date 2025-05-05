# Unoesc Thesis

Repositório contendo funções para formatações de TCC seguindo o padrão da Unoesc Chapecó.

## Configuração inicial

Para o arquivo funcionar, defina:

```latex
    \documentclass{unoesc-thesis}
```

> Importante notar que o arquivo `.cls` precisa estar no mesmo nível do arquivo `.tex`.

Após isso defina os campos do trabalho:

1. Use `\titulo{Seu título}`
2. Use `\autor{Seu nome}`
3. Use `\data{Ano}`
4. Use `\cidade{Cidade do campus}`
5. Use `\descricao{Descrição que define o trabalho, "Projeto de Trabalho de Conclusão de Curso ..."}`
6. Use `\coautor{Função do coautor (Orientador)}{Nome do coautor}`
7. Use `\palavraschave{palavra1, palavra 2, palavra 3, ...}` no mínimo três separadas por vírgula

> Sempre defina todos os campos acima para o funcionamento correto.

## Comandos básicos

Não use os comandos padrão do latex/overleaf, sempre use os da biblioteca para garantir compatibilidade e que as formatações estejam corretas.

### Capítulo

Para capítulos (Introdução, Revisão de Literatura, etc.) use o comando `\capitulo{<nome do capitulo>}`, isso fará a adição ao sumário e a formatação correta.

### Sub-Seção

Da mesma forma do capítulo, a formatação fica correta se usar `\secao{<titulo da secao>}`

### Sub-Sub-Seção

Ainda há essa forma de aninhar os conceitos e partes do trabalho, para isso use `\subsubsecao{<titulo>}`

### Imagem

Para adicionar uma imagem e adicionar na Lista de Ilustrações:

```latex
\begin{ilustracao}{<label que aparece na lista de ilustrações>}{<fonte a ser citada, não precisa colocar Fonte:>}
    \centering
    \includegraphics{<caminho da imagem>}
    \label{<fig:label-do-latex>}
\end{ilustracao}
```

### Bullets

Para adicionar bullet points, não funciona com o `itemize`, precisa usar o environment `marcadores` do unoesc-thesis:

```latex
\begin{marcadores}
   \item ...
   \item ...
\end{marcadores}
```

### Siglas e Abreviações

> As siglas precisam ser definidas no preâmbulo do documento (antes do `\begin{document}`).
> Para isso use uma das opções abaixo:

- ```latex
   \abreviatura{<chave>}{<abreviatura>}{<nome longo>}
  ```
- ```latex
   \sigla{<chave>}{<sigla>}{<nome longo>}
  ```

A chave é o que vai usar para referenciar dentro do seu trabalho, com o comando `\ac{<chave>}`. Isso vai adicionar as siglas que usou no trabalho em uma página chamada Abreviações e Siglas de forma automática.

## Referências

Tenha um arquivo `.bib` contendo todas as referências que vai usar no trabalho salvo no projeto, após isso importe ele usando o comando `\bibliography{<caminho do arquivo>}`.

Pronto! Suas referências serão geradas conforme as usar no trabalho com `\cite{nomeDaReferencia}` (para referências fora do texto), e `\textcite{nomeDaReferência}` para citações no texto no formato Nome (Ano).

## Dica

Pode separar o seu trabalho em múltiplos arquivos `.tex`, um para cada capítulo por exemplo, e depois importar eles dentro do arquivo principal com o comando `\input{caminho-do-arquivo}`. Isso permite lidar melhor com trabalhos longos.

> Não defina nenhum comando de preâmbulo fora do arquivo principal. Ex: `\begin{document}`

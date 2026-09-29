# Desafio DevSecOps — Gerenciador de Tarefas

## Sobre o Projeto
Este repositório faz parte do desafio prático do módulo de DevSecOps da ADA Tech.
Você receberá este projeto com vulnerabilidades propositais e uma pipeline incompleta.
Seu objetivo é **implementar a pipeline de segurança** e **corrigir as vulnerabilidades**.

## Estado atual
A pipeline está **incompleta**. Os steps de segurança precisam ser implementados por você.

## Sua missão
1. Implementar os steps de segurança no `pipeline.yml`
2. Fazer a pipeline **quebrar** ao detectar os problemas
3. Corrigir as vulnerabilidades encontradas
4. Fazer a pipeline **passar** com tudo verde ✅
5. Documentar o funcionamento da pipeline neste README

## O que implementar
- [ ] Secrets Scanning com **Gitleaks**
- [ ] SAST com **Semgrep**
- [ ] SCA com **Grype**
- [ ] Deploy com **GitHub Pages**

## 🚀 O que é e como funciona esta Pipeline de Segurança?
Uma **Pipeline de Segurança** é como uma esteira de testes automatizada. Cada vez que um desenvolvedor termina de escrever uma parte do código e tenta enviar o projeto para a internet, essa esteira inspeciona o código atrás de falhas. 

Se qualquer um dos testes encontrar um problema, a esteira trava e impede que o site vá ao ar com vulnerabilidades. 

Neste desafio, configurei **3 etapas de proteção (Gates)** essenciais:

### 1. 🔑 Secrets Scanning (Gitleaks)
* **O que ele faz:** Funciona como um detetive que varre todo o código procurando por "segredos" esquecidos, como senhas de bancos de dados, chaves de API ou credenciais de acesso.
* **Por que importa:** É muito comum desenvolvedores esquecerem senhas fixas dentro do código por pressa ou descuido. Se esse código for enviado para um repositório público, qualquer hacker poderia roubar essas senhas e invadir os sistemas da empresa. O Gitleaks impede que isso aconteça.

### 2. 🔍 SAST - Análise Estática (Semgrep)
* **O que ele faz:** Ele lê o texto do código (como se estivesse revisando uma redação) procurando por erros de estrutura, boas práticas ou funções perigosas que deixam o sistema vulnerável (como o uso inadequado de `eval()` e `innerHTML`).
* **Por que importa:** O Semgrep encontra falhas de segurança antes mesmo do programa ser executado ou compilado. Isso permite que o desenvolvedor corrija brechas que poderiam ser usadas por invasores para roubar dados dos usuários (ataques de XSS) ou travar o site.

### 3. 📦 SCA - Análise de Dependências (Grype)
* **O que ele faz:** Ele analisa os pacotes e bibliotecas de terceiros que o projeto usa (como `axios` e `express`) e checa em um banco de dados mundial se essas ferramentas externas possuem vírus ou falhas conhecidas (CVEs).
* **Por que importa:** Hoje em dia, nenhum programador cria tudo do zero; usamos muitos códigos prontos da internet. Se uma dessas ferramentas estiver desatualizada ou com falhas, o nosso site também fica vulnerável. O Grype garante que só usemos pedaços de código seguros e atualizados.


## URL de Produção
https://github.com/MarioRondon09/projeto-devsecop-desafio.git

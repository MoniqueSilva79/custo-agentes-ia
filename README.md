# 🤖 Custo por Tarefa de Agentes de IA (FinOps de IA)

**🔗 Demo ao vivo: https://moniquesilva79.github.io/custo-agentes-ia/**

Calculadora que compara cenários de agentes de IA pelo **custo por tarefa concluída com sucesso**, e não pelo preço por token. Um modelo barato que erra mais pode sair caro, porque cada tentativa falha também é paga.

## 🎯 Problema que resolve
Times que colocam agentes de IA em produção costumam escolher o modelo pelo preço por milhão de tokens. Mas o que importa para o orçamento é quanto custa entregar a tarefa pronta: número de passos, tamanho do contexto e, principalmente, quantas tentativas o agente precisa até acertar.

## ✨ Funcionalidades
- Até 3 cenários lado a lado (ex.: modelo grande, modelo pequeno e roteamento entre os dois)
- Passos por tentativa, tokens de entrada e saída, preços e taxa de sucesso editáveis
- Custo por tentativa, tentativas por tarefa, custo por tarefa concluída e custo mensal em R$
- Gráfico comparativo e destaque automático do cenário mais econômico
- Aviso quando o cenário de tentativa mais barata perde no custo final

## 🧮 Como o cálculo funciona
```
custo por tentativa = passos × (tokens_entrada × preço_entrada + tokens_saída × preço_saída) ÷ 1.000.000
tentativas esperadas = 1 ÷ taxa de sucesso
custo por tarefa concluída = custo por tentativa ÷ taxa de sucesso
```

## 🧰 Tecnologias
HTML, CSS e JavaScript puros, sem frameworks, sem dependências e sem servidor. Publicado no GitHub Pages.

## 🚀 Como rodar localmente
```bash
git clone https://github.com/MoniqueSilva79/custo-agentes-ia.git
cd custo-agentes-ia
# abra o index.html no navegador, ou sirva a pasta:
python -m http.server 8000   # e acesse http://localhost:8000
```

## ⚠️ Limitações
Os preços que vêm preenchidos são **ilustrativos**. Use sempre a tabela oficial do provedor (Vertex AI, Bedrock, Azure OpenAI etc.) e meça a taxa de sucesso real do seu agente com um conjunto de testes.

## 🗺️ Próximos passos
- [ ] Importar logs reais de uso (tokens por chamada) em CSV
- [ ] Modelar cache de contexto e lotes (batch)
- [ ] Simular roteamento por dificuldade da tarefa

---
Projeto autoral de **Monique da Silva Cruz**: [LinkedIn](https://www.linkedin.com/in/moniquesilva-cloud-ti-projetos-latam) · [outros projetos](https://github.com/MoniqueSilva79)

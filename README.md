![Version](https://img.shields.io/badge/version-0.1.0-blue)
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Java](https://img.shields.io/badge/Java-Spring%20Boot%20%2F%20Quarkus-red)
![Python](https://img.shields.io/badge/Python-ML%20Service-green)
![FAISS](https://img.shields.io/badge/Vector%20Search-FAISS%20%7C%20Pinecone-purple)
![License](https://img.shields.io/badge/license-Educacional-lightgrey)

# Sistema de Recomendação de Conteúdo

Projeto de backend focado em Inteligência Artificial para recomendação de conteúdos baseada em similaridade semântica, utilizando busca vetorial e modelos de linguagem para gerar embeddings.

## 👨‍💻 Autores

- [Ítalo Leal (Lealwbs)](https://github.com/Lealwbs)
- [Vitor Hugo (PureVice)](https://github.com/PureVice)

---

## 📌 Visão Geral

Plataformas com grandes volumes de dados (produtos, artigos, posts, etc.) têm dificuldade em conectar usuários ao que realmente é relevante. A busca tradicional por palavras-chave não entende contexto, o que gera experiências ruins e baixo engajamento.

Este projeto resolve isso com:

* Processamento semântico de textos
* Embeddings gerados por IA
* Busca vetorial para encontrar itens semelhantes

Tudo exposto por uma API pronta para integração.

---

## 🧩 Arquitetura

O sistema é dividido em dois módulos principais:

| Módulo                | Responsabilidade                           | Tecnologias                                   |
| --------------------- | ------------------------------------------ | --------------------------------------------- |
| API Principal         | Endpoints, regras de negócio, orquestração | Java, Spring Boot/Quarkus, REST               |
| Motor de Recomendação | Embeddings, busca vetorial, similaridade   | Python, Sentence Transformers, FAISS/Pinecone |

Comunicação entre módulos via HTTP (REST).

![alt](docs\uml.png)

---

## 🎯 Escopo

### Incluído

* API de recomendação
* Motor de IA
* Busca vetorial
* Cadastro e remoção de itens
* Atualização do índice
* Filtros por categoria
* Logs e métricas

### Fora do escopo

* Interface gráfica para usuário final
* Processamento de áudio ou vídeo
* Pagamentos
* Geração de conteúdo (não é um LLM gerador de texto)

---

## 👥 Tipos de Usuário

| Tipo                   | Descrição                                                      |
| ---------------------- | -------------------------------------------------------------- |
| Cliente                | Sistema externo que consome a API (e-commerce, blog, intranet) |
| Administrador de Dados | Gerencia catálogo e índice vetorial                            |
| Desenvolvedor          | Integra sistemas usando a API                                  |

---

## ⚙️ Funcionalidades Principais

| Funcionalidade         | Descrição                            |
| ---------------------- | ------------------------------------ |
| Recomendação por texto | Envia texto e recebe itens similares |
| Cadastro de itens      | Admin cadastra novos itens           |
| Geração de embeddings  | Vetores gerados automaticamente      |
| Atualização de índice  | Reindexação vetorial                 |
| Filtro por categoria   | Refina resultados                    |
| Remoção de itens       | Exclusão do catálogo                 |
| Métricas               | Acurácia e desempenho                |
| Health Check           | Status da API                        |
| Logs                   | Registro de requisições              |

---

## 📐 Requisitos Não Funcionais

| Requisito         | Meta                        |
| ----------------- | --------------------------- |
| Tempo de resposta | < 200ms                     |
| Capacidade        | 10.000+ itens               |
| Linguagem API     | Java                        |
| Linguagem IA      | Python                      |
| Comunicação       | REST                        |
| Conformidade      | LGPD (anonimização de logs) |

---

## 🛠️ Tecnologias Utilizadas

| Camada         | Tecnologias                   |
| -------------- | ----------------------------- |
| Backend        | Java (Spring Boot/Quarkus)    |
| IA             | Python, Sentence Transformers |
| Busca Vetorial | FAISS ou Pinecone             |
| Comunicação    | REST                          |

---

## 🚀 Como Rodar o Projeto

### Pré-requisitos

* Java 17+
* Python 3.9+
* Pip
* Docker (opcional)

### Passos

1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/seu-repo.git
```

2. Subir o serviço de IA

```bash
cd ml-service
pip install -r requirements.txt
python app.py
```

3. Subir a API Java

```bash
cd api-java
./mvnw spring-boot:run
```

4. Endpoints locais

* API: [http://localhost:8080](http://localhost:8080)
* Serviço ML: [http://localhost:5000](http://localhost:5000)

---

## 📡 Exemplos de Uso

### Requisição

```http
POST /recommend
{
  "text": "notebook para programação"
}
```

### Resposta

```json
[
  { "id": 12, "nome": "Notebook Gamer X", "score": 0.91 },
  { "id": 45, "nome": "Notebook Dev Pro", "score": 0.88 }
]
```

---

## 📊 Métricas

* Acurácia das recomendações
* Tempo médio de resposta
* Volume de requisições

---

## 📊 Documentos

- [Diagrama UML](./docs/uml.puml) - Diagrama de classes do sistema
- [Documento de Visão](./docs/Documento%20de%20Visão.pdf) - Especificação
- [API Documentation](./docs/api.md) - Documentação dos endpoints (IMPLEMENTAR SWAGGER)

---

## 📄 Licença

Projeto acadêmico para fins educacionais.

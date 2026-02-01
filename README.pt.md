<div align="center">

[![en](https://img.shields.io/badge/lang-en-blue.svg)](README.md)
[![pt-br](https://img.shields.io/badge/lang-pt--br-green.svg)](README.pt.md)

# AppFlowy · Coolify

### Implante seu workspace. Seja dono dos seus dados.

*Uma maneira simples de auto-hospedar o AppFlowy usando Coolify*

<br>

[Começar](#começar) · [Recursos](#recursos) · [Requisitos](#requisitos)

<br>
<br>

</div>

---

<br>

## Visão Geral

AppFlowy encontra Coolify. Experimente a liberdade de um workspace colaborativo auto-hospedado com a simplicidade de uma implantação moderna.

Este repositório fornece tudo o que você precisa para implantar o AppFlowy—uma alternativa open-source e focada em privacidade ao Notion—em sua própria infraestrutura usando a elegante plataforma como serviço da Coolify.

<br>

### Por Que Isso Importa

**Privacidade em Primeiro Lugar**  
Seus dados permanecem em seus servidores. Sem terceiros. Sem compromissos.

**Simplicidade Integrada**  
Implantação com um clique. SSL automático. Zero complexidade DevOps.

**Controle Completo**  
Seja dono do seu workspace. Escale nos seus termos. Personalize sem limites.

<br>
<br>

## Recursos

<table>
<tr>
<td width="50%">

### 🎯 Implantação com Um Clique
Inicie o AppFlowy com uma única ação. Coolify cuida da complexidade.

</td>
<td width="50%">

### 🔒 Segurança Empresarial
Certificados SSL automáticos, padrões seguros e isolamento completo de dados.

</td>
</tr>
<tr>
<td width="50%">

### 📦 Nativo em Contêiner
Construído em Docker. Portável, reproduzível e testado em batalha.

</td>
<td width="50%">

### 🚀 Pronto para Produção
Configurações otimizadas para estabilidade, performance e escala.

</td>
</tr>
</table>

<br>
<br>

## Começar

### Requisitos

Antes de começar, certifique-se de ter:

- Um servidor com Docker instalado (Linux recomendado)
- Coolify instalado e em execução ([Obter Coolify](https://coolify.io))
- Nome de domínio com DNS configurado (opcional, recomendado para SSL)
- Mínimo de 2GB RAM, 2 núcleos de CPU

<br>

### Implantação Rápida

**1. Acesse Seu Painel Coolify**

Navegue até sua instância Coolify em `https://seu-dominio-coolify.com`

<br>

**2. Crie um Novo Serviço**

```
Painel → Adicionar Novo Recurso → Docker Compose
```

<br>

**3. Configure o AppFlowy**

Aponte para a imagem Docker do AppFlowy:
```
appflowyinc/appflowy_cloud
```

Configure as variáveis de ambiente conforme necessário para sua configuração.

<br>

**4. Implante**

Clique em implantar. Coolify orquestra tudo—contêineres, rede, armazenamento, SSL.

Seu workspace é iniciado em minutos.

<br>

**5. Acesse o AppFlowy**

Abra seu domínio configurado ou endereço IP. Crie seu primeiro workspace.

<br>
<br>

## Configuração

### Configurações Essenciais

**Banco de Dados**  
PostgreSQL recomendado. Coolify pode provisionar isso automaticamente.

**Armazenamento**  
Configure volumes persistentes para dados do usuário e anexos.

**Domínio & SSL**  
Defina seu domínio personalizado. Coolify cuida dos certificados SSL via Let's Encrypt.

**Recursos**  
Ajuste limites de memória e CPU com base no tamanho da sua equipe.

<br>

### Variáveis de Ambiente

Personalize sua implantação com estas variáveis-chave:

| Variável | Descrição | Padrão |
|----------|-----------|--------|
| `DATABASE_URL` | String de conexão PostgreSQL | Obrigatório |
| `GOTRUE_URL` | URL do serviço de autenticação | Obrigatório |
| `STORAGE_PATH` | Localização de armazenamento persistente | `/data` |

<br>
<br>

## Suporte

### Recursos

- [Documentação AppFlowy](https://docs.appflowy.io)
- [Documentação Coolify](https://coolify.io/docs)
- [Comunidade AppFlowy](https://discord.gg/appflowy)

<br>

### Obter Ajuda

Encontrou um problema? Tem uma pergunta?

Abra uma issue neste repositório ou entre em contato com as comunidades acima.

<br>
<br>

---

<div align="center">
<br>

**Construído com cuidado para equipes que valorizam privacidade e controle**

<br>

*AppFlowy · Coolify · Docker*

<br>
<br>

</div>

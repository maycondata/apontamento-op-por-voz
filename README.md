# MVP – Apontamento de OP por Voz (Whisper + gTTS + CSV)

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/maycondata/apontamento-op-por-voz/blob/main/Assistente_de_Apontamento_Industrial_por_Voz.ipynb)

Este projeto é um MVP 100% gratuito (sem API paga) para **apontamento de Ordem de Produção (OP) por voz**.
O usuário fala, ex: **"Apontar OP 1015"**, o sistema transcreve com Whisper, extrai a OP, pede confirmação (**sim/não**) e salva o resultado em **CSV**.

## Funcionalidades
- Gravação de áudio no navegador (Google Colab + JavaScript)
- Speech-to-Text com Whisper (rodando local no Colab)
- Extração da OP via regras (regex)
- Confirmação por voz (sim/não)
- Resposta em áudio com gTTS
- Registro do apontamento em `apontamentos.csv`

## Pré-requisitos
- Permitir acesso ao microfone no navegador (Google Colab)
- Whisper pode exigir ffmpeg no ambiente
- gTTS requer internet para sintetizar o áudio


## Fluxo do MVP
1. Usuário fala: "Apontar OP 1015"
2. Whisper transcreve
3. Sistema extrai OP e pergunta: "Confirma apontar OP 1015?"
4. Usuário responde: "Sim" ou "Não"
5. Sistema grava e salva em CSV com timestamp

## Como executar (recomendado)
- Abra o notebook no Google Colab
- Execute as células na ordem
- Permita acesso ao microfone
- Teste com:
  - "Apontar OP 1015"
  - Responda "Sim" ou "Não"

## Saída (CSV)
Arquivo: `/content/apontamentos.csv`

Campos:
- timestamp
- op
- status (APONTADO / CANCELADO / INDEFINIDO)
- comando_transcrito
- confirmacao_transcrita

## Tecnologias
- Whisper (Speech-to-Text)
- gTTS (Text-to-Speech)
- Python + JavaScript (MediaRecorder)
- pandas (visualizar CSV)

## Próximos passos (ideias)
- Loop contínuo (modo operador)
- Capturar quantidade boa/refugo
- Motivos de parada (dropdown por voz)
- Dashboard simples com os apontamentos

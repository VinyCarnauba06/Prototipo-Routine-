
---

## Configuração do projeto (informações do projeto)

- **API de clima**: o projeto consome a OpenWeatherMap para obter condição e temperatura atual.  
  - A chave da API deve ser inserida na variável `API_KEY` em `script.js`.
  - O MVP utiliza requisições diretas ao endpoint público (frontend). Em produção, recomenda-se encaminhar requisições através de um backend para proteger a chave e reduzir custo/exposição.

- **Persistência**: tarefas são salvas em `localStorage` sob a chave `tasks_v1`. Esse comportamento permite uso offline e recuperação dos dados no mesmo navegador/dispositivo.

- **Alerta climático**: a verificação de alerta para tarefas com categoria **Ao ar livre** é feita com base na condição meteorológica atual retornada pela API. A lógica vigente é propositalmente simples no MVP (detecção de chuva/tempestade). Pode ser estendida para previsões por horário, thresholds de vento/temperatura, etc.

---

## Limitações e pontos para evolução

1. **Segurança da API Key**: atualmente a chave fica no frontend — mover para backend é recomendado.  
2. **Notificações reais**: alertas são exibidos via `alert()` e logs; ideal evoluir para notificações push (FCM) ou sistema de notificações in-app.  
3. **Sincronização multi-dispositivo**: a solução atual usa `localStorage`. Para multi-dispositivo, integrar um backend (ex.: Node.js + MongoDB) e autenticação (Firebase/Auth).  
4. **Cobertura meteorológica**: o MVP utiliza condição atual por cidade; futuramente adicionar previsões por horário, geolocalização e tolerâncias configuráveis pelo usuário.  
5. **Testes e qualidade**: incluir testes unitários e E2E, além de linter/formatter no pipeline CI.

---

## Boas práticas recomendadas para produção

- Proteja a chave da API movendo chamadas para um backend.
- Implemente autenticação e armazenamento remoto (usuários e tarefas).
- Adicione testes automatizados e integração contínua (CI).
- Utilize uma estratégia de deploy estável (ex.: GitHub Pages para frontend estático; backend separado).

---

## Contribuição

Contribuições são bem-vindas. Para melhorias no MVP, sugerimos dividir as tarefas em issues (ex.: “mover OpenWeatherMap para backend”, “adicionar notificações push”, “integração com Firebase Auth”).

---

## Licença

Este repositório pode incluir uma licença permissiva (por exemplo, MIT). Adicione `LICENSE` conforme sua preferência para uso público no GitHub.

---

### Contato

Projeto desenvolvido por **Vinícius Carnaúba** (Back-end, QA) e **Marcelo Tenório** (Front-end, UX/UI).


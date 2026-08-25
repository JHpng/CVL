# 🏭 CVL - Controle de Validade por Lote (Metodologia FEFO)

🔗 **[Acessar o Sistema Online](https://jhpng.github.io/CVL/)** *(Ferramenta Client-Side / Sem necessidade de servidor)*

## 🎯 O Problema de Negócio (A Dor)
Produtos vencidos na prateleira ou no armazém representam perda financeira direta e irrecuperável. A maioria dos estoques de varejo e centros de distribuição pequenos/médios controla validades usando planilhas manuais ou sistemas engessados que não funcionam bem no chão de fábrica. O resultado? Ruptura, capital perdido e dificuldade em aplicar a regra de saída correta.

## 🛠️ A Solução (O Pragmatismo)
Desenvolvi o **CVL**, uma aplicação de gestão de pátio focada exclusivamente em mitigar perdas por vencimento. A ferramenta opera com a metodologia **FEFO (First-Expire, First-Out)** e foi desenhada para rodar diretamente no navegador do computador ou tablet do estoquista.

**Principais Entregas:**
- **Integração com Leitor Óptico:** Campos preparados para receber bipagem de códigos de barras (EAN/GTIN) para entrada e saída rápida.
- **Motor FEFO Automático:** O algoritmo cruza as validades e destaca em tela qual lote deve ser despachado primeiro ("Sair 1º") ou qual deve ser descartado ("Retirar").
- **Dashboards de Risco:** Visão segmentada por criticidade (Vencido, ≤30 dias, ≤90 dias, Prazo OK).
- **Gestão Multi-Filial:** Controle cruzado entre matriz e filiais na mesma tela.

## 🧠 Arquitetura e Engenharia
Desenvolvi esta ferramenta com arquitetura *Offline-First* e *Serverless* para garantir velocidade máxima no chão de fábrica.

**A Filosofia de Desenvolvimento (AI-Assisted Engineering):**
Para acelerar a entrega deste produto, utilizei Inteligência Artificial Generativa como assistente de codificação ("pair programming"). O foco do meu trabalho não foi digitar linhas de código braçalmente, mas sim atuar como o **arquiteto da solução**:
1. **Definição da Lógica Logística:** Implementação matemática da regra FEFO e status de criticidade baseados em data atual vs. data de vencimento (Lead Time).
2. **Design de Arquitetura de Dados:** Decisão técnica de substituir o banco de dados tradicional pelo **IndexedDB** do navegador, permitindo alta capacidade de armazenamento local, latência zero e operação robusta.
3. **Orquestração:** Integração da leitura de XLSX para subir bases-mestras em segundos e exportação de backups em JSON.

*Acredito que o diferencial do profissional moderno é focar na regra de negócio que dá lucro, usando a tecnologia (incluindo IA) como alavanca de produtividade.*

- **Frontend:** HTML5, CSS3, JavaScript (Vanilla).
- **Banco de Dados:** `IndexedDB` (com fallback) para persistência assíncrona robusta.
- **Processamento:** `XLSX.js` para parseamento de planilhas de entrada sem sobrecarregar o cliente.

## 💼 Impacto Esperado
O CVL elimina a necessidade de varreduras manuais e demoradas no estoque físico. A equipe sabe exatamente *qual SKU*, *qual lote* e *em qual prateleira* está o risco financeiro do dia.

## 🚀 Roadmap (Futuras Atualizações)
Como arquiteto desta solução, o próximo passo estrutural mapeado para a evolução do produto é:
- **Evolução para PWA (Progressive Web App):** Transformar a aplicação para permitir instalação nativa nos dispositivos móveis dos conferentes. Isso garantirá operação 100% offline dentro de galpões logísticos (onde o sinal de Wi-Fi é comumente instável ou inexistente), sincronizando os dados em cache no `Service Worker` assim que a conexão for restabelecida.

---
*Projeto orquestrado por Jean Henrique

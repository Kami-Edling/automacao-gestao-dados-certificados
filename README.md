# automacao-gestao-dados-certificados
Automação de ges[README.md](https://github.com/user-attachments/files/34817122/README.md)
🚀 Automação de Gestão de Dados e Emissão de Certificados
Este repositório apresenta um projeto robusto de gestão, tratamento de dados e automação de processos desenvolvido para otimizar o fluxo de emissão de certificados educacionais (Extensão, Pós-Graduação e MBA).

O projeto unifica o controle de bases acadêmicas, integração com dashboards e automação de e-mails em escala usando Google Apps Script, garantindo eficiência operacional, segurança de dados e redução de gargalos na área.

🛠️ Tecnologias e Ferramentas Utilizadas
Google Sheets & Google Drive: Organização e centralização do "planilhão" de alunos, controle de status e histórico de backups.

Google Apps Script (JavaScript): Automação do fluxo de disparo de e-mails personalizados em lote.

Looker (Google Data Studio): Construção de dashboards interativos para acompanhamento de métricas, progresso e ofensores em tempo real.

📈 Principais Funcionalidades e Etapas do Projeto
1. Governança e Assertividade da Base de Dados
Mapeamento Completo: Auditoria de colunas, linhas, fórmulas e integrações da base principal de processos.

Rotina de Backups Semanais: Implementação de um protocolo de segurança onde as alterações e inclusões de novos alunos são testadas e validadas em uma base de cópia antes de irem para a oficial.

Controle de Ofensores: Mapeamento visual e analítico de pendências (documentação pendente, progresso insuficiente, pendências de TCC e status de aprovação).

2. Dashboards e Indicadores (Looker)
Extração e visualização de dados consolidada por visão temporal (mensal e trimestral).

Acompanhamento do volume total de Matrículas, Alunos em Andamento, Aptos e Formados.

Visão de desempenho por operador/responsável pela documentação e solicitação de certificados.

3. Automação de Disparo de Certificados (Google Apps Script)
Script desenvolvido para ler a planilha de envios, capturar os dados do aluno (nome, e-mail, tipo de curso e link do drive) e disparar e-mails personalizados de forma automatizada.

Saudações dinâmicas adaptadas conforme a modalidade do curso (Extensão, Pós-Graduação ou MBA).

function myFunctionenviarEmail() {
  var ss = SpreadsheetApp.getActiveSpreadsheet();
  var paginaEmails = ss.getSheetByName("Envio de Certificado");
  var intervalo = paginaEmails.getRange(2, 1, paginaEmails.getLastRow() - 1, 6);
  var valores = intervalo.getValues();

  for (var i = 0; i < valores.length; i++) {
    var linha = valores[i];
    var destinatario = linha[0];
    var nome = linha[1];
    var assunto = linha[2];
    var links = linha[3].split(",");
    var tipoCurso = linha[4];
    
    // Regras de saudação personalizada por tipo de curso...
  }
}

📊 Resultados e Impactos
Padronização: Unificação de planilhas dispersas em um fluxo centralizado e integrado.

Agilidade: Eliminação de processos manuais repetitivos na comunicação com os alunos através da automação via Apps Script.

Confiabilidade: Redução drástica de bugs e erros de dados com a implementação de validações prévias e backups semanais rigorosos.

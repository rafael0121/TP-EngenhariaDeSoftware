# Monitoramento de geração solar residencial e consumo elétrico

Dashboard Solar Residencial — Monitoramento de Geração vs Consumo

## Sobre o projeto
O projeto aborda o ODS 7 — Energia Acessível e Limpa com o objetivo de fornecer um dashboard simples de monitoramento de geração solar residencial versus consumo elétrico, permitindo ao morador visualizar produção, consumo e energia exportada, além de indicadores básicos que apoiem decisões para aumentar o autoconsumo e reduzir desperdício.

## Problema a ser resolvido
O problema a ser resolvido é a falta de uma visão consolidada e acessível das leituras de geração e consumo em residências com painéis solares; dados fragmentados em dispositivos ou planilhas impedem a identificação rápida de quedas de rendimento, desperdício e oportunidades de otimização, resultando em custos evitáveis e menor eficiência energética.

## Solução proposta
A solução proposta é uma aplicação híbrida composta por um backend em C++ (API REST leve, persistência em SQLite e motor de cálculo de KPIs) e um frontend web simples para o dashboard. Haverá também um utilitário para importar arquivos CSV com leituras ou gerar dados mock para testes; o backend expõe endpoints para ingestão e consulta de séries temporais e KPIs.

## Requisitos Funcionais

RF01 — Cadastro e Autenticação: permitir cadastro de usuário e login com autenticação básica (token ou HTTP Basic).

RF02 — Ingestão de Leituras: aceitar leituras via POST /ingest (JSON) e importação de arquivos CSV.

RF03 — Persistência de Leituras: armazenar leituras com timestamp, tipo (produção|consumo), valor_kwh e fonte no banco SQLite.

RF04 — Cálculo de KPIs: calcular produção total, consumo total, energia exportada, percentual de autoconsumo e rendimento por período.

RF05 — Séries Temporais: fornecer endpoints para séries temporais por métrica (production, consumption, etc.) com filtros por start e end.

RF06 — Dashboard: exibir gráficos comparativos (produção vs consumo), indicadores principais e tabela de leituras com filtros por período.

RF07 — Geração de Relatórios: exportar relatórios semanais/mensais em CSV ou TXT contendo KPIs e leituras agregadas.

RF08 — Configuração de Alertas: permitir configurar alertas simples (ex.: produção diária abaixo de X kWh) e listar alertas ativos.

RF09 — Logs e Auditoria: registrar operações de ingestão, importação e geração de relatórios com carimbo de tempo e usuário.

RF10 — Testes Automatizados: incluir testes unitários para os módulos críticos (ingestão e cálculo de KPIs) e scripts de validação de importação CSV.

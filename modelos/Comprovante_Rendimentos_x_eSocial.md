# Mapeamento do Informe de Rendimentos x Eventos S-5002 e S2501 do eSocial - GT-Piloto

## Log de Alteração

| Data | Log |
|:----:|:----|
| 13/11/2025 | Criação do Documento |

---

## Sobre esse documento

Este documento foi construído pela empresas de sofware participantes do GT-Piloto do eSocial. Ele apresenta o **mapeamento** dos eventos **S-5002 - Imposto de Renda Retido na Fonte por Trabalhador** e **S-2501 - Informações de Tributos Decorrentes de Processo Trabalhista** do e-Social (versão S-1.3) e a correspondência para o **Comprovante de Rendimentos Pagos e de Imposto sobre a Renda Retido na Fonte(Informe de Rendimentos)** (Instrução Normativa RFB nº 2.060, de 13 de dezembro de 2021 - <https://normasinternet2.receita.fazenda.gov.br/#/consulta/externa/122177>)

---

## A tabela abaixo representa os grupos de campos do Informe de Rendimentos e a regra geral de preenchimento conforme os eventos S-5002 e S-2501

|Grupo|S-5002|S-2501|
|:--------|:--------------------------|:--------------------------|
|1. FONTE PAGADORA PESSOA JURÍDICA OU PESSOA FÍSICA | Sempre preencher | Sempre preencher |
|2. PESSOA FÍSICA BENEFICIÁRIA DOS RENDIMENTOS | Sempre preencher |Sempre preencher |
|3. RENDIMENTOS TRIBUTÁVEIS, DEDUÇÕES E IMPOSTO SOBRE A RENDA RETIDO NA FONTE | SEM informações em \<dmDev/infoRRA\> | \<infoCRIRRF/tpCR\> <> [188951] |
|4. RENDIMENTOS ISENTOS E NÃO TRIBUTÁVEIS | SEM informações em \<dmDev/infoRRA\> | \<infoCRIRRF/tpCR\> <> [188951] |
|5. RENDIMENTOS SUJEITOS A TRIBUTAÇÃO EXCLUSIVA (RENDIMENTO LÍQUIDO) | SEM informações em \<dmDev/infoRRA\> |  \<infoCRIRRF/tpCR\> <> [188951] |
|6. RENDIMENTOS RECEBIDOS ACUMULADAMENTE | COM informações em \<dmDev/infoRRA\> |  \<infoCRIRRF/tpCR\> = [188951] |
|7. INFORMAÇÕES COMPLEMENTARES | Sempre preencher | Sempre preencher |

## O preenchimento (de acordo com os eventos S-5002 e S-2501 do eSocial) de cada campo dos grupos do Informe de Rendimentos será detalhado a seguir

---

## 1 - FONTE PAGADORA PESSOA JURÍDICA OU PESSOA FÍSICA

### 1.1 - CNPJ/CPF

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002 e S-2501** | \<ideEmpregador/nrInsc\> |

### 1.2 - Nome Empresarial/Nome Completo

***Este campo não está disponível nos XMLs dos eventos S-5001 e S-2501***

---

## 2 -  PESSOA FÍSICA BENEFICIÁRIA DOS RENDIMENTOS

### 2.1 - CPF

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<ideTrabalhador/cpfBenef\> |
| **S-2501** | \<ideTrab/cpfTrab\> |

### 2.2 - Nome Completo

***Este campo não está disponível nos XMLs dos eventos S-5001 e S-2501***

### 2.3 - Natureza do Rendimento

**Mapeamentos por Cenário do S-5002:**

| Valor da Natureza de Rendimento | Regra |
|:--------|:--------------------------|
| Rendimento do trabalho assalariado | - \<infoIR/tpInfoIR\> = [11] </br> - \<dmDev/codCateg\> <> [201, 202, 701, 711, 712, 731, 734, 738, 741, 751, 771, ou 781] </br> - SEM informações em \<dmDev/infoRRA\> </br> - SEM informações em \<dmDev/infoPgtoExt\> |
|Rendimento do trabalho assalariado|- \<infoIR/tpInfoIR\> = [11,12,14]</br> - SEM informações em \<dmDev/infoRRA\> </br> - SEM informações em \<dmDev/infoPgtoExt\> |
|Rendimento do trabalho sem vínculo empregatício| - \<infoIR/tpInfoIR\> = [11] </br> - \<dmDev/codCateg\> = [201, 202, 701, 711, 712, 731, 734, 738, 741, 751, 771, ou 781] </br> - SEM informações em \<dmDev/infoRRA\> </br> - SEM informações em \<dmDev/infoPgtoExt\>|
|Rendimentos relativos à prestação de serviços de transporte rodoviário internacional de carga, pagos a transportador autônomo PF residente no Paraguai|- \<infoIR/tpInfoIR\> = [11] </br> - \<dmDev/codCateg\> = [712] </br> - \<dmDev/infoPgtoExt/paisResidExt\> = [586 - Paraguai]|
|Aposentadoria, reserva, reforma ou pensão pagos por previdência pública|- Evento origem S-1207 </br> - \<infoIR/tpInfoIR\> = [11] ou \<infoIR/tpInfoIR\> = [14] </br>- SEM informações em \<dmDev/infoRRA\> </br> - SEM informações em \<dmDev/infoPgtoExt\>|
|Participação nos lucros ou resultados (PLR)|- Somente \<infoIR/tpInfoIR\> = [14]|
|Residente / Domiciliado no Exterior|- \<infoIR/tpInfoIR\> = [11] </br> - SEM informações em \<dmDev/infoRRA\> </br> - COM informações em \<dmDev/infoPgtoExt\>|
|Rendimentos Recebidos Acumuladamente|- \<infoIR/tpInfoIR\> = [11] ou \<infoIR/tpInfoIR\> = [12] ou \<infoIR/tpInfoIR\> = [14] </br> - SOMENTE demonstrativos (dmDev) com RRA informações em \<dmDev/infoRRA\> </br> - SEM informações em \<dmDev/infoPgtoExt\>|

**Mapeamentos por Cenário do S-2501:**

| Valor da Natureza de Rendimento | Regra |
|:--------|:--------------------------|
| Rendimentos Decorrentes da Justiça do Trabalho | \<infoCRIRRF/tpCR\> = [593656 - IRRF - Decisão da Justiça do Trabalho] |
| Rendimentos Decorrentes de acordo CCP/Ninter | \<infoCRIRRF/tpCR\> = [056152 - IRRF - CCP/NINTER] |
| Rendimento do trabalho assalariado  | \<infoCRIRRF/tpCR\> = [188951 - IRRF - RRA] |

---

## 3 - RENDIMENTOS TRIBUTÁVEIS, DEDUÇÕES E IMPOSTO SOBRE A RENDA RETIDO NA FONTE

***(Somente quando o grupo de RRA (dmDev/infoRRA) NÃO for preenchido no evento S-5002)***

### 3.1 - Total de Rendimentos (inclusive férias)

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<consolidApurMen/vlrRendTrib\> |
| **S-5002: Tag infoIR/tpInfoIR SEM info de residente no exterior (dmDev/infoPgtoExt)** | \<infoIR/tpInfoIR\> = [11,13] |
| **S-5002: Tag infoIR/tpInfoIR COM info de residente no exterior (dmDev/infoPgtoExt)** | \<infoIR/tpInfoIR\> = [11,12,14,72,73,74,75,76,77,79,700,701,702,704] |
| **S-2501** | \<infoIR/vrRendTrib\> se \<infoCRIRRF/tpCR\> <> [188951]|

### 3.2 - Contribuição Previdenciária Oficial

| Campo | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<consolidApurMen/vlrPrevOficial\> |
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [41,9041] |
| **S-2501** |  \<infoIR/vrPrevOficial\> se \<infoCRIRRF/tpCR\> <> [188951]|

### 3.3 - Contribuição a entidades de previdência complementar, pública ou privada, e a fundos de </br> aposentadoria programada individual (Fapi) (preencher também o quadro 7) |

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag infoIRComplem** | \<infoIRComplem/infoIRCR/previdCompl/vlrDedPC\> |
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [46,61,63,9046,9061,9063] |
| **S-2501** | N/A |

### 3.4 - Pensão alimentícia (preencher também o quadro 7) |

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag infoIRComplem** | \<infoIRComplem/infoIRCR/penAlim/vlrDedPenAlim\> (se \<infoIRComplem/infoIRCR/penAlim/tpRend\> = [11,13,14,18])|
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [51,9051] |
| **S-2501** | \<infoCRIRRF/penAlim/vlrPensao\> se \<infoCRIRRF/penAlim/tpRend\> = [11] |

### 3.5 - Imposto sobre a renda retido na fonte (IRRF) |

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag infoIRComplem** | totInfoIR/consolidApurMen/vlrCRMen |
| **S-5002: Tag infoIR/tpInfoIR** |  infoIR/tpInfoIR = [31,9082,9083] |
| **S-2501** | Somar os valores dos campos abaixo quando \<infoCRIRRF/tpCR\> <> [188951]: </br> - \<infoCRIRRF/vrCR\> </br> - \<infoProcRet/infoValores/vlrCmpAnoCal\> e </br> - \<infoProcRet/infoValores/vlrCmpAnoAnt\>|

---

## 4 - RENDIMENTOS ISENTOS E NÃO TRIBUTÁVEIS

***(Somente quando o grupo de RRA (dmDev/infoRRA) NÃO for preenchido no evento S-5002)***

### 4.1 - Parcela isenta dos proventos de aposentadoria, reserva remunerada, reforma e pensão (65 anos ou mais), exceto a parcela isenta do 13º (décimo terceiro) salário

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<totInfoIR/consolidApurMen/vlrParcIsenta65\>  |
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [70] |
| **S-2501** | \<infoCRIRRF/infoIR/vrRendIsen65\> se \<infoCRIRRF/tpCR\> <> [188951] |

### 4.2 - Parcela isenta do 13º (décimo terceiro) salário de aposentadoria, reserva remunerada, reforma e pensão (65 anos ou mais)

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<totInfoIR/consolidApurMen/vlrParcIsenta65Dec\> |
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [71] |
| **S-2501** | \<infoCRIRRF/infoIR/vrRendIsen65Dec\> se \<infoCRIRRF/tpCR\> <> [188951] |

### 4.3 - Diárias e ajudas de Custo

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<totInfoIR/consolidApurMen/vlrDiarias\> + \<totInfoIR/consolidApurMen/vlrAjudaCusto\>|
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [72,73] |
| **S-2501** | \<infoIR/rendIsen0561/vlrDiarias\> se \<infoCRIRRF/tpCR\> <> [188951] |

### 4.4 - Pensão e proventos de aposentadoria ou reforma por moléstia grave; proventos de aposentadoria ou reforma por acidente em serviço

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<totInfoIR/consolidApurMen/vlrRendMoleGrave\> + \<totInfoIR/consolidApurMen/vlrRendMoleGrave13\>|
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [76,77] |
| **S-2501** | \<infoCRIRRF/infoIR/vrRendMoleGrave\> + \<infoCRIRRF/infoIR/vrRendMoleGrave13\> se \<infoCRIRRF/tpCR\> <> [188951] |

### 4.5 - Lucros e dividendos, apurados a partir de 1996, pagos por pessoa jurídica (lucro real, presumido ou arbitrado)

**Fora do escopo do eSocial - ver EFD-Reinf.**

### 4.6 - Valores pagos ao titular ou sócio de microempresa ou empresa de pequeno porte, exceto pró-labore, aluguéis ou serviços prestados

**Fora do escopo do eSocial - ver EFD-Reinf.**

### 4.7 - Indenizações por rescisão de contrato de trabalho, inclusive a título de PDV, e por acidente de trabalho

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<totInfoIR/consolidApurMen/vlrIndResContrato\> |
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [74] |
| **S-2501** |  \<infoIR/rendIsen0561/vlrIndResContrato\> se \<infoCRIRRF/tpCR\> <> [188951] |

### 4.8 - Juros de mora recebidos, devidos pelo atraso no pagamento de remuneração por exercício de emprego, cargo ou função

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<totInfoIR/consolidApurMen/vlrJurosMora\> |
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [704] |
| **S-2501** | \<infoCRIRRF/infoIR/vrJurosMora\> + \<infoCRIRRF/infoIR/vrJurosMora13\> se \<infoCRIRRF/tpCR\> <> [188951]  |

### 4.9 - Outros (Especificar)

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tag consolidApurMen** | \<totInfoIR/consolidApurMen/vlrIsenOutros\> + </br> \<totInfoIR/consolidApurMen/vlrBolsaMedico\> + </br> \<totInfoIR/consolidApurMen/vlrBolsaMedico13\> + </br> \<totInfoIR/consolidApurMen/vlrAuxMoradia\> + </br> \<totInfoIR/consolidApurMen/vlrAbonoPec\> |
| **S-5002: Tag infoIR/tpInfoIR** | \<infoIR/tpInfoIR\> = [700,701,702,703,79,75] e Descrição do valor do campo \<infoIR/tpInfoIR\>, exemplo: 700 -> "Auxílio moradia"|
| **S-2501** | Apresentar os valores dos campos separadamente conforme abaixo, se \<infoCRIRRF/tpCR\> <> [188951]: </br> - "Outros rendimentos isentos ou não tributáveis:" \<infoCRIRRF/infoIR/vrRendIsenNTrib\> </br> - "Abono pecuniário:" \<infoIR/rendIsen0561/lrAbonoPec\> </br> - "Auxílio moradia:" \<infoIR/rendIsen0561/vlrAuxMoradia\> |

---

## 5 - RENDIMENTOS SUJEITOS A TRIBUTAÇÃO EXCLUSIVA (RENDIMENTO LÍQUIDO)

***(Somente quando o grupo de RRA (dmDev/infoRRA) NÃO for preenchido no evento S-5002)***

### 5.1 13º (décimo terceiro) salário

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tags consolidApurMen e infoIRComplem** | \<totInfoIR/consolidApurMen/vlrRendTrib13\> – </br></br> ( \<totInfoIR/consolidApurMen/vlrPrevOficial13\> – </br> \<totInfoIR/consolidApurMen/vlrCR13Men\> – </br> \<infoIRComplem/infoIRCR/penAlim/vlrDedPenAlim\> [se \<tpRend\> = 12] – </br> \<infoIRComplem/infoIRCR/dedDepen/vlrDedDep\> [se \<tpRend\> = 12] – </br> infoIRComplem/infoIRCR/previdCompl/vlrDedPC13 – </br> \<infoIRComplem/infoIRCR/previdCompl/vlrPatrocFunp13\> )|
| **S-5002: Tags infoIR/tpInfoIR e infoIRComplem** | \<infoIR/tpInfoIR\> = [12] – </br></br> ( \<infoIR/tpInfoIR\> = [42,47,62,64,52,32] – </br> infoIRComplem/infoIRCR/dedDepen/vlrDedDep [tpRend = 12] )|
| **S-2501** | Se \<infoCRIRRF/tpCR\> <> [188951]: </br>\<infoCRIRRF/infoIR/vrRendTrib13\> – </br></br> ( \<infoCRIRRF/infoIR/vrPrevOficial13\> – </br> \<infoCRIRRF/vrCR13\> – </br> \<infoCRIRRF/dedDepen/vlrDeducao\> se \<tpRend\> = [12] – </br> \<infoCRIRRF/penAlim/vlrPensao\> se \<tpRend\> = [12] )|

### 5.2 Imposto sobre a renda retido na fonte sobre 13º (décimo terceiro) salário

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tags consolidApurMen** | \<totInfoIR/consolidApurMen/vlrCR13Men\> |
| **S-5002: Tag infoIR/tpInfoIR** |  \<infoIR/tpInfoIR\> = [32] |
| **S-2501** | \<infoCRIRRF/vrCR13\> se \<infoCRIRRF/tpCR\> <> [188951] |

### 5.3 Outros

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002: Tags consolidApurMen** | NA |
| **S-5002: Tag infoIR/tpInfoIR (S-5002)** |  \<infoIR/tpInfoIR\> = [14,34,54] |
| **S-2501** | N/A |

---

## 6 - RENDIMENTOS RECEBIDOS ACUMULADAMENTE - Art. 12-A da Lei nº 7.713, de 1988 (sujeitos a tributação exclusiva)

***(Somente quando o grupo de RRA \<dmDev/infoRRA\> FOR PREENCHIDO no evento S-5002)***

### 6.1 Número do processo: (especificar)

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<dmDev/infoRRA/nrProcRRA\> |
| **S-2501** | \<evtContProc/ideProc/nrProcTrab\> |

### 6.2 Quantidade de meses

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<dmDev/infoRRA/qtdMesesRRA\> |
| **S-2501** | \<infoCRIRRF/infoRRA/qtdMesesRRA\> |

### 6.1.1 - Total dos rendimentos tributáveis (inclusive férias e décimo terceiro salário)

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [11,12,14] |
| **S-2501** | \<infoIR/vrRendTrib\> + \<infoIR/vrRendTrib13\> se \<infoCRIRRF/tpCR\> = [188951] |

### 6.1.2 - Exclusão: Despesas com ação judicial

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [62,63] |
| **S-2501** | \<infoRRA/despProcJud/vlrDespCustas\> + \<infoRRA/despProcJud/vlrDespAdvogados\> |

### 6.1.3 - Dedução: Contribuição previdenciária oficial

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [41,42] |
| **S-2501** | (\<infoIR/vrPrevOficial\> + \<infoIR/vrPrevOficial13\>) se \<infoCRIRRF/tpCR\> = [188951] |

### 6.1.4 - Dedução: Pensão alimentícia (preencher também o quadro 7)

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [51,52,54] |
| **S-2501** | \<infoCRIRRF/penAlim/vlrPensao\> se \<infoCRIRRF/penAlim/tpRend\> = [18] |

### 6.1.5 - Imposto sobre a renda retido na fonte (IRRF)

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [31,32] |
| **S-2501** | (\<infoCRIRRF/vrCR\> + \<infoCRIRRF/vrCR13\>) se \<infoCRIRRF/tpCR\> = [188951]|

### 6.1.6 - Rendimentos isentos de pensão, proventos de aposentadoria ou reforma por moléstia grave ou aposentadoria ou reforma por acidente em serviço

**Mapeamentos por Cenário:**

| Cenário | Mapeamento S-5002/S-2501 |
|:--------|:--------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [76,77] |
| **S-2501** | \<infoCRIRRF/infoIR/vrRendMoleGrave\> + \<infoCRIRRF/infoIR/vrRendMoleGrave13\> se \<infoCRIRRF/tpCR\> = [188951]| 

---

## 7 - INFORMAÇÕES COMPLEMENTARES

### Assistência Médica/Plano de Saúde Coletivo

| Cenário  | Mapeamento S-5002/S-2501 |
|:------|:----------------------------------|
| **S-5002** | Grupo \<infoIRComplem/planSaude\> |
| **S-2501** | N/A |

### Pensão alimentícia

| Cenário  | Mapeamento S-5002/S-2501 |
|:------|:----------------------------------|
| **S-5002** | Grupo \<infoIRCR/penAlim\> |
| **S-2501** | Grupo \<infoCRIRRF/penAlim\> |

### Previdência Complementar

| Cenário  | Mapeamento S-5002/S-2501 |
|:------|:----------------------------------|
| **S-5002** | Grupo \<infoIRCR/previdCompl\> |
| **S-2501** | NA |

### Informações de Rendimentos com Exigibilidade Suspensa - Mensal

| Cenário  | Mapeamento S-5002/S-2501 |
|:------|:----------------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [9011,9031,9831,9041,9051,9061,9063] |
| **S-2501** | NA |

### Informações de Rendimentos com Exigibilidade Suspensa - 13o

| Cenário  | Mapeamento S-5002/S-2501 |
|:------|:----------------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [9012,9032,9832,9042,9047,9052,9062,9064] |
| **S-2501** | NA |

### ### Informações de Rendimentos com Exigibilidade Suspensa - PLR

| Cenário  | Mapeamento S-5002/S-2501 |
|:------|:----------------------------------|
| **S-5002** | \<infoIR/tpInfoIR\> = [9014,9034,9834,9054,9067] |
| **S-2501** | NA |

---

## Informações Adicionais

### 1. Grupo \<infoIR\> do S-5002

Ao somar os valores do campo \<infoIR/valor\> conforme os valores de \<infoIR/tpInfoIR\> pode resultar em valores negativos. Entretanto, a DIRF não trata valores negativos e esse comportamento foi mantido para o eSocial na tag \<consolidApurMen\>.

Abaixo um exemplo desse cenário: 
``` xml
<eSocial>
	<retornoProcessamentoLoteEventos>
		<!-- Additional processing information -->
		<tot tipo="S5002">
			<eSocial xmlns="http://www.esocial.gov.br/schema/evt/evtIrrfBenef/v_S_01_03_00">
				<evtIrrfBenef Id="">
					<!-- ... -->
					<ideTrabalhador>
						<cpfBenef>99999999999</cpfBenef>
						<dmDev>
							<perRef>2025-11</perRef>
							<ideDmDev>0654960800036</ideDmDev>
							<tpPgto>2</tpPgto>
							<dtPgto>2025-11-12</dtPgto>
							<codCateg>101</codCateg>
							<!-- ... -->
							<infoIR>
								<tpInfoIR>11</tpInfoIR>
								<valor>-4226.57</valor>
							</infoIR>
							<!-- ... -->
							<totApurMen>
								<CRMen>056107</CRMen>
								<vlrRendTrib>-4226.57</vlrRendTrib>
								<!-- ... -->
							</totApurMen>
						</dmDev>
						<totInfoIR>
							<consolidApurMen>
								<CRMen>056107</CRMen>
								<vlrRendTrib>0</vlrRendTrib>
								<!-- ... -->
							</consolidApurMen>
						</totInfoIR>
						<!-- ... -->
					</ideTrabalhador>
				</evtIrrfBenef>
			</eSocial>
		</tot>
	</retornoProcessamentoLoteEventos>
</eSocial>
```

---

### 2. Códigos tpInfoIR/infoIR do S-5002

#### Códigos Principais - Rendimentos Tributáveis

| Código | Descrição |
|:------:|:----------|
| **11** | Remuneração mensal |
| **12** | 13º salário |
| **14** | PLR |

#### Códigos Principais - Retenções IRRF

| Código | Descrição |
|:------:|:----------|
| **31** | Remuneração mensal |
| **32** | 13º salário |
| **34** | PLR |

#### Códigos Principais - Deduções da Base IRRF

| Código | Descrição |
|:------:|:----------|
| **41** | Previdência Social Oficial - Remuneração mensal |
| **42** | PSO - 13º salário |
| **46** | Previdência complementar - Salário mensal |
| **47** | Previdência complementar - 13º salário |
| **51** | Pensão alimentícia - Remuneração mensal |
| **52** | Pensão alimentícia - 13º salário |
| **54** | Pensão alimentícia - PLR |
| **61** | FAPI - Remuneração mensal |
| **62** | FAPI - 13º salário |
| **63** | Funpresp - Remuneração mensal |
| **64** | Funpresp - 13º salário |
| **67** | Plano privado coletivo assistência à saúde |
| **68** | Desconto simplificado mensal |

#### Códigos Principais - Rendimentos Isentos

| Código | Descrição |
|:------:|:----------|
| **70** | Parcela isenta 65 anos - Remuneração mensal |
| **71** | Parcela isenta 65 anos - 13º salário |
| **72** | Diárias |
| **73** | Ajuda de custo |
| **74** | Indenização rescisão contrato, PDV e acidentes |
| **75** | Abono pecuniário |
| **76** | Moléstia grave/acidente - Remuneração mensal |
| **77** | Moléstia grave/acidente - 13º salário |
| **79** | Outras isenções |
| **700** | Auxílio moradia |
| **701** | Transporte não tributável |
| **702** | Bolsa médico residente - remuneração mensal |
| **703** | Bolsa médico residente - 13º salário |
| **704** | Juros de mora |
| **7900** | Verbas diversas transitadas pela folha |

#### Códigos de Compatibilidade - Versões Anteriores

| Código | Descrição |
|:------:|:----------|
| **7950** | Rendimento não tributável |
| **7951** | Rendimento não tributável - acordos bitributação |
| **7952** | Rendimento tributável - RRA |
| **7953** | Retenção de IR - RRA |
| **7954** | Previdência Social Oficial - RRA |
| **7955** | Pensão alimentícia - RRA |
| **7956** | Valores ME/EPP (exceto pró-labore e aluguéis) |
| **7957** | Depósito judicial |
| **7958** | Compensação judicial do ano-calendário |
| **7959** | Compensação judicial de anos anteriores |
| **7960** | Exigibilidade suspensa - Remuneração mensal |
| **7961** | Exigibilidade suspensa - 13º salário |
| **7962** | Exigibilidade suspensa - Férias |
| **7963** | Exigibilidade suspensa - PLR |
| **7964** | Exigibilidade suspensa - RRA |

#### Códigos Exigibilidade Suspensa - Rendimento Tributável

| Código | Descrição |
|:------:|:----------|
| **9011** | Remuneração mensal |
| **9012** | 13º salário |
| **9014** | PLR |

#### Códigos Exigibilidade Suspensa - Retenção IRRF

| Código | Descrição |
|:------:|:----------|
| **9031** | Remuneração mensal |
| **9032** | 13º salário |
| **9034** | PLR |
| **9831** | Depósito judicial - Mensal |
| **9832** | Depósito judicial - 13º salário |
| **9834** | Depósito judicial - PLR |

#### Códigos Exigibilidade Suspensa - Deduções

| Código | Descrição |
|:------:|:----------|
| **9041** | PSO - Remuneração mensal |
| **9042** | PSO - 13º salário |
| **9046** | Previdência complementar - Salário mensal |
| **9047** | Previdência complementar - 13º salário |
| **9051** | Pensão alimentícia - Remuneração mensal |
| **9052** | Pensão alimentícia - 13º salário |
| **9054** | Pensão alimentícia - PLR |
| **9061** | FAPI - Remuneração mensal |
| **9062** | FAPI - 13º salário |
| **9063** | Funpresp - Remuneração mensal |
| **9064** | Funpresp - 13º salário |
| **9067** | Plano privado coletivo assistência à saúde |

#### Códigos Compensação Judicial

| Código | Descrição |
|:------:|:----------|
| **9082** | Compensação judicial do ano-calendário |
| **9083** | Compensação judicial de anos anteriores |

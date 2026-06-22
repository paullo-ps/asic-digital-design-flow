# 🧠 Microeletrônica & Digital ASIC Design Flow

Este repositório centraliza meus artefatos de descrição de hardware (RTL), verificação funcional, síntese lógica e implementação física de Circuitos Integrados de Aplicação Específica (**ASIC**), operando sob o fluxo digital de Standard Cells.

---

## 🗂️ Catálogo de Projetos em Silício

### 1. [ASIC Core Correlator — Filtro de Ruído para Sensor TSOP](./asic_core_tsop) 🏆
*Projeto de conclusão do programa global **UNIC-CASS** (Universalization of IC Design), promovido pela **IEEE Circuits and Systems Society**.*

* **O Silício:** Um acelerador de hardware dedicado a calcular a correlação em tempo real entre pulsos emitidos e recebidos por barreiras infravermelhas, eliminando falsos positivos por software.
* **Metodologia:** Fluxo Open-Source RTL-to-GDSII puro (SkyWater 130nm).
* **Stack:** `Verilog` • `Yosys` • `GTKWave` • `OpenROAD Flow`
* **Métricas de Sign-off:** `Setup WNS: +0.14 ns` | `DRC: 0 Violations` | `LVS: Matched`

> **[ 📂 ACESSAR PASTA DO PROJETO E CÓDIGOS RTL ──► ](./asic_core_tsop)**

---

### 2. [Laboratórios de Síntese Lógica & STA — Synopsys EDA](./synopsys_rtl_labs) 🚧
*Módulo de experimentação com o fluxo comercial padrão da indústria.*

* **Status:** *Abertura programada para Julho/2026 (Início da Residência em Microeletrônica).*
* **Objetivo:** Indexação de netlists otimizadas, relatórios de PPA (*Power, Performance, Area*) e Análise Estática de Temporização (STA) gerados no Design Compiler / IC Compiler.

---

## ⚙️ O Fluxo de Implementação Digital (Standard-Cell Flow)

Por se tratar de arquitetura digital pura, a esteira dispensa capturas esquemáticas analógicas (como *Xschem*), seguindo o pipeline automatizado de *Digital Sign-off*:

```text
                RTL DESIGN
         (Verilog / SystemVerilog)
                    │
                    ▼
          Functional Simulation
             (GTKWave / TBs)
                    │
                    ▼
             Logic Synthesis
                 (Yosys)
                    │
                    ▼
          Physical Implementation
                (OpenROAD)
                    │
     ┌──────────────┼──────────────┐
     │              │              │
     ▼              ▼              ▼
 Floorplan      Placement         CTS
                    │
                    ▼
                 Routing
                    │
                    ▼
             DRC / LVS Checks
                    │
                    ▼
             Final GDSII Layout

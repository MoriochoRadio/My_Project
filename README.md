# 🚀 My IoT × GitHub Project

🇰🇷 한국어 · 🇬🇧 [English](README.en.md)

**GitHub와 IoT 장비(Zybo Z7, Zynq-7000)를 연동하여 LED 제어와 스위치/PMOD 입력을 테스트하는 실습 프로젝트입니다.**  
이번 활동을 통해 GitHub의 기초, 버전 관리 방식, 협업 흐름, 그리고 오픈소스의 철학까지 함께 학습했습니다.

![GitHub](https://img.shields.io/badge/GitHub-000000?style=flat&logo=GitHub&logoColor=white)
![IoT](https://img.shields.io/badge/IoT-1E90FF?style=flat&logo=arduino&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)

---

## 🌱 프로젝트 소개
이 저장소는 **GitHub 교육 실습**을 위해 제작된 프로젝트로, Zynq 보드 기반 IoT 장비를 연결하여  
**LED ON/OFF, 버튼 신호 읽기** 등을 테스트하는 코드와 학습 내용을 포함하고 있습니다.

- GitHub 기초 사용법  
- Git/GitHub 기반 프로젝트 관리  
- Markdown 문서 작성  
- IoT 장비 제어 실습 (LED, 버튼)  
- 버전관리 도구 활용 경험 (SourceTree, Git CLI)

---

## 📌 주요 학습 내용 정리

### 1. 🧭 Git & GitHub Basics
- Git의 동작 원리 (스테이징, 커밋, 브랜치 흐름 이해)
- GitHub 저장소 생성 및 Push/Clone
- CLI와 GUI(SourceTree)를 통한 Git 명령어 실습
- GitHub Issues, Commits, Branching 간단 체험
- Markdown을 활용한 문서화 능력 향상

### 2. 🔧 IoT Device Programming
Zynq-7000 SoC 기반의 Processing System을 사용해:

- LED 제어  
- 버튼 입력 인식    

컴퓨터와 IoT 장비 간 **하드웨어-소프트웨어 연동 구조**를 이해했습니다.

### 3. 🌐 오픈소스 철학 이해
- 개방, 공유, 개선 이라는 오픈소스 정신 이해  
- GitHub을 기반으로 한 오픈 개발 문화 체험  
- 협업 가능한 개발 환경 구축 경험

---

## 📂 저장소 구조

| 폴더 | 내용 |
|------|------|
| `0_Docs/` | Zynq-7000 / Zybo Z7 공식 문서 (TRM, 회로도, 핀아웃 등) |
| `1_programmable_logic_project/` | Vivado 2024.2 하드웨어 프로젝트 (`.xpr`) — LED 제어, PMOD LED 제어 |
| `2_exported_programmable_logic/` | Vivado에서 내보낸 하드웨어 사양(`.xsa`) + Vitis용 `main.c` |
| `3_sample_source_code/` | 실습용 샘플 C 소스 (`main.c`) |
| `4_vitis_exported_archive/` | Vitis 프로젝트 아카이브 (`.zip`) |
| `MyWork/` | 직접 실습한 Vitis 워크스페이스 (LED 제어, PMOD 제어) |

---

## 🧪 IoT 실습 기능

| 기능 | 설명 |
|------|------|
| 🔴 LED 제어 | AXI GPIO를 통해 LED ON/OFF (`XGpio_DiscreteWrite`) |
| 🔘 스위치 입력 | 스위치 상태(0/1)를 읽어 LED에 반영 (`XGpio_DiscreteRead`) |
| 🔌 PMOD 제어 | 듀얼 채널 AXI GPIO로 PMOD 입력을 LED에 미러링 |
| 🛠️ 시리얼 모니터링 | `xil_printf` 출력을 TeraTerm으로 확인 |

---

## 🛠 사용 도구

| 도구 | 설명 |
|------|------|
| **VS Code** | IoT 코드 작성 및 편집 |
| **Git for Windows** | Git 명령어 실습 |
| **SourceTree** | Git GUI | 
| **TeraTerm** | IoT 장치 연결 및 로그 확인 |
| **Notion** | 실습 내용 정리 |
| **Slack** | 실습 커뮤니케이션 |

---

## 🧭 실습 진행 과정

### **Session 1 : 환경 구성**
- Git, VSCode, SourceTree 설치  
- Slack, Notion 세팅   

### **Session 2 : Git/GitHub 사용**
- GitHub 계정 준비 및 저장소 생성  
- Markdown 작성 연습  
- Git CLI / SourceTree로 push & pull 실습  

### **Session 3 : IoT 실습**
- Zynq PS 기반 LED 제어  
- 스위치/PMOD 입력 확인    

---

## ❓ 왜 이렇게 구성했나 (미니 Q&A)

**Q. 왜 Zynq(Zybo Z7) 보드인가?**
Zynq-7000은 ARM Cortex-A9 프로세서(PS)와 FPGA(PL)가 한 칩에 있는 SoC입니다. Vivado에서 AXI GPIO로 LED/스위치를 PL에 연결하고, PS에서 C 코드(`XGpio_*` API)로 제어하면서 하드웨어-소프트웨어 연동 구조를 실습할 수 있습니다.

**Q. 폴더를 왜 단계별로 나눴나?**
Vivado 하드웨어 설계(`.xpr`) → 하드웨어 사양 내보내기(`.xsa`) → Vitis에서 C 애플리케이션 작성이라는 Zynq 개발 흐름을 그대로 폴더 순서(1→2→3→4)로 옮겼습니다. `MyWork/`는 이 흐름을 따라 직접 실습한 결과물입니다.

**Q. 첫 예제가 왜 "스위치 → LED 미러링"인가?**
GPIO 입력(스위치 읽기)과 출력(LED 쓰기), 시리얼 출력(`xil_printf`)을 한 번에 검증할 수 있는 가장 단순한 구성이기 때문입니다. PMOD 예제는 여기서 한 단계 나아가 듀얼 채널 AXI GPIO(채널1 입력, 채널2 출력)를 사용합니다.

---

## 🎉 실습 결과  
- GitHub와 IoT 장비 연동 성공  
- GitHub Repository 운영 경험  
- Markdown 문서화 능력 향상  
- 오픈소스 기반 개발 방식 체험  

---


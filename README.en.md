# 🚀 My IoT × GitHub Project

🇰🇷 [한국어](README.md) · 🇬🇧 English

**A hands-on project connecting GitHub with an IoT device (Zybo Z7, Zynq-7000) to test LED control and switch/PMOD input.**
Through this activity, I also studied GitHub fundamentals, version control practices, collaboration workflows, and the philosophy of open source.

![GitHub](https://img.shields.io/badge/GitHub-000000?style=flat&logo=GitHub&logoColor=white)
![IoT](https://img.shields.io/badge/IoT-1E90FF?style=flat&logo=arduino&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)

---

## 🌱 About the Project
This repository was created for a **GitHub training course**. It connects a Zynq-based IoT device and contains
the code and study notes for testing **LED ON/OFF, reading button signals**, and more.

- GitHub basics
- Git/GitHub-based project management
- Writing Markdown documentation
- Hands-on IoT device control (LED, buttons)
- Experience with version control tools (SourceTree, Git CLI)

---

## 📌 Key Things I Learned

### 1. 🧭 Git & GitHub Basics
- How Git works (understanding staging, commits, and branch flow)
- Creating a GitHub repository and Push/Clone
- Practicing Git commands via CLI and GUI (SourceTree)
- A quick tour of GitHub Issues, Commits, and Branching
- Improving documentation skills with Markdown

### 2. 🔧 IoT Device Programming
Using the Processing System on the Zynq-7000 SoC:

- LED control
- Button input detection

I came to understand the **hardware-software integration structure** between a computer and an IoT device.

### 3. 🌐 Understanding the Open Source Philosophy
- Understanding the open source spirit of openness, sharing, and improvement
- Experiencing GitHub-based open development culture
- Experience setting up a collaboration-ready development environment

---

## 📂 Repository Structure

| Folder | Contents |
|------|------|
| `0_Docs/` | Official Zynq-7000 / Zybo Z7 documentation (TRM, schematics, pinouts, etc.) |
| `1_programmable_logic_project/` | Vivado 2024.2 hardware project (`.xpr`) — LED control, PMOD LED control |
| `2_exported_programmable_logic/` | Hardware specification exported from Vivado (`.xsa`) + `main.c` for Vitis |
| `3_sample_source_code/` | Sample C source for practice (`main.c`) |
| `4_vitis_exported_archive/` | Vitis project archive (`.zip`) |
| `MyWork/` | My own hands-on Vitis workspace (LED control, PMOD control) |

---

## 🧪 IoT Features Practiced

| Feature | Description |
|------|------|
| 🔴 LED control | LED ON/OFF via AXI GPIO (`XGpio_DiscreteWrite`) |
| 🔘 Switch input | Read switch state (0/1) and reflect it on the LEDs (`XGpio_DiscreteRead`) |
| 🔌 PMOD control | Mirror PMOD input to LEDs via dual-channel AXI GPIO |
| 🛠️ Serial monitoring | Check `xil_printf` output in TeraTerm |

---

## 🛠 Tools Used

| Tool | Description |
|------|------|
| **VS Code** | Writing and editing IoT code |
| **Git for Windows** | Practicing Git commands |
| **SourceTree** | Git GUI |
| **TeraTerm** | Connecting to the IoT device and checking logs |
| **Notion** | Organizing practice notes |
| **Slack** | Communication during the course |

---

## 🧭 Course Progress

### **Session 1: Environment Setup**
- Installed Git, VSCode, SourceTree
- Set up Slack and Notion

### **Session 2: Using Git/GitHub**
- Prepared a GitHub account and created a repository
- Practiced writing Markdown
- Practiced push & pull with Git CLI / SourceTree

### **Session 3: IoT Practice**
- Zynq PS-based LED control
- Verified switch/PMOD input

---

## ❓ Why It's Organized This Way (Mini Q&A)

**Q. Why the Zynq (Zybo Z7) board?**
The Zynq-7000 is an SoC that combines an ARM Cortex-A9 processor (PS) and an FPGA (PL) on a single chip. By wiring LEDs/switches to the PL with AXI GPIO in Vivado and controlling them from the PS with C code (the `XGpio_*` API), you get hands-on experience with the hardware-software integration structure.

**Q. Why are the folders split by stage?**
The folder order (1→2→3→4) mirrors the Zynq development flow as-is: Vivado hardware design (`.xpr`) → exporting the hardware specification (`.xsa`) → writing the C application in Vitis. `MyWork/` holds the results of following this flow myself.

**Q. Why is the first example "switch → LED mirroring"?**
Because it's the simplest setup that verifies GPIO input (reading switches), output (writing LEDs), and serial output (`xil_printf`) all at once. The PMOD example goes one step further, using dual-channel AXI GPIO (channel 1 input, channel 2 output).

---

## 🎉 Results
- Successfully connected GitHub with an IoT device
- Experience operating a GitHub repository
- Improved Markdown documentation skills
- Experienced open-source-based development practices

---

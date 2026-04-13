# AI Cosmetic Surgery Simulation Platform
> **얼굴 부위별 특징 분리를 이용한 차세대 성형 시뮬레이션 및 분석 플랫폼**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-2.1-EE4C2C?logo=pytorch&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)

---

## 🎯 Project Overview
기존의 뷰티 필터가 얼굴 전체를 일괄 변형하는 한계를 넘어, **BiSeNet 기반의 정교한 얼굴 파싱**과 **SF-GAN 파이프라인**을 통해 눈, 코, 입 등 특정 부위만을 독립적으로 조작합니다. 사용자는 자신의 아이덴티티를 유지하면서도 원하는 부위의 변화를 실시간으로 시뮬레이션할 수 있습니다.

### ✨ Key Features
* **Precision Parsing**: BiSeNet V2를 이용한 9개 클래스 실시간 마스크 추출
* **Independent Editing**: SEAN 기반의 Latent 조작으로 특정 부위만 선택적 수정
* **Identity Preservation**: ArcFace 유사도 0.8 이상의 높은 본인 인증 유지율
* **Security First**: 모든 사용자 데이터는 AES-256 암호화 처리 및 분석 후 즉시 파기

---

## 🛠 Tech Stack
### AI & Model Training
* **Architectures**: BiSeNet V2, StyleGAN2, SF-GAN
* **Frameworks**: PyTorch, CUDA 11.8
* **Datasets**: FFHQ (CelebAMask-HQ)

### Engineering
* **Backend**: Flask (REST API, JWT Auth)
* **Frontend**: React, TypeScript, Vite
* **Database/Storage**: AES-256 Encrypted Storage

---

## 🧬 System Architecture
```mermaid
graph LR
    A[User Image] --> B(BiSeNet Parsing)
    B --> C{Region Mask}
    C --> D[Region Inversion]
    D --> E[Latent Manipulation]
    E --> F[StyleGAN2 Decoder]
    F --> G[Simulated Result]

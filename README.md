# 🧠 CIFAR-10 이미지 분류

> 다양한 CNN 모델 비교 및 실험 기반 성능 최적화 프로젝트
<br /><br /><br />
## 📑 목차

* [🔗 프로젝트 개요](#-프로젝트-개요)
* [📅 프로젝트 기간](#-프로젝트-기간)
* [✨ 주요 내용](#-주요-내용)
* [🛠 기술 스택](#-기술-스택)
* [📊 실험 결과](#-실험-결과)
* [🧪 실험 과정](#-실험-과정)
* [💡 핵심 인사이트](#-핵심-인사이트)
* [📂 프로젝트 구조](#-프로젝트-구조)
<br /><br /><br />
## 🔗 프로젝트 개요

CIFAR-10 데이터셋을 기반으로 다양한 CNN 모델을 비교하고,
학습 조건 및 데이터 처리 방식에 따른 성능 변화를 실험적으로 분석한 프로젝트입니다.

단순 구현이 아닌, **성능에 영향을 주는 요소를 직접 조정하고 비교하는 과정**에 집중했습니다.
<br /><br /><br />
## 📅 프로젝트 기간

* 2023.03 ~ 2023.06
* 모델 실험 및 성능 개선 중심으로 반복적인 실험 수행
<br /><br /><br />
## ✨ 주요 내용

* VGG, ResNet, DenseNet 모델 비교
* 하이퍼파라미터 (batch size, learning rate, epoch) 최적화
* 데이터 전처리 및 augmentation 실험
* optimizer 및 scheduler 비교
* 학습/평가 모드(eval) 적용에 따른 성능 차이 분석
<br /><br /><br />
## 🛠 기술 스택

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=PyTorch&logoColor=white" />
  <img src="https://img.shields.io/badge/Torchvision-5C3EE8?style=for-the-badge" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=NumPy&logoColor=white" />
  <img src="https://img.shields.io/badge/Matplotlib-ffffff?style=for-the-badge&logo=plotly&logoColor=black" />
  <img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=black" />
</p>
<br /><br /><br />
## 📊 실험 결과

| 모델              | 정확도      |
| --------------- | -------- |
| VGG11           | 약 79~80% |
| VGG19           | 약 87%    |
| ResNet18/34     | 약 86~87% |
| DenseNet121     | 약 88%    |
| **VGG19 (최적화)** | **92%**  |
<br /><br /><br />
## 🧪 실험 과정

### 1. 모델 비교

* 다양한 CNN 구조(VGG, ResNet, DenseNet)를 비교
* 깊은 구조일수록 성능이 좋은 경향 확인

### 2. 하이퍼파라미터 조정

* learning rate: 0.001이 가장 안정적
* batch size: 64~128 범위에서 최적 성능

### 3. 데이터 처리

* normalization: (0.5, 0.5, 0.5) 유지
* augmentation:

  * 잘못 적용 시 성능 저하
  * 적절한 강도로 조정 시 성능 향상

### 4. 핵심 발견

* `model.eval()` 적용 여부가 성능에 큰 영향
* eval 적용 + epoch 증가 → 최종 성능 향상

### 5. 최적 설정

* 모델: VGG19
* optimizer: Adam
* scheduler 적용
* epoch 증가 + augmentation 조정
<br /><br /><br />
## 💡 핵심 인사이트

* 동일한 모델이라도 학습 설정에 따라 성능 차이가 크게 발생
* 단순 구현보다 실험 설계 및 결과 분석 능력이 중요
* 작은 구현 차이(eval, augmentation 등)가 성능에 큰 영향을 미침
<br /><br /><br />
## 📂 프로젝트 구조

```bash
.
├── cifar10_classification.ipynb
├── requirements.txt
└── README.md
```

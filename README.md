# AInation
# 다이캐스팅 부품 분류 및 품질 검사 프로젝트

딥러닝을 활용한 다이캐스팅 부품의 자동 분류 및 품질 검사 시스템

## 프로젝트 개요

본 프로젝트는 딥러닝 기술을 활용하여 다이캐스팅 부품을 자동으로 분류하고 품질을 검사하는 시스템을 개발합니다. 4가지 부품 유형(CN7, G2, BLDC-400-Front, BLDC-400-Back)의 분류와 양품/불량품 판정을 수행합니다.

## 주요 기능

- **부품 분류**: 4개 클래스 다중 분류 (CN7, G2, BLDC-400-F, BLDC-400-B)
- **품질 검사**: 양품(OK)/불량품(NG) 이진 분류
- **다중 모델 비교**: EfficientNet, MobileNet 계열 모델 성능 비교
- **데이터 증강**: 회전 변환 기반 데이터 증강으로 학습 데이터 확장

## 프로젝트 구조

```
├── efficient_net_comparison.ipynb    # EfficientNet 모델 비교 분석
├── augmentation_original.ipynb       # 데이터 증강 및 전처리
├── NG_split_final.ipynb             # 불량품 데이터 분할
├── 양불판정.ipynb                    # 품질 검사 모델 학습
└── mobilenet_organized.ipynb        # MobileNet 계열 모델 실험
```

## 사용 기술

### 딥러닝 프레임워크
- **PyTorch**: EfficientNet 모델 구현
- **TensorFlow/Keras**: MobileNet 모델 구현

### 모델 아키텍처
- **EfficientNet**: B4, B5, V2-S 버전 비교
- **MobileNet**: V1, V2, V3-Small, V3-Large 버전 비교

### 데이터 처리
- **OpenCV**: 이미지 전처리
- **Albumentations**: 데이터 증강
- **scikit-learn**: 성능 평가 및 데이터 분할

## 데이터셋

### 부품 클래스
- **CN7**: 특정 다이캐스팅 부품
- **G2**: 특정 다이캐스팅 부품  
- **BLDC-400-Front**: BLDC 모터 전면 부품
- **BLDC-400-Back**: BLDC 모터 후면 부품

### 데이터 분할
- **Train**: 70% (증강 데이터 포함)
- **Validation**: 10%
- **Test**: 20%

### 데이터 증강 기법
- 원본 이미지 보존
- ±30°/±45° 랜덤 회전
- 90°, 180°, 270° 고정 각도 회전

## 실행 방법

### 1. 환경 설정
```bash
pip install torch torchvision
pip install tensorflow
pip install opencv-python
pip install albumentations
pip install scikit-learn
pip install matplotlib seaborn
```

### 2. 데이터 증강
```python
# augmentation_original.ipynb 실행
# 원본 데이터를 증강하여 학습용 데이터셋 생성
```

### 3. 모델 학습 및 평가
```python
# EfficientNet 모델 비교
# efficient_net_comparison.ipynb 실행

# MobileNet 모델 실험
# mobilenet_organized.ipynb 실행

# 품질 검사 모델
# 양불판정.ipynb 실행
```

## 성능 결과

### EfficientNet 결과
- **EfficientNet-B4**: 92.5% 정확도
- **EfficientNet-B5**: 100% 정확도 (검증)
- **EfficientNet-V2-S**: 100% 정확도 (검증)

### 평가 지표
- **정확도 (Accuracy)**
- **정밀도 (Precision)**
- **재현율 (Recall)**
- **F1-Score**
- **혼동행렬 (Confusion Matrix)**
- **ROC Curve**
- **mAP (Mean Average Precision)**

## 주요 특징

### 1. 종합적인 모델 비교
- EfficientNet과 MobileNet 계열의 다양한 버전 성능 비교
- 정확도, 학습 시간, 추론 시간 종합 분석

### 2. 실용적인 데이터 증강
- 제조업 환경을 고려한 회전 변환 중심의 증강
- 클래스별 균형잡힌 데이터 생성

### 3. 이중 분류 시스템
- 부품 종류 분류와 품질 검사를 분리하여 구현
- 각각의 목적에 최적화된 모델 아키텍처 적용

### 4. 상세한 성능 분석
- 클래스별 성능 지표 제공
- 시각화를 통한 직관적인 결과 분석

## 활용 분야

- **제조업 품질 관리**: 자동화된 품질 검사 시스템
- **산업용 비전 시스템**: 실시간 부품 분류 및 검사
- **스마트 팩토리**: AI 기반 생산 라인 최적화

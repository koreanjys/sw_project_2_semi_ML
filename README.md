# `타이타닉 데이터 ML 분석`

## `팀 구성`

팀장 

김현수 : EDA, 머신러닝 모델학습, 시각화

팀원

신주용 : EDA, 머신러닝 모델학습,  발표

이화정 : EDA, 시각화, 발표자료준비

이재용 : EDA, 머신러닝 모델학습, 시각화

## `개요`

타이타닉 데이터를 학습해 승객의 생존 여부를 예측하는 모델 생성

## `프로젝트 단계`

1. feature와 label 상관관계 분석
2. feature와 label 전처리
3. 머신러닝 모델 학습 및 평가
4. 후기

## `titanic 시각화 및 EDA`

- 시각화에는 matplotlib 과 seaborn 사용
- 각 feature값과 label값의 연관도를 직관적으로 보기 위해 그래프로 확인하고 분석

## `preprocessing`

- age 결측치는 상위 25%~75% 비율의 나이로 랜덤하게 적용
- Embarked 의 2개 행은 결측치라서 제거
- 필요없는 식별값 제거 ('Cabin', 'Ticket', 'Name', 'PassengerId')
- train test 비율은 7:3
- pipeline 모듈을 사용해서 동시에 전처리 진행
- Numerical => StandardScaler
- Categorical => OneHotEncoder
- 파생 column 생성 (family => 가족과 동승한 승객 1, 아니면 0)

## `머신러닝 학습 및 평가`

- Stacking을 통한 모델 비교: SVM > XGB > RandomForest > ExtraTrees > LogisticReression > DecisionTree
세부적인 모델링을 통한 비교: XGB > SVM > LogisticReression > DecisionTree

- 예측 결과는 약 80% 전후로 나왔으나 그래도 가장 높게 나온 값은 82%로 XGB가 가장 잘 나왔다.

## `후기`

- 결측치, 이상치가 많았으나 시간관계상 자세한 내용을 파악하기 힘들었기에 결측치 제거 위주로 전처리를 진행했다. 만일 성능을 더 끌어 올리려면 디테일한 내용을 파악하고 결측치와 이상치를 잘 처리해서 모델 성능을 올려줄 수 있다.
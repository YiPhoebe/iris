## 🌱 Iris 데이터셋 분류 프로젝트📌 프로젝트 개요

본 프로젝트에서는 **Iris 데이터셋**을 활용하여 **결정트리(Decision Tree)와 로지스틱 회귀(Logistic Regression) 모델을 구축하여 품종을 분류**하는 작업을 수행합니다. 또한 데이터 탐색(EDA), 통계 분석, 머신러닝 모델링, 성능 평가 및 개선 방안을 다룹니다.

---

## 📊 1. 데이터 탐색 및 전처리

### ✅ 데이터셋 정보

- **데이터 출처**: Scikit-learn `load_iris()`
- **특성(Features)**: `sepal length`, `sepal width`, `petal length`, `petal width`
- **레이블(Labels)**: `setosa`, `versicolor`, `virginica`
- **총 샘플 수**: 150개

### ✅ 데이터 전처리

- 결측치 없음 (완전한 데이터셋)
- 변수 간 상관관계 분석
- 데이터 정규성 검정 (Shapiro-Wilk Test)

---

## 📊 2. 탐색적 데이터 분석 (EDA)

- **상관계수 분석**: `petal length`와 `petal width`가 강한 양의 상관관계를 보임.
- **박스플롯 분석**: 품종별 특성 차이를 시각적으로 확인.
- **ANOVA 검정**: 모든 변수에서 품종 간 평균 차이가 유의미함 (p < 0.05).

---

## 🤖 3. 머신러닝 모델 구축

### ✅ 1) 결정트리 (Decision Tree)

- `DecisionTreeClassifier`을 사용하여 품종을 예측.
- **Feature Importance 분석** 결과 `petal length`와 `petal width`가 가장 중요한 변수로 확인됨.
- 트리 다이어그램을 통해 분기 기준 및 의사결정 과정 시각화.

### ✅ 2) 로지스틱 회귀 (Logistic Regression)

- `LogisticRegression` 모델을 사용하여 품종을 분류.
- **결정트리보다 높은 정확도(96.67%)를 기록**하며, 더 안정적인 성능을 보임.

### ✅ 3) 모델 성능 비교

| 모델                    | 정확도 (Accuracy) | F1-score |
| ----------------------- | ----------------- | -------- |
| **결정트리**      | 93.33%            | 93.33%   |
| **로지스틱 회귀** | 96.67%            | 96.66%   |

📌 **결론:** 로지스틱 회귀 모델이 결정트리보다 더 높은 정확도를 보이며, 일반화 성능이 우수함.

---

## 🔧 4. 모델 개선 방안

### ✅ 1) 데이터 전처리

- **StandardScaler 적용**하여 특성 스케일링 → 로지스틱 회귀 성능 개선 가능.
- **PCA 적용**하여 차원 축소 → 결정트리 모델의 과적합 방지.

### ✅ 2) 하이퍼파라미터 튜닝

- 결정트리: `max_depth` 조정하여 과적합 방지.
- 로지스틱 회귀: `C` 값 최적화하여 일반화 성능 향상.
- `GridSearchCV`를 활용하여 최적 하이퍼파라미터 탐색.

### ✅ 3) 모델 변경

- **앙상블 모델(Random Forest, Gradient Boosting) 적용**하여 성능 향상 가능.
- **SVM, 신경망 모델(MLPClassifier) 실험**을 통해 비선형 관계를 학습할 수도 있음.
- **교차 검증(Cross-validation) 적용**하여 모델 성능을 안정적으로 평가.

---

## 🚀 5. 결론 및 향후 방향

- **`petal length`와 `petal width`가 품종을 분류하는 데 가장 중요한 변수임을 확인**.
- **로지스틱 회귀 모델이 가장 높은 성능(96.67%)을 보였으며, 결정트리는 상대적으로 과적합 가능성이 있음**.
- **앙상블 기법, 비선형 모델, 하이퍼파라미터 튜닝을 통해 추가적인 성능 향상을 기대할 수 있음**.

📌 **👉 본 프로젝트는 머신러닝 기반의 분류 문제를 해결하는 과정을 다루었으며, 향후 다양한 모델 및 기법을 실험해볼 수 있습니다! 🚀🔥**

# Ubion_Project1
![image](https://github.com/user-attachments/assets/7e3ade20-355a-4214-bda6-c77fb16d10ae)
### ProJect WorkFlow

#### 데이터 수집 
- 상장 승인 기업 (1150개) + 비상장외감기업 (32,088개) 대상 재무 / 비재무 데이터 수집
  * 참고) 기술특례기업 및 결측치가 있는 기업들을 제외한 기업 수.

#### 데이터 전처리
- 이상치를 윈저라이징을 통해 처리하였으며, MinMaxScaler를 진행
- Lasso 방식을 활용하여 전체 변수 중 예측에 중요한 변수를 선택
- 
#### 모델링
- train_test_split(stratify)를 사용해서 test와 train의 레이블 분포를 맞추기
- 클래스 불균형 해결 방법
  - 방식 1) SMOTE방식으로 label1 (상장 기업) 수 늘리기
  - 방식 2)StratiftKflod로 클래스 불균형을 해소하면서 학습 시키기
- XGBoost, CatBoost, LightGBM 등 머신러닝을 방식을 통해 예측 모델 생성

#### 결과
- XGBoost, LightGBM, CatBoost 중에서 CatBoost가 가장 높은 F1-점수를 기록
- CatBoost의 주요 변수: 기업순이익률, 유동자산구성비율, 자기자본구성비율, 총자본증가율 → 재무적 지표가 상장 가능성에 큰 영향을 미침
- 이들 재무 지표는 기업의 수익 창출 능력, 규모, 안정성을 평가하는 핵심 요소
- 상장 전/후의 재무적 특징을 비교·분석함으로써 비상장기업 투자 정보 제공 가능
- 결과적으로 투자자들은 상장 가능성이 높은 기업에 투자 기회를 얻고, 비상장기업 시장 활성화에도 기여하게 됨

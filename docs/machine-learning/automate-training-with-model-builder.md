---
title: 모델 작성기란 무엇이며 어떻게 작동하나요?
description: ML.NET 모델 작성기를 사용하여 기계 학습 모델을 자동으로 학습하는 방법
ms.date: 03/25/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 9cf66455109908ebd9fc10e62cf4f067609b57d9
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344776"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a>모델 작성기란 무엇이며 어떻게 작동하나요?

ML.NET 모델 작성기는 사용자 지정 기계 학습 모델을 빌드, 학습 및 배포하기 위한 직관적인 그래픽 Visual Studio 확장 기능입니다.

모델 작성기는 AutoML(자동 기계 학습)을 사용하여 다양한 기계 학습 알고리즘과 설정을 탐색하여 시나리오에 가장 적합한 것을 찾아냅니다.

모델 작성기를 사용하기 위해 기계 학습 전문 지식이 필요하지 않습니다. 필요한 것은 약간의 데이터와 해결해야 할 문제뿐입니다. 모델 작성기는 .NET 애플리케이션에 모델을 추가하는 코드를 생성합니다.

![모델 작성기 Visual Studio 확장 사용자 인터페이스 애니메이션](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> 모델 작성기는 현재 미리 보기로 제공됩니다.

## <a name="scenario"></a>시나리오

애플리케이션에 대한 기계 학습 모델을 생성하기 위해 모델 작성기에 다양한 시나리오를 가져올 수 있습니다.

시나리오는 데이터를 사용하여 수행할 예측 유형에 대한 설명입니다. 예를 들어:

- 과거 판매 데이터를 기반으로 향후 제품 판매량 예측
- 고객 리뷰에 따라 감정을 긍정 또는 부정으로 분류
- 은행 트랜잭션이 사기인지 여부를 검색
- 고객 피드백 문제를 회사의 올바른 팀에 전달

### <a name="which-machine-learning-scenario-is-right-for-me"></a>어떤 기계 학습 시나리오가 나에게 적합한가요?

모델 작성기에서 시나리오를 선택해야 합니다. 시나리오 형식은 수행하려는 예측의 종류에 따라 다릅니다.

#### <a name="text-classification"></a>텍스트 분류

분류는 데이터를 범주로 분류하는 데 사용됩니다.

![사기 탐지, 위험 완화 및 애플리케이션 심사를 포함한 이진 분류의 예를 보여 주는 다이어그램](media/binary-classification-examples.png)

![문서 및 제품 분류, 지원 티켓 라우팅 및 고객 이슈 우선 순위 지정을 포함한 다중 클래스 분류의 예](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a>값 예측

회귀는 숫자를 예측하는 데 사용됩니다.

![가격 예측, 매출 예측 및 예측 유지 관리와 같은 회귀 예를 보여 주는 다이어그램](media/regression-examples.png)

#### <a name="image-classification"></a>이미지 분류

이미지 분류는 다른 범주의 이미지를 식별하는 데 사용될 수 있습니다. 예를 들어 다른 종류의 지형이나 동물 또는 제조 결함이 있습니다.

이미지 집합이 있고 이미지를 여러 범주로 분류하려는 경우 이미지 분류 시나리오를 사용할 수 있습니다.

#### <a name="recommendation"></a>권장

추천 시나리오는 특정 사용자의 좋아요 및 싫어요가 다른 사용자와 얼마나 비슷한지에 따라 해당 사용자에 대한 추천 항목 목록을 예측합니다.

사용자 집합과 "제품" 집합(예: 구매할 항목, 영화, 책 또는 TV 프로그램) 그리고 해당 제품에 대한 사용자 "평점"이 있는 경우 추천 시나리오를 사용할 수 있습니다.

## <a name="environment"></a>환경

컴퓨터에서 로컬로 또는 Azure 클라우드에서 기계 학습 모델을 학습시킬 수 있습니다.

로컬로 학습시키는 경우 컴퓨터 리소스(CPU, 메모리 및 디스크)의 제약 조건 내에서 작업합니다. 클라우드에서 학습시키는 경우에는 특히 대규모 데이터 집합의 시나리오 요구 사항에 맞게 리소스를 확장할 수 있습니다.

로컬 학습은 모든 시나리오에서 지원됩니다.

Azure 학습은 이미지 분류에 대해 지원됩니다.

## <a name="data"></a>데이터

시나리오를 선택하면 모델 작성기에서 데이터 세트를 제공하라는 메시지가 표시됩니다. 이 데이터는 시나리오에 가장 적합한 모델을 학습, 평가 및 선택하는 데 사용됩니다.

![모델 작성기 단계를 보여 주는 다이어그램](media/model-builder-steps.png)

모델 작성기는 SQL 데이터베이스 형식 뿐만 아니라 .tsv, .csv, .txt 형식의 데이터 세트를 지원합니다. .txt 파일을 사용하는 경우 열을 `,`, `;` 또는 `/t`로 구분해야 하며 파일에는 머리글 행이 있어야 합니다.

데이터 세트가 이미지로 구성된 경우 지원되는 파일 형식은 `.jpg` 및 `.png`입니다.

자세한 내용은 [모델 작성기로 학습 데이터 로드](how-to-guides/load-data-model-builder.md)를 참조하세요.

### <a name="choose-the-output-to-predict-label"></a>예측할 출력을 선택합니다(레이블).

데이터 세트는 학습 예제의 행과 특성 열을 나열한 표입니다. 각 행에는 다음이 있습니다.

- **레이블**(예측하려는 특성)
- **기능**(레이블을 예측하기 위한 입력으로 사용되는 특성).

주택 가격 예측 시나리오의 경우 다음과 같은 기능을 사용할 수 있습니다.

- 집의 평방 피트
- 침실과 욕실의 수
- 우편 번호

이 레이블은 평방 피트, 침실, 욕실 값 및 우편 번호 행에 대해 기록한 주택 가격입니다.

![크기 객실 우편 번호 및 가격 레이블로 구성된 기능을 갖춘 주택 가격 데이터의 행과 열을 보여주는 표](media/model-builder-data.png)

### <a name="example-datasets"></a>예제 데이터 세트

아직 사용자 고유의 데이터가 없는 경우 다음 데이터 세트 중 하나를 사용해 보세요.

|시나리오|예제|데이터|레이블|기능|
|-|-|-|-|-|
|분류|판매 변칙 예측|[제품 판매 데이터](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|제품 판매|월|
||웹 사이트 댓글의 감정 예측|[웹 사이트 주석 데이터](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|레이블(부정적인 감정인 경우 0, 긍정적인 감정인 경우 1)|주석, 연도|
||사기성 신용 카드 거래 예측|[신용 카드 데이터](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|클래스(사기일 경우 1, 그렇지 않으면 0)|수량, V1-V28(익명화된 기능)|
||GitHub 리포지토리에서 문제 유형 예측|[GitHub 문제 데이터](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|Area|제목, 설명|
|값 예측|택시 요금 예측|[택시 요금 데이터](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|요금|운행 시간, 거리|
|이미지 분류|문제의 범주 예측|[꽃 이미지](http://download.tensorflow.org/example_images/flower_photos.tgz)|꽃의 종류: 데이지, 민들레, 장미, 해바라기, 튤립|이미지 데이터 자체|
|권장|좋아하는 영화 예측|[영화 평점](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|사용자, 영화|등급|

## <a name="train"></a>학습

시나리오, 데이터 및 레이블을 선택하면 모델 작성기가 모델을 학습합니다.

### <a name="what-is-training"></a>학습이란?

학습은 모델 작성기가 시나리오에 대한 질문에 대답하는 방법을 모델에 알려주는 자동 프로세스입니다. 학습하면 이전에 없었던 입력 데이터로 예측할 수 있습니다. 예를 들어 주택 가격을 예측하고 새 집이 시장에 나온다면 판매 가격을 예측할 수 있습니다.

모델 작성기는 AutoML(자동 기계학습)을 사용하기 때문에 학습 중에 입력하거나 튜닝할 필요가 없습니다.

### <a name="how-long-should-i-train-for"></a>얼마나 학습해야 하나요?

모델 작성기는 AutoML을 사용하여 여러 모델을 탐색하고 가장 잘 수행하는 모델을 찾습니다.

학습 기간이 길수록 AutoML에서 더 넓은 설정 범위로 더 많은 모델을 탐색할 수 있습니다.

아래 표는 로컬 컴퓨터에서 예제 데이터 세트에 대해 양호한 성능을 얻는 데 걸리는 평균 시간을 요약하여 보여 줍니다.

|데이터 세트 크기|평균 학습 시간|
|------------|---------------------|
|0 - 10MB|10초|
|10 - 100MB|10분|
|100 - 500MB|30분|
|500 - 1GB|60분|
|1GB+|3시간 이상|

이러한 숫자는 단지 안내일 뿐입니다. 정확한 학습 길이는 다음에 따라 달라집니다.

- 모델에 대한 입력으로 사용되는 기능(열)의 수
- 열의 형식
- ML 작업
- 학습에 사용되는 컴퓨터의 CPU, 디스크 및 메모리 성능

## <a name="evaluate"></a>Evaluate

평가는 모델의 성능을 측정하는 프로세스입니다. 모델 작성기는 학습된 모델을 통해 새 테스트 데이터를 사용하여 예측한 다음, 예측이 얼마나 올바른지를 측정합니다.

모델 작성기는 학습 데이터를 학습 집합과 테스트 집합으로 분할합니다. 학습 데이터(80%)는 모델을 학습하는 데 사용되며, 테스트 데이터(20%)는 모델을 평가하기 위해 보류됩니다.

### <a name="how-do-i-understand-my-model-performance"></a>모델 성능을 어떻게 이해할까요?

시나리오는 기계 학습 작업에 매핑됩니다. 각 ML 작업에는 고유한 평가 메트릭 집합이 있습니다.

#### <a name="value-prediction"></a>값 예측

값 예측 문제에 대한 기본 메트릭은 RSquared이고, RSquared 값의 범위는 0과 1 사이입니다. 가능한 최고의 값은 1입니다. 즉, RSquared의 값이 1에 가까울수록 모델의 성능이 향상됩니다.

절대 손실, 제곱 손실 및 RMS 손실과 같이 보고된 다른 메트릭은 추가 메트릭이며 모델의 성능을 이해하고 다른 값 예측 모델과 비교하는 데 사용할 수 있습니다.

#### <a name="classification-2-categories"></a>분류(2개 범주)

분류 문제에 대한 기본 메트릭은 정확도입니다. 정확도는 모델이 테스트 데이터 세트에 대해 내리는 정확한 예측 비율을 정의합니다. 100% 또는 1.0에 가까울수록 좋습니다.

참 긍정 비율과 거짓 긍정 비율을 측정하는 AUC(곡선 아래의 영역)와 같은 보고된 기타 메트릭은 허용 가능한 모델에 대해 0.50보다 커야 합니다.

F1 점수와 같은 추가 메트릭을 사용하여 전체 정밀도와 재현율 간의 균형을 제어할 수 있습니다.

#### <a name="classification-3-categories"></a>분류(3개 이상 범주)

다중 클래스 분류에 대한 기본 메트릭은 Micro 정확도입니다. Micro 정확도는 100% 또는 1.0에 가까울수록 좋습니다.

다중 클래스 분류에 대한 또 다른 중요한 메트릭은 Macro 정확도입니다. Micro 정확도와 마찬가지로 1.0에 가까울수록 좋습니다. 이러한 두 가지 유형의 정확도를 고려하는 올바른 방법은 다음과 같습니다.

- Micro 정확도: 들어오는 티켓이 올바른 팀으로 분류되는 빈도
- Macro 정확도: 평균 팀의 경우 들어오는 티켓이 해당 팀에 올바르게 분류된 빈도

### <a name="more-information-on-evaluation-metrics"></a>평가 메트릭에 대한 자세한 내용

자세한 내용은 [모델 평가 메트릭](resources/metrics.md)을 참조하세요.

## <a name="improve"></a>개선

모델 성능 점수가 원하는 만큼 좋지 않은 경우 다음을 수행할 수 있습니다.

- 더 긴 시간 동안 학습합니다. 시간이 지날수록 자동화된 기계 학습 엔진은 더 많은 알고리즘과 설정으로 실험합니다.

- 더 많은 데이터를 추가합니다. 경우에 따라 데이터의 양이 고품질 기계 학습 모델을 학습하기에 충분하지 않을 수도 있습니다.

- 데이터의 균형을 유지합니다. 분류 작업의 경우 학습 집합이 범주 전반에 걸쳐 균형을 유지하는지 확인합니다. 예를 들어 100개의 학습 예제에 대한 네 개의 클래스가 있고, 90개의 레코드에 두 개의 첫 번째 클래스(tag1 및 tag2)가 사용되지만 다른 두 개 클래스(tag3 및 tag4)가 나머지 10개의 레코드에만 사용되는 경우 균형 있는 데이터가 부족하여 모델이 tag3 또는 tag4를 올바르게 예측하는 데 어려움을 겪을 수 있습니다.

## <a name="code"></a>코드

평가 단계 후 모델 작성기는 모델 파일 및 모델을 애플리케이션에 추가하는 데 사용할 수 있는 코드를 출력합니다. ML.NET 모델은 zip 파일로 저장됩니다. 모델을 로드하고 사용하는 코드는 솔루션에는 새 프로젝트로 추가됩니다. 또한 모델 작성기는 실행 중인 모델을 보기 위해 실행할 수 있는 샘플 콘솔 앱을 추가합니다.

또한 모델 작성기는 모델을 생성하는 데 사용되는 단계를 이해할 수 있도록 모델을 생성하는 코드를 출력합니다. 모델 학습 코드를 사용하여 새 데이터로 모델을 다시 학습할 수도 있습니다.

## <a name="whats-next"></a>새로운 기능

모델 작성기 Visual Studio 확장 [설치](how-to-guides/install-model-builder.md)

[가격 예측 또는 모든 회귀 시나리오](tutorials/predict-prices-with-model-builder.md) 시도

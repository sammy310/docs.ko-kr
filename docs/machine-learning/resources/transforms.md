---
title: 기계 학습 데이터 변환 - ML.NET
description: ML.NET에서 지원되는 기능 엔지니어링 구성 요소를 탐색합니다.
author: JRAlexander
ms.custom: seodec18
ms.date: 01/14/2019
ms.openlocfilehash: e649c9a27f0409cb9cdfb554963b5c0e732991f2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355413"
---
# <a name="machine-learning-data-transforms---mlnet"></a>기계 학습 데이터 변환 - ML.NET

다음 테이블은 ML.NET에서 지원되는 모든 데이터 변환에 대한 정보를 포함합니다.

> [!NOTE]
> ML.NET은 현재 미리 보기로 제공됩니다. 일부 데이터 변환은 현재 지원되지 않습니다. 특정 변환에 대한 요청을 제출하려면 [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) GitHub 리포지토리에서 문제를 엽니다.

## <a name="combiners-and-segregators"></a>결합자 및 분리기

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.GroupTransform> | 스칼라 열의 값을 인접 그룹 ID 기반의 벡터로 그룹화합니다. |
| <xref:Microsoft.ML.Transforms.UngroupTransform> | 벡터 열을 행의 시퀀스로 그룹을 해제합니다(그룹 변환의 반대). |

## <a name="conversions"></a>변환

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Conversions.HashingTransformer> | 단일 반환된 열 또는 벡터 열을 해싱합니다. 벡터 열의 경우 각 슬롯을 개별적으로 해싱합니다. 텍스트 값 또는 키 값을 해싱할 수 있습니다. |
| <xref:Microsoft.ML.Transforms.Conversions.HashJoiningTransform> | 여러 열 값을 해시로 변환합니다. 이 변환은 숫자 및 텍스트 입력 모두와 단일 및 벡터 값 열 모두를 허용합니다. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToBinaryVectorMappingTransformer> | 키를 이진 벡터 열로 변환합니다. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToValueMappingTransformer > | KeyValues 메타데이터를 활용하여 키 인덱스를 KeyValues 메타데이터의 해당 값으로 매핑합니다. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToVectorMappingTransformer> | 키를 벡터 열로 변환합니다. |
| <xref:Microsoft.ML.Transforms.Conversions.TypeConvertingTransformer> | 유형을 변환할 수 있는 경우 기본 열 유형을 변경합니다. |
| <xref:Microsoft.ML.Transforms.Conversions.ValueToKeyMappingTransformer> | 입력 값(단어, 숫자 등)을 사전의 인덱스로 변환합니다. |

## <a name="deep-learning"></a>딥러닝

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | 데이터를 기존 ONNX 모델에 제공하고 점수를 반환합니다(예측). |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | 미리 학습된 TensorFlow 모델을 사용하여 점수를 매기거나 TensorFlow 모델을 재교육할 수 있습니다. |

## <a name="feature-extraction"></a>기능 추출

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.CustomStopWordsRemovingTransform> | 개별 토큰(대/소문자를 구분하지 않는 비교)을 중지 단어와 비교하여 지정된 중지 단어의 목록을 제거합니다.|
| <xref:Microsoft.ML.ImageAnalytics.ImageGrayscaleTransform> | 하나 이상의 ImageType 열을 사용하고 동일한 이미지의 회색조 표현으로 변환합니다.|
| <xref:Microsoft.ML.ImageAnalytics.ImageLoaderTransform> | 하나 이상의 ReadOnlyMemory 열을 사용하고 ImageType으로 로드합니다. |
| <xref:Microsoft.ML.ImageAnalytics.ImagePixelExtractorTransform> | 하나 이상의 ImageType 열을 사용하고 벡터 표현으로 변환합니다.|
| <xref:Microsoft.ML.ImageAnalytics.ImageResizerTransform> | 하나 이상의 ImageType 열을 사용하고 제공된 높이 및 너비로 크기를 조정합니다.|
| <xref:Microsoft.ML.Transforms.Text.LatentDirichletAllocationTransformer> | Latent Dirichlet 할당의 최신 구현인 LightLDA를 구현합니다.|
| <xref:Microsoft.ML.Transforms.LoadTransform> | 지정된 모델 파일에서 특정 변환을 로드합니다. 직렬화된 체인에서 'cherry picking' 변환을 허용하거나 다른(그러나 여전히 호환 가능한) 데이터 뷰에 미리 학습된 변환을 적용하도록 합니다. |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractingTransformer> | 키의 지정된 벡터에서 ngrams 개수 모음(1-n 길이의 연속 값의 시퀀스)을 생성합니다. ngrams의 사전을 빌드하고 모음의 인덱스로 사전의 ID를 사용하여 이를 수행합니다. |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractorTransform> | 토큰화된 텍스트의 컬렉션(ReadOnlyMemory의 벡터) 또는 키의 벡터를 숫자 기능 벡터로 설정합니다. 기능 벡터는 ngrams의 개수입니다(1-n 길이의 연속 토큰- 단어 또는 키의 시퀀스). |
| <xref:Microsoft.ML.Transforms.Text.NgramHashExtractingTransformer> | 해싱을 사용하여 토큰화된 텍스트의 컬렉션(ReadOnlyMemory의 벡터)을 숫자 기능 벡터로 설정합니다. |
| <xref:Microsoft.ML.Transforms.Text.NgramHashingTransformer> | 지정된 텍스트에서 ngrams 개수 모음(1-n 길이의 연속 단어의 시퀀스)을 생성합니다. |
| <xref:Microsoft.ML.Transforms.Categorical.OneHotEncodingTransformer> | 데이터를 기반으로 범주의 사전을 빌드하고 배열의 인덱스로 사전의 ID를 사용하여 범주 값을 표시기 배열로 변환합니다. |
| <xref:Microsoft.ML.Transforms.Projections.PcaTransform> | 기능 벡터의 프로젝션을 낮은 순위 하위 공간으로 계산합니다. |
| <xref:Microsoft.ML.Transforms.Text.SentimentAnalyzingTransformer> | 미리 학습된 감정 모델을 사용하여 입력 문자열의 점수를 매깁니다. |
| <xref:Microsoft.ML.Transforms.Text.StopWordsRemovingTransformer> | 개별 토큰(대/소문자를 구분하지 않는 비교)을 중지 단어와 비교하여 중지 단어의 언어별 목록(가장 일반적인 단어)을 제거합니다. |
| <xref:Microsoft.ML.Transforms.Text.WordBagBuildingTransformer> | 지정된 텍스트에서 ngrams 개수 모음(연속 단어의 시퀀스)을 생성합니다. ngrams의 사전을 빌드하고 모음의 인덱스로 사전의 ID를 사용하여 이를 수행합니다. |
| <xref:Microsoft.ML.Transforms.Text.WordHashBagProducingTransformer> | 지정된 텍스트에서 ngrams 개수 모음(1-n 길이의 연속 단어의 시퀀스)을 생성합니다. 각 ngram을 해싱하고 모음의 인덱스로 해시 값을 사용하여 이를 수행합니다. |
| <xref:Microsoft.ML.Transforms.Text.WordTokenizingTransformer> | 구분 문자를 사용하여 텍스트를 단어로 분할합니다. |


## <a name="image-model-featurizers"></a>이미지 모델 Featurizer

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.AlexNetExtension> | 미리 학습된 [AlexNet](https://en.wikipedia.org/wiki/AlexNet) 모델을 사용하기 위해 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>와 함께 사용되는 확장 메서드입니다. 이 확장을 포함하는 NuGet도 이진 모델 파일을 포함하도록 보장됩니다. |
| <xref:Microsoft.ML.Transforms.ResNet18Extension> | 미리 학습된 ResNet18 모델을 사용하기 위해 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>와 함께 사용되는 확장 메서드입니다. 이 확장을 포함하는 NuGet도 이진 모델 파일을 포함하도록 보장됩니다. |
| <xref:Microsoft.ML.Transforms.ResNet50Extension> | 미리 학습된 ResNet50 모델을 사용하기 위해 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>와 함께 사용되는 확장 메서드입니다. 이 확장을 포함하는 NuGet도 이진 모델 파일을 포함하도록 보장됩니다. |
| <xref:Microsoft.ML.Transforms.ResNet101Extension> | 미리 학습된 ResNet101 모델을 사용하기 위해 <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>와 함께 사용되는 확장 메서드입니다. 이 확장을 포함하는 NuGet도 이진 모델 파일을 포함하도록 보장됩니다. |

## <a name="label-parsing"></a>레이블 구문 분석

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.LabelConvertTransform> |  레이블을 변환합니다. |
| <xref:Microsoft.ML.Transforms.LabelIndicatorTransform> | 주로 OVA와 함께 사용하기 위해 다중 클래스 레이블을 이진 True, False 레이블로 다시 매핑합니다.|

## <a name="missing-values"></a>누락 값

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueDroppingTransformer> | 열에서 누락 값을 삭제합니다. |
| <xref:Microsoft.ML.Transforms.MissingValueIndicatorTransform> | 입력 열과 동일한 수의 슬롯을 사용하여 부울 출력 열을 만듭니다. 여기서 출력 값은 입력 열의 값이 누락된 경우 true입니다. |
| <xref:Microsoft.ML.Transforms.MissingValueReplacingTransformer> | 기본값 또는 평균값/최솟값/최댓값으로 대체하여 누락 값을 처리합니다(텍스트가 아닌 열에만 해당). |

## <a name="normalization"></a>표준화

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Projections.LpNormalizingTransformer> | Lp-Norm(벡터/행 단위) 정규화 변환입니다. |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarDblAggregator> | 벡터 값 열에 대한 평균 및 분산을 계산합니다. 현재 평균 및 M2(평균 값의 제곱차의 합계), NaNs의 수 및 0이 아닌 요소의 수를 추적합니다. |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarSngAggregator> | 벡터 값 열에 대한 평균 및 분산을 계산합니다. 현재 평균 및 M2(평균 값의 제곱차의 합계), NaNs의 수 및 0이 아닌 요소의 수를 추적합니다. |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxDblAggregator> | 벡터 값 열에 대한 최소, 최대, 스파스가 아닌 값(vCount)의 수 및 ProcessValue() 호출의 수(trainCount)를 추적합니다. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizeTransform> | 기능 범위를 표준화합니다. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizingTransformer> |기능 범위를 표준화합니다. |

## <a name="onnx"></a>Onnx

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | ONNX 표준 v1.2를 사용하는 미리 학습된 ONNX 모델의 점수를 매깁니다. |

## <a name="preprocessing"></a>전처리
| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BootstrapSamplingTransformer> | 푸아송 샘플링을 사용하는 부트스트랩 샘플링을 대략적으로 보여줍니다. |
| <xref:Microsoft.ML.Transforms.Projections.RandomFourierFeaturizingTransformer> | 임의 Fourier 기능을 생성합니다. |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | 텍스트가 문자의 시퀀스로 간주되는 문자 기반 토크나이저입니다. |
| <xref:Microsoft.ML.Transforms.Projections.VectorWhiteningTransformer> | 가중치 식별을 돕기 위해 최적화를 간소화합니다. |

## <a name="row-filters"></a>행 필터

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowShufflingTransformer> | 지정된 수의 행의 풀을 사용하여 수행하기 위해 임의 커서 시도의 순서를 섞습니다.  |
| <xref:Microsoft.ML.Transforms.SkipFilter> | 행 수를 건너뛰어 행의 하위 집합으로 입력 제한을 허용합니다. |
| <xref:Microsoft.ML.Transforms.SkipTakeFilter> | 선택적 오프셋에서 행의 하위 집합으로 입력 제한을 허용합니다. 데이터 페이징을 구현하는 데 사용될 수 있습니다. SkipTakeFilter.SkipArguments를 사용하여 만든 경우 `SkipFilter`처럼 동작합니다.
| <xref:Microsoft.ML.Transforms.TakeFilter> | N을 첫 번째 행으로 사용하여 행의 하위 집합으로 입력 제한을 허용합니다. |


## <a name="schema"></a>스키마

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnCopyingTransformer> | 데이터 세트에서 열을 복제합니다.|
| <xref:Microsoft.ML.Transforms.ColumnSelectingTransformer> | 지정된 입력에서 삭제 또는 유지할 열 집합을 선택합니다. |
| <xref:Microsoft.ML.Transforms.FeatureSelection.SlotsDroppingTransformer> | 열에서 슬롯을 삭제합니다.|
| <xref:Microsoft.ML.Transforms.OptionalColumnTransform> | 지정된 형식 및 기본 값을 사용하여 새 열을 만듭니다. |
| <xref:Microsoft.ML.Transforms.RangeFilter> | Single, Double 또는 Key(연속) 형식의 열에서 데이터 보기를 필터링합니다. 지정된 최소/최대 범위 내에 있는 값을 유지합니다. NaNs는 항상 필터링됩니다. 입력이 Key 형식인 경우 최소/최대는 값 수의 백분율로 간주됩니다. |

## <a name="tensorflow"></a>TensorFlow

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | 미리 학습된 TensorFlow 모델을 사용하여 점수를 매기거나 TensorFlow 모델을 재교육합니다. |

## <a name="text-processing-and-featurization"></a>텍스트 처리 및 기능화

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.TextNormalizingTransformer> | 텍스트 대/소문자 정규화, 분음 부호 제거, 문장 부호 및/또는 숫자를 허용하는 텍스트 정규화 변환입니다. 변환은 토큰/텍스트(ReadOnlyMemory의 벡터)의 벡터 뿐만 아니라 텍스트 입력에서 작동합니다. |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | 텍스트가 문자의 시퀀스로 간주되는 문자 기반 토크나이저입니다. |

## <a name="time-series"></a>시계열

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesProcessing.ExponentialAverageTransform> | 값의 가중치 평균을 사용합니다. ExpAvg(y_t) = a * y_t + (1-a) * ExpAvg(y_(t-1)) |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidChangePointDetector> | 적응 커널 밀도 추정 및 마틴게일을 기준으로 i.i.d. 시퀀스(임의 샘플)에 대한 변경 지점 탐지기 변환을 구현합니다. |
| <xref:Microsoft.ML.TimeSeriesProcessing.IidSpikeDetector> | 적응 커널 밀도 추정을 기준으로 i.i.d. 시퀀스(임의 샘플)에 대한 급증 탐지기 변환을 구현합니다. |
| <xref:Microsoft.ML.TimeSeriesProcessing.MovingAverageTransform> | 슬라이딩 윈도우 값의 가중치 평균을 제공합니다. |
| <xref:Microsoft.ML.TimeSeriesProcessing.PercentileThresholdTransform> | 시계열 현재 값이 슬라이딩 윈도우 상위 값 백분위 수에 속하는지 여부를 결정합니다. |
| <xref:Microsoft.ML.TimeSeriesProcessing.PValueTransform> | 슬라이딩 윈도우의 다른 값을 기준으로 시리즈 현재 값 경험적 p-값을 계산합니다. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SlidingWindowTransform> | Single 형식의 시계열에 슬라이딩 윈도우를 출력합니다. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaChangePointDetector> | 시계열의 단수 스펙트럼 모델링에 따라 변경 지점 탐지기 변환을 구현합니다. |
| <xref:Microsoft.ML.TimeSeriesProcessing.SsaSpikeDetector> | 시계열의 단수 스펙트럼 모델링에 따라 급증 탐지기 변환을 구현합니다. |

## <a name="miscellaneous"></a>기타

| 변형 | 정의 |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CompositeTransformer> | 복합 데이터 변환을 만듭니다. |
| <xref:Microsoft.ML.Transforms.CustomMappingTransformer%602> | 제공된 `IDataView`에 추가 열을 생성합니다. 행의 수를 변경하지 않으며 입력 데이터의 모든 행에 사용자 함수의 애플리케이션 결과로 표시될 수 있습니다.|
| <xref:Microsoft.ML.Transforms.GenerateNumberTransform> | 생성된 번호 시퀀스를 사용하여 열을 추가합니다. |
| <xref:Microsoft.ML.Transforms.ProduceIdTransform> | 열로 커서의 ID를 사용하여 열을 생성합니다. |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | 난수를 생성합니다. |

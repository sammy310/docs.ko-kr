---
title: ML.NET CLI를 통한 모델 학습 자동화
description: ML.NET CLI 도구를 사용하여 명령줄에서 자동으로 최상의 모델을 학습하는 방법을 알아봅니다.
ms.date: 06/03/2020
ms.custom: how-to, mlnet-tooling
ms.openlocfilehash: 0b230e4a517b6493abdb1ec975776fd286b654e3
ms.sourcegitcommit: b27645cb378d4e8137a267e5467ff31409acf6c0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103231409"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a>ML.NET CLI를 통한 모델 학습 자동화

ML.NET CLI는 .NET 개발자를 위한 모델 생성을 자동화합니다.

ML.NET API를 (ML.NET AutoML CLI 없이) 그대로 사용하려면 트레이너(특정 작업에 대한 기계 학습 알고리즘 구현)와 데이터에 적용할 데이터 변환 세트(특성 엔지니어링(Feature engineering))를 선택해야 합니다. 최적 파이프 라인은 데이터 세트마다 다르며 모든 선택에서 최적의 알고리즘을 찾으려는 시도는 복잡성을 더합니다. 나아가 각각의 알고리즘에는 조정 대상인 하이퍼 매개 변수 집합이 있습니다. 따라서 몇 주, 때에 따라서는 몇 달에 걸쳐 기계 학습 모델 최적화를 수행하여 기능 엔지니어링, 학습 알고리즘, 하이퍼 매개 변수의 최적 조합을 찾을 수 있습니다.

ML.NET CLI는 자동화된 ML을 사용하여 이 프로세스를 간소화합니다.

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET **CLI** 및 ML.NET **AutoML** 을 참조하며, 자료는 변경될 수 있습니다.

## <a name="what-is-the-mlnet-command-line-interface-cli"></a>ML.NET CLI(명령줄 인터페이스)란?

ML.NET CLI는 [.NET Core 도구](../core/tools/global-tools.md)입니다. 설치되면 여기에 기계 학습 작업 및 학습 데이터 세트를 제공하게 되며 이 도구는 애플리케이션에서 모델을 사용하기 위해 실행할 C# 코드뿐만 아니라 ML.NET 모델을 생성합니다.

다음 그림처럼 간단하게 품질 높은 ML.NET 모델(직렬화된 모델 .zip 파일)과 샘플 C# 코드를 생성하여 해당 모델을 실행/채점할 수 있습니다. 또한, 모델 생성/학습을 위한 C# 코드도 생성되므로 이렇게 생성된 “최상의 모델”에 사용되는 알고리즘과 설정을 바탕으로 연구 및 반복을 수행할 수 있습니다.

![ML.NET CLI 내 AutoML 엔진 작업](media/automate-training-with-cli/cli-high-level-process.png)

직접 코딩하지 않고도 자체 데이터 세트에서 해당 자산을 생성할 수 있기 때문에 ML.NET을 이미 알고 있더라도 생산성이 증대됩니다.

현재 ML.NET CLI에서 지원하는 ML 작업은 다음과 같습니다.

- 분류
- 재발
- 권장 사항
- 이미지 분류

사용 예(분류 시나리오):

```console
mlnet classification --dataset "yelp_labelled.txt" --label-col 1 --has-header false --train-time 10
```

![명령줄에서 ML.NET 분류](media/automate-training-with-cli/mlnet-classification-powershell.gif)

*Windows PowerShell*, *macOS/Linux bash* 또는 *Windows CMD* 에서 같은 방식으로 실행할 수 있습니다. 그러나 테이블 형식 자동 완성(매개 변수 제안)은 *Windows CMD* 에서 작동하지 않습니다.

## <a name="output-assets-generated"></a>생성된 출력 자산

CLI의 ML 작업 명령은 출력 폴더에 다음 자산을 생성합니다.

- 예측 실행에 사용할 수 있는 직렬화된 모델의 .zip("최상의 모델") 파일
- 다음을 포함한 C# 솔루션:
  - 생성된 모델을 실행/채점하는 C# 코드(해당 모델의 최종 사용자 앱에서 예측 수행)
  - 해당 모델을 생성하는 데 사용된 학습 코드를 포함한 C# 코드(교육용 또는 모델 재교육용)
- 상세 구성/파이프라인을 포함하여 평가된 여러 알고리즘 전체의 모든 반복/스윕 정보가 담긴 로그 파일

처음 두 자산은 생성된 ML 모델로 예측하기 위해 최종 사용자 앱(ASP.NET Core 웹앱, 서비스, 데스크톱 앱 등)에서 직접 사용할 수 있습니다.

세 번째 자산인 학습 코드는 생성된 모델을 학습하기 위해 CLI에서 사용한 ML.NET API 코드를 보여주므로, 바탕의 CLI 및 AutoML에서 선택한 특정 트레이너/알고리즘 및 하이퍼 매개 변수를 살펴볼 수 있습니다.

## <a name="understanding-the-quality-of-the-model"></a>모델의 품질 이해

CLI 도구를 사용하여 “최상의 모델”을 생성할 때는 대상으로 하는 ML 작업에 적합하게 품질 메트릭(예: 정확도, R 제곱)이 표시됩니다.

여기에서는 ML 작업에 따라 메트릭이 그룹화되어 요약되므로 자동 생성된 ‘최상의 모델’ 품질을 이해할 수 있습니다.

### <a name="metrics-for-classification-models"></a>분류 모델에 대한 메트릭

다음 이미지는 CLI에서 찾은 상위 5개 모델에 대한 분류 메트릭 목록을 표시합니다.

![상위 5개 모델에 대한 분류 메트릭](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

 정확도는 분류 문제에 대해 널리 사용되는 메트릭이나, 다음 참조에서 설명된 것처럼 최상의 모델을 선택하기 위해 항상 가장 적합한 메트릭인 것은 아닙니다. 추가적인 메트릭을 사용하여 모델 품질을 평가해야 하는 경우도 있습니다.

CLI에서 출력하는 메트릭을 살펴보고 이해하려면 [Evaluation metrics for classification](resources/metrics.md#evaluation-metrics-for-multi-class-classification)(분류에 대한 평가 메트릭)을 참조하세요.

### <a name="metrics-for-regression-and-recommendation-models"></a>회귀용 메트릭 및 권장 모델

관찰된 값과 모델의 예측된 값 사이의 차이가 적고 편향되지 않은 경우 회귀 모델이 데이터에 잘 맞습니다. 회귀는 특정 메트릭으로 평가할 수 있습니다.

CLI에서 찾은 상위 5개 품질 모델에 대한 유사한 메트릭 목록이 표시됩니다. 단, 이 경우 상위 5개는 회귀 ML 작업과 관련이 있습니다.

![상위 5개 모델에 대한 회귀 메트릭](media/automate-training-with-cli/cli-regression-metrics.png)

CLI에서 출력하는 메트릭을 살펴보고 이해하려면 [회귀용 평가 메트릭](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation)을 참조하세요.

## <a name="see-also"></a>참조

- [ML.NET CLI 도구를 설치하는 방법](how-to-guides/install-ml-net-cli.md)
- [자습서: ML.NET CLI를 사용하여 감정 분석](tutorials/sentiment-analysis-cli.md)
- [ML.NET CLI 명령 참조](reference/ml-net-cli-reference.md)
- [ML.NET CLI의 원격 분석](resources/ml-net-cli-telemetry.md)

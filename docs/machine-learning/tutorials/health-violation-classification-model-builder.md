---
title: '자습서: 모델 작성기를 사용하여 위생 위반 분류'
description: 이 자습서에서는 ML.NET 모델 작성기를 사용하여 다중 클래스 분류 모델을 빌드하고 샌프란시스코의 식당 위생 위반 심각도를 분류하는 방법을 보여 줍니다.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: 6a36989f9453208e436ef8a4db2d4440aa0a1382
ms.sourcegitcommit: 2ff49dcf9ddf107d139b4055534681052febad62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2020
ms.locfileid: "80438185"
---
# <a name="tutorial-classify-the-severity-of-restaurant-health-violations-with-model-builder"></a>자습서: 모델 작성기를 사용하여 식당 위생 위반의 심각도 분류

모델 작성기를 사용하여 다중 클래스 분류 모델을 빌드하고 위생 점검 중에 발견된 식당 위생 위험 수준을 분류하는 방법을 알아봅니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> - 데이터 준비 및 이해
> - 시나리오 선택
> - 데이터베이스에서 데이터 로드
> - 모델 학습
> - 모델 평가
> - 예측에 모델 사용

> [!NOTE]
> 모델 작성기는 현재 미리 보기로 제공됩니다.

## <a name="prerequisites"></a>사전 요구 사항

필수 구성 요소 및 설치 지침 목록을 보려면 [모델 작성기 설치 가이드](../how-to-guides/install-model-builder.md)를 방문하세요.

## <a name="model-builder-multiclass-classification-overview"></a>모델 작성기 다중 클래스 분류 개요

이 샘플은 모델 작성기로 빌드된 기계 학습 모델을 사용하여 위생 위반 위험을 범주화하는 C# .NET Core 콘솔 애플리케이션을 만듭니다. [dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

1. "RestaurantViolations"라는 **C# .NET Core 콘솔 애플리케이션**을 만듭니다. **솔루션 및 프로젝트를 같은 디렉터리에 배치**가 **선택 취소**되었는지(VS 2019) 또는 **솔루션의 디렉터리 만들기**가 **선택되었는지**(VS 2017)를 확인하세요.

## <a name="prepare-and-understand-the-data"></a>데이터 준비 및 이해

> 기계 학습 모델을 학습하고 평가하는 데 사용되는 데이터 세트는 원래 [San Francisco Department of Public Health Restaurant Safety Scores](https://www.sfdph.org/dph/EH/Food/score/default.asp)(샌프란시스코 공중 보건 식당 안전 점수)를 기반으로 합니다. 편의상 모델을 학습하고 예측하는 데 관련된 열만 포함하도록 데이터 세트를 압축했습니다. [데이터 세트](https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i?row_index=0)에 대해 알아보려면 다음 웹 사이트를 방문하세요.

[식당 안전 점수 데이터 세트를 다운로드](https://github.com/luisquintanilla/machinelearning-samples/raw/AB1608219/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantScores.zip)하고 압축을 풉니다.

데이터 세트의 각 행에는 위생을 점검하는 동안 관측된 위반에 대한 정보 및 이러한 위반이 공중 보건 및 안전에 미치는 위협에 대한 위험 평가가 포함됩니다.

| InspectionType | ViolationDescription | RiskCategory |
| --- | --- | --- |
| 루틴 - 예정되지 않음 | 부적절하게 씻었거나 위생 처리된 식품 접촉 표면 | 위험 수준 보통 |
| 새 소유권 | 고위험 해충 감염 | 위험 수준 높음 |
| 루틴 - 예정되지 않음 | 행주가 깨끗하지 않거나 제대로 보관되지 않았거나 살균제가 부적절함 | 위험 수준 낮음 |

- **InspectionType**: 검사 유형입니다. 새로운 시설에 대한 최초 점검, 정기 점검, 불만 사항 점검 및 기타 여러 유형이 될 수 있습니다.
- **ViolationDescription**: 점검 중 발견된 위반에 대한 설명입니다.
- **RiskCategory**: 위반이 공중 보건 및 안전에 미치는 위험의 심각도입니다.

`label`은 예측할 열입니다. 분류 작업을 수행하는 경우 목표는 범주(텍스트 또는 숫자)를 할당하는 것입니다. 이 분류 시나리오에서 위반의 심각도에는 낮음, 보통 또는 높음 위험 값이 할당됩니다. 따라서 **RiskCategory**는 레이블입니다. `features`는 `label` 예측을 위해 모델에 제공하는 입력입니다. 이 경우 **InspectionType** 및 **ViolationDescription**은 **RiskCategory**를 예측하기 위한 기능 또는 입력으로 사용됩니다.

## <a name="choose-a-scenario"></a>시나리오 선택

![Visual Studio의 모델 작성기 마법사](./media/sentiment-analysis-model-builder/model-builder-screen.png)

모델을 학습하려면 모델 작성기에서 제공하는 사용 가능한 기계 학습 시나리오 목록에서 선택합니다. 이 경우 시나리오는 *문제 분류*입니다.

1. **솔루션 탐색기**에서 *RestaurantViolations* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **Machine Learning**을 선택합니다.
1. 이 샘플의 경우 시나리오는 다중 클래스 분류입니다. 모델 작성기의 *시나리오* 단계에서 **문제 분류** 시나리오를 선택합니다.

## <a name="load-the-data"></a>데이터 로드

모델 작성기는 SQL Server 데이터베이스 또는 로컬 파일 `csv` 또는 `tsv` 형식에서 데이터를 허용합니다.

1. 모델 작성기 도구의 데이터 단계의 데이터 원본 드롭다운에서 **SQL Server**를 선택합니다.
1. **SQL Server 데이터베이스에 연결** 텍스트 상자 옆에 있는 단추를 선택합니다.
    1. **데이터 선택** 대화 상자에서 **Microsoft SQL Server 데이터베이스 파일**을 선택합니다.
    1. **항상 이 선택 사용** 확인란의 선택을 취소하고 **계속**을 선택합니다.
    1. **연결 속성** 대화 상자에서 **찾아보기**를 선택하고 다운로드한 *RestaurantScores.mdf* 파일을 선택합니다.
    1. **확인**을 선택합니다.
1. **테이블 이름** 드롭다운에서 **위반**을 선택합니다.
1. **예측할 열(레이블)** 드롭다운에서 **RiskCategory**를 선택합니다.
1. **입력 열(기능)** 드롭다운에서 선택된 기본 열 선택 항목인 **InspectionType** 및 **ViolationDescription**을 그대로 둡니다.
1. **학습** 링크를 선택하여 모델 작성기의 다음 단계로 이동합니다.

## <a name="train-the-model"></a>모델 학습

이 자습서에서 문제 분류 모델을 학습하는 데 사용되는 기계 학습 작업은 다중 클래스 분류입니다. 모델 학습 프로세스 중에 모델 작성기는 다른 다중 클래스 분류 알고리즘 및 설정을 통해 개별 모델을 학습하여 데이터 세트에 가장 적합한 모델을 찾습니다.

모델을 학습하는 데 필요한 시간은 데이터 양에 비례합니다. 모델 작성기는 데이터 소스의 크기에 따라 **학습 시간(초)** 의 기본값을 자동으로 선택합니다.

1. 모델 작성기는 **학습 시간(초)** 값을 10초로 설정하지만 이 값을 30초로 늘립니다. 더 긴 시간 동안 학습하면 모델 작성기가 최상의 모델을 찾아 더 많은 알고리즘과 매개 변수의 조합을 탐색할 수 있습니다.
1. **학습 시작**을 선택합니다.

    학습 프로세스 전체에서 진행률 데이터는 학습 단계의 `Progress` 섹션에 표시됩니다.

    - **상태**는 학습 프로세스의 완료 상태를 표시합니다.
    - **가장 높은 정확도** 는 모델 작성기가 현재까지 찾은 최고 성능 모델의 정확도를 표시합니다. 더 높은 정확도는 테스트 데이터에서 모델이 더 정확하게 예측된다는 것을 의미합니다.
    - **최상의 알고리즘** 은 모델 작성기가 현재까지 찾은 최고 성능 알고리즘의 이름을 표시합니다.
    - **마지막 알고리즘** 은 모델 작성기가 가장 최근에 학습하기 위해 사용한 알고리즘의 이름을 표시합니다.

1. 학습이 완료되면 **평가** 링크를 선택하여 다음 단계로 이동합니다.

## <a name="evaluate-the-model"></a>모델 평가

학습 단계의 결과는 최상의 성능을 가진 하나의 모델이 됩니다. 모델 작성기의 평가 단계에서 출력 섹션에는 **최상의 모델** 항목의 가장 성능이 좋은 모델에서 사용되는 알고리즘과 더불어 **최상의 모델 정확도**의 메트릭이 포함됩니다. 또한 탐색된 모델을 5개까지 포함하는 요약 테이블과 해당 메트릭이 표시됩니다.

정확도 메트릭에 만족하지 않는 경우 모델 정확도를 개선하기 위한 몇 가지 쉬운 방법은 모델을 학습하거나 더 많은 데이터를 사용하기 위한 시간을 늘리는 것입니다. 그렇지 않으면 **코드** 링크를 선택하여 모델 작성기의 최종 단계로 이동합니다.

## <a name="add-the-code-to-make-predictions"></a>코드를 추가하여 예측하기

학습 프로세스의 결과로 두 개의 프로젝트가 만들어집니다.

- RestaurantViolationsML.ConsoleApp: 모델 학습 및 샘플 소비 코드가 포함된 C# .NET Core 콘솔 애플리케이션입니다.
- RestaurantViolationsML.Model: 입력 및 출력 모델 데이터의 스키마를 정의하는 데이터 모델, 학습 중 가장 성능이 뛰어난 모델의 저장된 버전, 예측을 위한 `ConsumeModel`이라는 도우미 클래스를 포함하는 .NET Standard 클래스 라이브러리입니다.

1. 모델 작성기의 코드 단계에서 **프로젝트 추가**를 선택하여 자동 생성된 프로젝트를 솔루션에 추가합니다.
1. *RestaurantViolations* 프로젝트에서 *Program.cs* 파일을 엽니다.
1. *RestaurantViolationsML.Model* 프로젝트를 참조하도록 다음 using 문을 추가합니다.

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L2)]

1. 모델을 사용하여 새 데이터에 대해 예측을 수행하려면 `Main` 메서드 내부에 `ModelInput` 클래스의 새 인스턴스를 만듭니다. 위험 범주는 입력에 포함되지 않습니다. 모델에서 해당 범주를 예측하기 때문입니다.

    [!code-csharp [TestData](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L11-L15)]

1. `ConsumeModel` 클래스의 `Predict` 메서드를 사용합니다. `Predict` 메서드는 학습된 모델을 로드하고 모델에 대한 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만든 후 새 데이터에 대해 예측하는 데 사용합니다.

    [!code-csharp [Prediction](~/machinelearning-samples/samples/modelbuilder/MulticlassClassification_RestaurantViolations/RestaurantViolations/Program.cs#L17-L24)]

1. 애플리케이션을 실행합니다.

    프로그램에서 생성된 출력은 아래 코드 조각과 유사해야 합니다.

    ```bash
    Inspection Type: Complaint
    Violation Description: Inadequate sewage or wastewater disposal
    Risk Category: Moderate Risk
    ```

생성된 프로젝트를 나중에 다른 솔루션 내에서 참조해야 하는 경우 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 디렉터리 내에서 찾을 수 있습니다.

지금까지 모델 작성기를 사용하여 위생 위반 위험을 범주화하기 위한 기계 학습 모델을 성공적으로 빌드했습니다. [dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/MulticlassClassification_RestaurantViolations) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="additional-resources"></a>추가 자료

이 자습서에서 언급한 항목에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [모델 작성기 시나리오](../automate-training-with-model-builder.md#scenario)
- [다중 클래스 분류](../resources/glossary.md#multiclass-classification)
- [다중 클래스 분류 모델 메트릭](../resources/metrics.md#evaluation-metrics-for-multi-class-classification)

---
title: '자습서: 전이 학습을 사용한 자동화된 시각적 개체 검사'
description: 이 자습서에서는 전이 학습을 사용하여 이미지 검색 API로 ML.NET의 TensorFlow 딥 러닝 모델을 학습함으로써 콘크리트 표면 이미지를 금이 갔는지 여부로 분류하는 방법을 설명합니다.
author: luisquintanilla
ms.author: luquinta
ms.date: 12/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 2dfa3cdab9de47b55f7a3f73f0d6e9460390700c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "76920098"
---
# <a name="tutorial-automated-visual-inspection-using-transfer-learning-with-the-mlnet-image-classification-api"></a>자습서: ML.NET 이미지 분류 API와 함께 전이 학습을 사용한 자동화된 시각적 개체 검사

전이 학습, 사전 학습된 TensorFlow 모델 및 ML.NET 이미지 분류 API를 통해 사용자 지정 딥 러닝 모델을 학습하여 콘크리트 표면 이미지를 금이 갔는지 여부로 분류하는 방법을 알아봅니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
>
> - 문제 이해
> - ML.NET 이미지 분류 API에 대한 자세한 정보
> - 사전 학습된 모델 이해
> - 전이 학습을 사용하여 사용자 지정 TensorFlow 이미지 분류 모델 학습
> - 사용자 지정 모델을 사용하여 이미지 분류

## <a name="prerequisites"></a>사전 요구 사항

- “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 버전 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)

## <a name="image-classification-transfer-learning-sample-overview"></a>이미지 분류 전이 학습 샘플 개요

이 샘플은 사전 학습된 딥 러닝 TensorFlow 모델을 사용하여 이미지를 분류하는 C# .NET Core 콘솔 애플리케이션입니다. 이 샘플의 코드는 GitHub의 [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary)에서 찾을 수 있습니다.

## <a name="understand-the-problem"></a>문제 이해

이미지 분류는 컴퓨터 비전 문제입니다. 이미지 분류는 이미지를 입력으로 사용하고 규정된 클래스로 분류합니다. 이미지 분류를 유용하게 사용할 수 있는 몇 가지 시나리오는 다음과 같습니다.

- 얼굴 인식
- 감정 감지
- 의료 진단
- 랜드마크 검색

이 자습서에서는 사용자 지정 이미지 분류 모델을 학습하여 교량 상판의 자동화된 시각적 개체 검사를 통해 금이 간 구조물을 확인합니다.

## <a name="mlnet-image-classification-api"></a>ML.NET 이미지 분류 API

ML.NET은 이미지를 분류하는 다양한 방법을 제공합니다. 이 자습서에서는 이미지 분류 API를 사용하여 전이 학습을 적용합니다. 이미지 분류 API는 TensorFlow C++ API에 대한 C# 바인딩을 제공하는 하위 수준 라이브러리인 [TensorFlow.NET](https://github.com/SciSharp/TensorFlow.NET)를 사용합니다.

## <a name="what-is-transfer-learning"></a>전이 학습이란?

전이 학습은 한 가지 문제를 해결하면서 얻은 지식을 다른 관련 문제에 적용합니다.

딥 러닝 모델을 처음부터 학습하려면 여러 개의 매개 변수를 설정해야 하고 레이블이 지정된 대량 학습 데이터와 막대한 컴퓨팅 리소스(수백 시간의 GPU 시간)가 필요합니다. 전이 학습과 함께 사전 학습된 모델을 사용하면 학습 프로세스를 단축할 수 있습니다.

## <a name="training-process"></a>학습 프로세스

이미지 분류 API는 사전 학습된 TensorFlow 모델을 로드하여 학습 프로세스를 시작합니다. 학습 프로세스는 다음 두 단계로 구성됩니다.

1. 병목 상태 단계
2. 학습 단계

![학습 단계](./media/image-classification-api-transfer-learning/training.png)

### <a name="bottleneck-phase"></a>병목 상태 단계

병목 상태 단계에서는 학습 이미지 집합이 로드되고, 픽셀 값이 사전 학습된 모델의 고정 계층에 대한 입력 또는 기능으로 사용됩니다. 고정 계층에는 끝에서 두 번째 계층(비공식적으로 병목 상태 계층이라고 함)까지 신경망의 모든 계층이 포함됩니다. 이 계층에서는 학습이 발생하지 않고 작업이 통과되기 때문에 고정 계층이라고 합니다. 모델에서 각 클래스를 구분하는 데 도움이 되는 하위 수준 패턴이 컴퓨팅되는 곳이 고정 계층입니다. 계층 수가 많을수록 이 단계에서 사용되는 컴퓨팅이 증가합니다. 다행히 일회성 계산이므로 결과를 캐시했다가 후속 실행에서 다른 매개 변수로 실험할 때 사용할 수 있습니다.

### <a name="training-phase"></a>학습 단계

병목 상태 단계의 출력 값이 컴퓨팅되고 나면, 모델의 최종 계층을 다시 학습하기 위한 입력으로 사용됩니다. 이 프로세스는 반복되며 모델 매개 변수에 지정된 횟수만큼 실행됩니다. 실행할 때마다 손실과 정확도가 평가됩니다. 그런 다음, 손실 최소화 및 정확도 최대화를 목표로 해서 모델을 개선하기 위해 적절하게 조정됩니다. 학습이 완료되면 두 가지 모델 형식이 출력됩니다. 하나는 모델의 `.pb` 버전이고, 다른 하나는 모델의 ML.NET 직렬화된 `.zip` 버전입니다. ML.NET이 지원하는 환경에서 작업하는 경우 모델의 `.zip` 버전을 사용하는 것이 좋습니다. 그러나 ML.NET이 지원되지 않는 환경에서는 `.pb` 버전을 사용할 수 있습니다.

## <a name="understand-the-pretrained-model"></a>사전 학습된 모델 이해

이 자습서에서 사용되는 사전 학습 모델은 ResNet(Residual Network) v2 모델의 101 계층 변형입니다. 원본 모델은 이미지를 1000개 범주로 분류하도록 학습되었습니다. 모델은 224x224 크기의 이미지를 입력으로 사용하고, 모델이 학습된 각 클래스의 클래스 확률을 출력합니다. 이 모델의 일부는 두 클래스 간의 예측을 위해 사용자 지정 이미지를 사용하여 새 모델을 학습하는 데 사용됩니다.

## <a name="create-console-application"></a>콘솔 애플리케이션 만들기

이제 전이 학습과 이미지 분류 API에 대한 일반적인 사항을 파악했으므로 애플리케이션을 빌드하겠습니다.

1. “DeepLearning_ImageClassification_Binary”라는 **C# .NET Core 콘솔 애플리케이션**을 만듭니다.
1. **Microsoft.ML** 버전 **1.4.0** NuGet 패키지를 설치합니다.
    1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.
    1. 패키지 원본으로 "nuget.org"를 선택합니다.
    1. **찾아보기** 탭을 선택합니다.
    1. **시험판 포함** 확인란을 선택합니다.
    1. **Microsoft.ML**을 검색합니다.
    1. **설치** 단추를 선택합니다.
    1. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.
    1. **Microsoft.ML.Vision** 버전 **1.4.0**, **SciSharp.TensorFlow.Redist** 버전 **1.15.0** 및 **Microsoft.ML.ImageAnalytics** 버전 **1.4.0** NuGet 패키지에 이러한 단계를 반복합니다.

### <a name="prepare-and-understand-the-data"></a>데이터 준비 및 이해

> [!NOTE]
> 이 자습서의 데이터 세트는 Maguire, Marc, Dorafshan, Sattar 및 Thomas, Robert J., “SDNET2018: A concrete crack image dataset for machine learning applications”(기계 학습 애플리케이션의 콘크리트 금 이미지 데이터 세트)(2018)에서 가져온 것입니다. 모든 데이터 세트를 살펴봅니다. 논문 48입니다. [https://digitalcommons.usu.edu/all_datasets/48](https://digitalcommons.usu.edu/all_datasets/48 )

SDNET2018은 금이 간 콘크리트 구조물(교량 상판, 벽, 도로)과 금이 가지 않은 콘크리트 구조물에 대한 주석이 포함된 이미지 데이터 세트입니다.

![SDNET2018 데이터 세트 교량 상판 샘플](./media/image-classification-api-transfer-learning/sdnet2018decksamples.png)

데이터는 다음 세 개의 하위 디렉터리로 구성되어 있습니다.

- D에는 교량 상판 이미지가 있습니다.
- P에는 도로 이미지가 있습니다.
- W에 벽 이미지가 있습니다.

각 하위 디렉터리에는 접두사가 붙은 다음 두 개의 하위 디렉터리가 있습니다.

- C는 금이 간 표면에 사용되는 접두사입니다.
- U는 금이 가지 않은 표면에 사용되는 접두사입니다.

이 자습서에서는 교량 상판 이미지만 사용합니다.

1. [데이터 세트](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/assets.zip)를 다운로드하여 압축을 풉니다.
1. 프로젝트에서 데이터 세트 파일을 저장할 “assets”라는 디렉터리를 만듭니다.
1. 최근에 압축을 푼 디렉터리의 *CD* 및 *UD* 하위 디렉터리를 *assets* 디렉터리에 복사합니다.

### <a name="create-input-and-output-classes"></a>입력 및 출력 클래스 만들기

1. *Program.cs* 파일을 열고 파일의 맨 위에 있는 기존 `using` 문을 다음 문으로 바꿉니다.

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L1-L7)]

1. *Program.cs*의 `Program` 클래스 아래에 `ImageData`라는 클래스를 만듭니다. 이 클래스는 처음에 로드된 데이터를 나타내는 데 사용됩니다.

    [!code-csharp [ImageDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L137-L142)]

    `ImageData`에는 다음 속성이 있습니다.

    - `ImagePath`는 이미지가 저장된 정규화된 경로입니다.
    - `Label`은 이미지가 속하는 범주입니다. 예측할 값입니다.

1. 입력 및 출력 데이터의 클래스 만들기

    1. `ImageData` 클래스 아래에 있는 `ModelInput`이라는 새 클래스에서 입력 데이터의 스키마를 정의합니다.

        [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L144-L153)]

        `ModelInput`에는 다음 속성이 있습니다.

        - `Image`는 이미지의 `byte[]` 표현입니다. 모델을 학습하려면 이미지 데이터가 이 형식이어야 합니다.
        - `LabelAsKey`는 `Label`의 숫자 표현입니다.
        - `ImagePath`는 이미지가 저장된 정규화된 경로입니다.
        - `Label`은 이미지가 속하는 범주입니다. 예측할 값입니다.

        `Image` 및 `LabelAsKey`만 모델을 학습하고 예측하는 데 사용됩니다. `ImagePath` 및 `Label` 속성은 원본 이미지 파일 이름과 범주에 액세스하기 편리하도록 유지됩니다.

    1. 그런 다음, `ModelInput` 클래스 아래에 있는 `ModelOutput`이라는 새 클래스에서 출력 데이터의 스키마를 정의합니다.

        [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L155-L162)]

        `ModelOutput`에는 다음 속성이 있습니다.

        - `ImagePath`는 이미지가 저장된 정규화된 경로입니다.
        - `Label`은 이미지가 속하는 원래 범주입니다. 예측할 값입니다.
        - `PredictedLabel`은 모델에서 예측된 값입니다.

        `ModelInput`과 마찬가지로, 예측 작업에는 모델의 예측이 포함된 `PredictedLabel`만 있으면 됩니다. `ImagePath` 및 `Label` 속성은 원본 이미지 파일 이름과 범주에 액세스하기 편리하도록 유지됩니다.

### <a name="create-workspace-directory"></a>작업 영역 디렉터리 만들기

학습 및 유효성 검사 데이터가 자주 변경되지 않는 경우 추가 실행을 위해 계산된 병목 상태 값을 캐시하는 것이 좋습니다.

1. 프로젝트에서 *workspace*라는 새 디렉터리를 만들어 계산된 병목 상태 값과 모델의 `.pb` 버전을 저장합니다.

### <a name="define-paths-and-initialize-variables"></a>경로 정의 및 변수 초기화

1. `Main` 메서드에서 자산의 위치, 계산된 병목 상태 값, 모델의 `.pb` 버전을 정의합니다.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L15-L17)]

1. [MLContext](xref:Microsoft.ML.MLContext)의 새 인스턴스를 사용하여 `mlContext` 변수를 초기화합니다.

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L19)]

    [MLContext](xref:Microsoft.ML.MLContext) 클래스는 모든 ML.NET 작업의 시작점이며, mlContext를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다. 개념적으로 Entity Framework의 `DBContext`와 유사합니다.

## <a name="load-the-data"></a>데이터 로드

### <a name="create-data-loading-utility-method"></a>데이터 로드 유틸리티 메서드 만들기

이미지는 두 개의 하위 디렉터리에 저장됩니다. 데이터를 로드하기 전에 `ImageData` 개체 목록으로 형식을 지정해야 합니다. `Main` 메서드 아래에 `LoadImagesFromDirectory` 메서드를 만들면 됩니다.

```csharp
public static IEnumerable<ImageData> LoadImagesFromDirectory(string folder, bool useFolderNameAsLabel = true)
{

}
```

1. `LoadImagesDirectory` 안에 다음 코드를 추가하여 하위 디렉터리에서 파일 경로를 모두 가져옵니다.

    [!code-csharp [GetFiles](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L104-L105)]

1. `foreach` 문을 사용하여 각 파일을 반복합니다.

    ```csharp
    foreach (var file in files)
    {

    }
    ```

1. `foreach` 문 내에서 파일 확장명이 지원되는지 확인합니다. 이미지 분류 API는 JPEG 및 PNG 형식을 지원합니다.

    [!code-csharp [CheckExtension](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L109-L110)]

1. 파일의 레이블을 가져옵니다. `useFolderNameAsLabel` 매개 변수를 `true`로 설정하면 파일이 저장된 부모 디렉터리가 레이블로 사용됩니다. true로 설정하지 않으면 파일 이름의 접두사 또는 파일 이름 자체가 레이블이 됩니다.

    [!code-csharp [GetLabel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L112-L126)]

1. 마지막으로, `ModelInput`의 새 인스턴스를 만듭니다.

    [!code-csharp [CreateImageData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L128-L132)]

### <a name="prepare-the-data"></a>데이터 준비

1. `Main` 메서드로 돌아가서 `LoadFromDirectory` 유틸리티 메서드를 사용하여 학습에 사용할 이미지 목록을 가져옵니다.

    [!code-csharp [LoadImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L21)]

1. [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 메서드를 사용하여[`IDataView`](xref:Microsoft.ML.IDataView)에 이미지를 로드합니다.

    [!code-csharp [CreateIDataView](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L23)]

1. 디렉터리에서 읽어온 순서대로 데이터가 로드됩니다. 데이터의 균형을 조정하려면 [`ShuffleRows`](xref:Microsoft.ML.DataOperationsCatalog.ShuffleRows*) 메서드를 사용하여 순서를 섞습니다.

    [!code-csharp [ShuffleRows](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L25)]

1. 기계 학습 모델에서는 입력이 숫자 형식이어야 합니다. 따라서 학습 전에 데이터에서 몇 가지 전처리 작업을 수행해야 합니다. [`MapValueToKey`](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*) 및 `LoadRawImageBytes` 변환으로 구성된 [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)을 만듭니다. `MapValueToKey` 변환은 `Label` 열의 범주 값을 사용하여 숫자 `KeyType` 값으로 변환하고 `LabelAsKey`라는 새 열에 저장합니다. `LoadImages`는 `ImagePath` 열의 값을 `imageFolder` 매개 변수와 함께 사용하여 학습에 사용할 이미지를 로드합니다.

    [!code-csharp [PreprocessingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L27-L33)]

1. [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) 메서드를 사용하여 `preprocessingPipeline` [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)에 데이터를 적용합니다. 그 다음에 오는 [`Transform`](xref:Microsoft.ML.Data.TransformerChain`1.Transform*) 메서드가 전처리된 데이터를 포함하는 [`IDataView`](xref:Microsoft.ML.IDataView)를 반환합니다.

    [!code-csharp [PreprocessData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L35-L37)]

1. 모델을 학습하려면 유효성 검사 데이터 세트뿐만 아니라 학습 데이터 세트도 있어야 합니다. 학습 세트에서 모델이 학습됩니다. 보이지 않는 데이터의 예측 성능은 유효성 검사 세트에 대한 성능으로 측정됩니다. 성능 결과에 따라 모델이 배운 내용을 조정하여 개선합니다. 유효성 검사 세트는 원본 데이터 세트를 분할해서 얻거나, 이 용도로 이미 설정된 다른 소스에서 가져올 수 있습니다. 이 예제에서는 전처리된 데이터 세트를 학습, 유효성 검사 및 테스트 세트로 분할합니다.

    [!code-csharp [CreateDataSplits](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L39-L40)]

    위의 코드 샘플은 두 가지 분할 작업을 수행합니다. 먼저, 전처리된 데이터가 분할되어 70%는 학습에 사용되고 나머지 30%는 유효성 검사에 사용됩니다. 그런 다음 30% 유효성 검사 세트가 유효성 검사 및 테스트 세트로 다시 분할됩니다. 여기서 90%는 유효성 검사에 사용되고 10%는 테스트에 사용됩니다.

    시험 보기에 비유하면 이러한 데이터 파티션의 용도를 쉽게 파악할 수 있습니다. 시험 공부를 할 때는 노트, 책 또는 기타 리소스를 검토하여 시험에 나오는 개념을 파악합니다. 이때 학습 세트가 사용됩니다. 그 다음에는 지식을 검증하기 위해 모의 시험을 볼 수 있습니다. 이 용도에는 유효성 검사 세트가 유용합니다. 실제 시험을 보기 전에 개념을 잘 파악했는지 여부를 확인하려고 합니다. 결과에 따라 잘못 이해했거나 이해하지 못한 내용을 기록하고, 실제 시험을 위해 검토할 때 변경 내용을 통합합니다. 최종 단계로, 시험을 봅니다. 이때 테스트 세트가 사용됩니다. 시험에 나온 질문을 본 적이 없으며, 이제 학습 및 유효성 검사에서 배운 내용을 사용하여 해당 작업에 지식을 적용합니다.

1. 학습, 유효성 검사 및 테스트 데이터의 파티션에 해당 값을 할당합니다.

    [!code-csharp [CreateDatasets](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L42-L44)]

## <a name="define-the-training-pipeline"></a>학습 파이프라인 정의

모델 학습은 몇 가지 단계로 구성됩니다. 먼저, 이미지 분류 API를 사용하여 모델을 학습합니다. `MapKeyToValue` 변환을 사용하여 `PredictedLabel` 열의 인코드된 레이블이 원래 범주 값으로 다시 변환됩니다.

1. `ImageClassificationTrainer`에 대한 필수 및 선택적 매개 변수 집합을 저장할 새 변수를 만듭니다.

    [!code-csharp [ClassifierOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L46-L57)]

    `ImageClassificationTrainer`는 다음과 같은 몇 가지 선택적 매개 변수를 사용합니다.

    - `FeatureColumnName`은 모델의 입력으로 사용되는 열입니다.
    - `LabelColumnName`은 예측할 값의 열입니다.
    - `ValidationSet`는 유효성 검사 데이터를 포함하는 [`IDataView`](xref:Microsoft.ML.IDataView)입니다.
    - `Arch`는 사용할 사전 학습 모델 아키텍처를 정의합니다. 이 자습서에서는 ResNetv2 모델의 101 계층 변형을 사용합니다.
    - `MetricsCallback`은 학습 중에 진행 상황을 추적하기 위해 함수를 바인딩합니다.
    - `TestOnTrainSet`는 유효성 검사 세트가 없는 경우 학습 세트에서 성능을 측정하도록 모델에 지시합니다.
    - `ReuseTrainSetBottleneckCachedValues`는 병목 상태 단계에서 캐시된 값을 후속 실행에 사용할지 여부를 모델에 지시합니다. 병목 상태 단계는 일회성 통과 계산으로, 처음 수행할 때는 계산을 많이 사용합니다. 학습 데이터가 변경되지 않았으며 다른 Epoch 수나 일괄 처리 크기를 사용하여 실험하려는 경우 캐시된 값을 사용하면 모델을 학습하는 데 필요한 시간을 훨씬 줄일 수 있습니다.
    - `ReuseValidationSetBottleneckCachedValues`는 `ReuseTrainSetBottleneckCachedValues`와 비슷하지만, 이 경우에는 유효성 검사 데이터 세트에 사용됩니다.
    - `WorkspacePath`는 계산된 병목 상태 값과 모델의 `.pb` 버전을 저장할 디렉터리를 정의합니다.

1. `mapLabelEstimator` 및 `ImageClassificationTrainer`로 구성된 [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 학습 파이프라인을 정의합니다.

    [!code-csharp [TrainingPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L59-L60)]

1. [`Fit`](xref:Microsoft.ML.Data.EstimatorChain%601.Fit*) 메서드를 사용하여 모델을 학습합니다.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L62)]

## <a name="use-the-model"></a>모델 사용

이제 모델을 학습했으므로, 모델을 사용하여 이미지를 분류해야 합니다.

`Main` 메서드 아래에 예측 정보를 콘솔에 표시하는 `OutputPrediction`이라는 새 유틸리티 메서드를 만듭니다.

[!code-csharp [OuputPredictionMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L96-L100)]

### <a name="classify-a-single-image"></a>단일 이미지 분류

1. `Main` 메서드 아래에 단일 이미지 예측을 수행하고 출력하는 `ClassifySingleImage`라는 새 메서드를 추가합니다.

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. `ClassifySingleImage` 메서드 안에 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만듭니다. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스를 전달하고 예측하는 데 사용할 수 있는 편리한 API입니다.

    [!code-csharp [CreatePredictionEngine](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L73)]

1. 단일 `ModelInput` 인스턴스에 액세스하기 위해 [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) 메서드를 사용하여 `data` [`IDataView`](xref:Microsoft.ML.IDataView)를 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)로 변환하고 첫 번째 관찰을 가져옵니다.

    [!code-csharp [GetTestInputData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L75)]

1. [`Predict`](xref:Microsoft.ML.PredictionEngine%602.Predict*) 메서드를 사용하여 이미지를 분류합니다.

    [!code-csharp [MakeSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L77)]

1. `OutputPrediction` 메서드를 사용하여 예측을 콘솔에 출력합니다.

    [!code-csharp [OuputSinglePrediction](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L79-L80)]

1. `Main` 메서드 내에서 테스트 이미지 세트를 사용하여 `ClassifySingleImage`를 호출합니다.

    [!code-csharp [ClassifySingleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L64)]

### <a name="classify-multiple-images"></a>여러 이미지 분류

1. `ClassifySingleImage` 메서드 아래에 여러 이미지 예측을 수행하고 출력하는 `ClassifyImages`라는 새 메서드를 추가합니다.

    ```csharp
    public static void ClassifyImages(MLContext mlContext, IDataView data, ITransformer trainedModel)
    {

    }
    ```

1. [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) 메서드를 사용하여 예측을 포함하는 [`IDataView`](xref:Microsoft.ML.IDataView)를 만듭니다. `ClassifyImages` 메서드 내에 다음 코드를 추가합니다.

    [!code-csharp [MakeMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L85)]

1. 예측을 반복하기 위해 [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) 메서드를 사용하여 `predictionData` [`IDataView`](xref:Microsoft.ML.IDataView)를 [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)로 변환하고 처음 10개의 관찰을 가져옵니다.

    [!code-csharp [IEnumerablePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L87)]

1. 예측을 반복하고 예측의 원래 레이블과 예측 레이블을 출력합니다.

    [!code-csharp [OutputMultiplePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L89-L93)]

1. 최종 단계로, `Main` 메서드 내에서 테스트 이미지 세트를 사용하여 `ClassifyImages`를 호출합니다.

    [!code-csharp [ClassifyImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ImageClassification_Binary/DeepLearning_ImageClassification_Binary/Program.cs#L66)]

## <a name="run-the-application"></a>애플리케이션 실행

콘솔 앱을 실행합니다. 아래와 유사하게 출력되어야 합니다. 경고 또는 처리 메시지가 표시될 수 있지만, 이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다. 간단히 표시하기 위해 출력이 압축되었습니다.

**병목 상태 단계**

이미지가 `byte[]`로 로드되어 표시할 이미지 이름이 없으므로 이미지 이름 값이 출력되지 않습니다.

```test
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 279
Phase: Bottleneck Computation, Dataset used:      Train, Image Index: 280
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   1
Phase: Bottleneck Computation, Dataset used: Validation, Image Index:   2
```

**학습 단계**

```text
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  21, Accuracy:  0.6797619
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  22, Accuracy:  0.7642857
Phase: Training, Dataset used: Validation, Batch Processed Count:   6, Epoch:  23, Accuracy:  0.7916667
```

**이미지 분류 출력**

```text
Classifying single image
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD

Classifying multiple images
Image: 7001-220.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-163.jpg | Actual Value: UD | Predicted Value: UD
Image: 7001-210.jpg | Actual Value: UD | Predicted Value: UD
```

*7001-220.jpg* 이미지를 살펴보면 실제로 금이 가지 않은 것을 확인할 수 있습니다.

![예측에 사용되는 SDNET2018 데이터 세트 이미지](./media/image-classification-api-transfer-learning/predictedimage.jpg)

지금까지 이제 이미지 분류를 위한 딥 러닝 모델을 빌드했습니다.

### <a name="improve-the-model"></a>모델 개선

모델의 결과가 만족스럽지 않으면, 다음과 같은 방법을 사용하여 성능을 개선할 수 있습니다.

- **데이터 추가**: 모델이 더 많은 예제를 학습할수록 성능이 향상됩니다. 전체 [SDNET2018 데이터 세트](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?filename=2&article=1047&context=all_datasets&type=additional)를 다운로드하여 학습에 사용합니다.
- **데이터 보강**: 데이터에 다양성을 추가하는 일반적인 방법은 이미지에 다양한 변환(회전, 대칭 이동, 이동, 자르기)을 적용하여 데이터를 보강하는 것입니다. 이렇게 하면 모델이 학습할 수 있는 다양한 예제가 추가됩니다.
- **학습 시간 연장**: 학습 시간이 길수록 모델이 더 튜닝됩니다. Epoch 수를 늘리면 모델의 성능이 향상될 수 있습니다.
- **하이퍼 매개 변수로 실험**: 이 자습서에서 사용된 매개 변수 외에 다른 매개 변수를 튜닝하여 성능을 개선할 수 있습니다. 각 Epoch 후의 모델 업데이트 크기를 결정하는 학습 속도를 변경하면 성능이 향상될 수 있습니다.
- **다른 모델 아키텍처 사용**: 데이터 모양에 따라 기능 학습에 가장 적합한 모델이 다를 수 있습니다. 모델의 성능이 만족스럽지 않으면 아키텍처를 변경해 보세요.

### <a name="additional-resources"></a>추가 리소스

- [딥 러닝 및 기계 학습](/azure/machine-learning/service/concept-deep-learning-vs-machine-learning).

## <a name="next-steps"></a>다음 단계

이 자습서에서는 전이 학습, 사전 학습된 이미지 분류 TensorFlow 모델 및 ML.NET 이미지 분류 API를 통해 사용자 지정 딥 러닝 모델을 작성하여 콘크리트 표면 이미지를 금이 갔는지 여부로 분류하는 방법을 배웠습니다.

다음 자습서로 이동하여 자세히 알아보세요.

> [!div class="nextstepaction"]
> [개체 감지](object-detection-onnx.md)

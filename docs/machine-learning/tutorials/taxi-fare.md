---
title: ML.NET와 함께 회귀 학습자를 사용하여 가격 예측
description: ML.NET와 함께 회귀 학습자를 사용하여 가격을 예측합니다.
author: aditidugar
ms.author: johalex
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 811de96748fcc095e289905e73845c8cfdd8eea7
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58921080"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a>자습서: ML.NET와 함께 회귀 학습자를 사용하여 가격 예측

이 자습서에서는 ML.NET을 사용하여 가격(특히, 뉴욕시 택시 요금)을 예측하기 위한 [회귀 모델](../resources/glossary.md#regression)을 빌드하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 자습서와 관련 샘플에서는 현재 **ML.NET 버전 0.11**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
> * 문제 이해
> * 적절한 기계 학습 작업 선택
> * 데이터 준비 및 이해
> * 학습 파이프라인 만들기
> * 데이터 로드 및 변환
> * 학습 알고리즘 선택
> * 모델 학습
> * 모델 평가
> * 예측에 모델 사용

## <a name="prerequisites"></a>전제 조건

* “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

## <a name="understand-the-problem"></a>문제 이해

이 문제는 뉴욕시의 택시 요금 예측에 관한 것입니다. 처음에는 요금이 단순히 주행 거리에 따라 결정되는 것처럼 보일 수 있습니다. 그러나 뉴욕 택시 업체는 추가 승객 또는 현금 대신 신용 카드 결제 등의 다른 요소를 고려하여 다양한 금액을 청구합니다.

## <a name="select-the-appropriate-machine-learning-task"></a>적절한 기계 학습 작업 선택

데이터 집합의 기타 요인에 따라 실제 값인 가격 값을 예측하려고 합니다. 이렇게 하려면 [회귀](../resources/glossary.md#regression) 기계 학습 작업을 선택합니다.

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

1. Visual Studio 2017을 엽니다. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다. 그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다. **이름** 텍스트 상자에 “TaxiFarePrediction”을 입력하고 **확인** 단추를 선택합니다.

1. 프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합과 모델 파일을 저장합니다.

    **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다. “Data”를 입력하고 Enter 키를 누릅니다.

1. **Microsoft.ML** NuGet 패키지를 설치합니다.

    **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다. “nuget.org”를 패키지 소스로 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.

## <a name="prepare-and-understand-the-data"></a>데이터 준비 및 이해

1. [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 및 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 데이터 집합을 다운로드하여 이전 단계에서 만든 *Data* 폴더에 저장합니다. 이러한 데이터 집합을 사용하여 기계 학습 모델을 학습한 다음, 모델의 정확성을 평가합니다. 이러한 데이터 집합은 원래 [NYC TLC Taxi Trip 데이터 집합](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)에서 가져옵니다.

1. **솔루션 탐색기**에서 각 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.

1. **taxi-fare-train.csv** 데이터 집합을 열고 첫 번째 행에서 열 머리글을 확인합니다. 각 열을 살펴보세요. 데이터를 이해하고 **기능** 및 **레이블**로 사용할 열을 결정합니다.

**레이블**은 예측하려는 열의 식별자입니다. 식별된 **기능**은 레이블을 예측하는 데 사용됩니다.

제공된 데이터 집합에는 다음과 같은 열이 포함되어 있습니다.

* **vendor_id:** 택시 공급업체의 ID가 기능입니다.
* **rate_code:** 택시 이동의 요금 유형이 기능입니다.
* **passenger_count:** 이동하는 승객 수가 기능입니다.
* **trip_time_in_secs:** 이동에 걸린 시간입니다. 이동을 완료하기 전에 이동 요금을 예측하려고 합니다. 해당 시간에는 이동이 얼마나 길지 알지 못합니다. 따라서 이동 시간은 기능이 아니며 모델에서 이 열을 제외합니다.
* **trip_distance:** 이동 거리가 기능입니다.
* **payment_type:** 결제 방법(현금 또는 신용 카드)이 기능입니다.
* **fare_amount:** 지급한 총 택시 요금이 레이블입니다.

## <a name="create-data-classes"></a>데이터 클래스 만들기

입력 데이터 및 예측에 대한 클래스를 만듭니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.
1. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TaxiTrip.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.
1. 새 파일에 다음 `using` 지시문을 추가합니다.

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

기존 클래스 정의를 제거하고 두 개의 클래스 `TaxiTrip` 및 `TaxiTripFarePrediction`가 있는 다음 코드를 *TaxiTrip.cs* 파일에 추가합니다.

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` 은(는) 입력 데이터 클래스이며 각 데이터 집합 열의 정의를 포함합니다. <xref:Microsoft.ML.Data.LoadColumnAttribute> 특성을 사용하여 데이터 세트에서 소스 열의 인덱스를 지정합니다.

`TaxiTripFarePrediction` 클래스는 예측된 결과를 나타냅니다. 여기에는 `FareAmount`라는 단일 부동 필드가 있으며 `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> 특성이 적용되었습니다. 회귀 작업의 경우 **점수** 열에 예측된 레이블 값이 포함됩니다.

> [!NOTE]
> `float` 유형을 사용하여 입력 및 예측 데이터 클래스에서 부동 소수점 값을 나타냅니다.

## <a name="define-data-and-model-paths"></a>데이터 및 모델 경로 정의

*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

데이터 세트가 있는 파일 및 모델을 저장할 파일의 경로를 포함할 세 개의 필드를 만들어야 합니다.

* `_trainDataPath` 에는 모델을 학습하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.
* `_testDataPath` 에는 모델을 평가하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.
* `_modelPath` 에는 학습된 모델이 저장되는 파일에 대한 경로가 포함됩니다.

`Main` 메서드 바로 위에 다음 코드를 추가하여 해당 경로와 `_textLoader` 변수를 지정합니다.

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

ML.NET을 사용하여 모델을 작성하는 경우 먼저 ML 컨텍스트를 만듭니다. 이는 Entity Framework에서 `DbContext`를 사용하는 것과 개념이 비슷합니다. 환경은 예외 추적 및 로깅에 사용할 수 있는 기계 학습 작업의 컨텍스트를 제공합니다.

### <a name="initialize-variables-in-main"></a>Main에서 변수 초기화

`mlContext`라는 변수를 만들고 `MLContext`의 새 인스턴스로 초기화합니다.  `Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

`Train` 메서드를 호출하려면 `Main` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

`Train` 메서드는 다음 작업을 실행합니다.

* 데이터를 로드합니다.
* 데이터를 추출하고 변환합니다.
* 모델을 학습시킵니다.
* 모델을 .zip 파일로 저장합니다.
* 모델을 반환합니다.

`Train` 메서드는 모델을 학습시킵니다. 다음 코드를 사용하여 `Main` 바로 아래 메서드를 만듭니다.

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

`Train` 메서드에 두 개의 매개 변수를 전달합니다. 하나는 컨텍스트(`mlContext`)를 나타내는 `MLContext`이고, 다른 하나는 데이터 세트 경로(`dataPath`)를 나타내는 문자열입니다. 데이터 세트를 로드하기 위해 이 메서드를 다시 사용하겠습니다.

## <a name="load-and-transform-data"></a>데이터 로드 및 변환

[LoadFromTextFile 메서드](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)에 대해 `MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 데이터를 로드합니다. <xref:Microsoft.Data.DataView.IDataView>가 반환됩니다. 

`Transforms`의 입력 및 출력으로 사용되는 `DataView`는 `LINQ`의 `IEnumerable`과 비슷한 기본적인 데이터 파이프라인 형식입니다.

ML.NET에서 데이터는 SQL 뷰와 유사합니다. 지연 계산되고, 스키마화되며, 형식이 다릅니다. 개체가 파이프라인의 첫 번째 부분이며 데이터를 로드합니다. 이 자습서에서는 택시 주행 가격 정보가 포함된 데이터 세트를 로드합니다. 이 데이터 세트는 모델을 만들고 학습시키는 데 사용됩니다.

다음 코드를 `Train` 메서드의 첫 번째 줄로 추가합니다.

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

다음 단계에서는 `TaxiTrip` 클래스에 정의된 이름으로 해당 열을 참조합니다.

모델을 학습하고 평가할 때 기본적으로 **Label** 열의 값이 예측할 올바른 값으로 간주됩니다. 택시 요금을 예측하려면 `FareAmount` 열을 **Label** 열로 복사합니다. 이 작업을 수행하려면 `CopyColumnsEstimator` 변환 클래스를 사용하고 다음 코드를 추가합니다.

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

모델을 학습시키는 알고리즘에는 **숫자** 기능이 필요하므로 범주 데이터(`VendorId`, `RateCode` 및 `PaymentType`) 값을 숫자(`VendorIdEncoded`, `RateCodeEncoded` 및 `PaymentTypeEncoded`)로 변환해야 합니다. 이 작업을 수행하려면 각 열의 값마다 다른 숫자 키 값을 할당하는 Microsoft.ML.Transforms.OneHotEncodingTransformer> 변환 클래스를 사용하고 다음 코드를 추가합니다.

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

데이터 준비의 마지막 단계에서는 `mlContext.Transforms.Concatenate` 변환 클래스를 사용하여 모든 기능 열을 **Features** 열에 결합합니다. 기본적으로, 학습 알고리즘은 **Features** 열의 기능만 처리합니다. 다음 코드를 추가합니다.

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a>학습 알고리즘 선택

파이프라인에 데이터를 추가하고 데이터를 올바른 입력 형식으로 변환한 후 학습 알고리즘(**학습자**)을 선택합니다. 학습자는 모델을 학습시킵니다. 이 문제에 대해 **회귀** 작업을 선택했으므로 ML.NET에서 제공하는 회귀 학습자 중 하나인 `FastTreeRegressionTrainer` 학습자를 사용합니다.

`FastTreeRegressionTrainer` 학습 알고리즘은 그래디언트 부스팅을 활용합니다. 그라데이션 승격은 회귀 문제에 대한 기계 학습 기술입니다. 이 파이프라인은 각 회귀 트리를 단계적으로 빌드합니다. 미리 정의된 손실 함수를 사용하여 각 단계에서 오류를 측정한 다음, 수정합니다. 결과는 실제로 더 약한 예측 모델의 앙상블인 예측 모델입니다. 그라데이션 승격에 대한 자세한 내용은 [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)(승격된 의사 결정 트리 회귀)을 참조하세요.

`Train` 메서드에 다음 코드를 추가하여 이전 단계에서 추가한 데이터 처리 코드에 `FastTreeRegressionTrainer`를 추가합니다.

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a>모델 학습

마지막 단계에서는 모델을 학습시킵니다. 로드되고 변환된 데이터 세트를 기준으로 <xref:Microsoft.ML.Data.TransformerChain> 모델을 학습시킵니다. 추정기가 정의되면, 이미 로드된 학습 데이터를 제공하는 동시에 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>을 사용하여 모델을 학습시킵니다. 그러면 예측에 사용할 모델이 반환됩니다. `pipeline.Fit()` 은(는) 파이프라인을 학습시키고, 전달된 `DataView`에 따라 `Transformer`를 반환합니다. 이 문제가 발생할 때까지 실험이 실행되지 않습니다.

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

### <a name="save-the-model"></a>모델 저장

이 시점에는 기존 또는 새 .NET 애플리케이션에 통합할 수 있는 <xref:Microsoft.ML.Data.TransformerChain> 형식의 모델이 있습니다. 모델을 .zip 파일로 저장하려면 `Train` 메서드 끝에 다음 코드를 추가합니다.

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a>모델을 .zip 파일로 저장

다음 코드를 사용하여 `Train` 메서드 바로 뒤에 `SaveModelAsFile` 메서드를 만듭니다.

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

`SaveModelAsFile` 메서드는 다음 작업을 실행합니다.

* 모델을 .zip 파일로 저장합니다.

다른 애플리케이션에서 다시 사용하고 이용할 수 있도록 모델을 저장하는 메서드를 만들어야 합니다. `ITransformer`에는 `_modelPath` 전역 필드를 사용하는 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 메서드와 <xref:System.IO.Stream>이 있습니다. 이 파일을 zip 파일로 저장하려고 하기 때문에 `SaveTo` 메서드를 호출하기 직전에 `FileStream`을 만들겠습니다. `SaveModelAsFile` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

다음 코드를 사용해서 `_modelPath`가 포함된 콘솔 메시지를 작성하여 파일이 작성된 위치를 표시할 수도 있습니다.

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a>모델 평가

평가는 모델이 레이블 값을 얼마나 잘 예측하는지 확인하는 프로세스입니다. 모델을 학습될 때 사용하지 않은 데이터를 기반으로 모델이 적절한 예측을 하는 것이 중요합니다. 이를 수행하는 한 가지 방법은 이 자습서에서 한 것처럼 데이터를 학습 및 테스트 데이터 집합으로 분할하는 것입니다. 학습 데이터를 기반으로 모델을 학습시켰으므로 테스트 데이터에서 모델이 얼마나 잘 작동하는지 확인할 수 있습니다.

`Evaluate` 메서드는 모델을 평가합니다. 해당 메서드를 만들려면 `Train` 메서드 아래에 다음 코드를 추가합니다.

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```
`Evaluate` 메서드는 다음 작업을 실행합니다.

* 테스트 데이터 세트를 로드합니다.
* 회귀 평가자를 만듭니다.
* 모델을 평가하고 메트릭을 만듭니다.
* 메트릭을 표시합니다.

다음 코드를 사용하여 `Train` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

`MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 테스트 데이터 세트를 로드합니다. 이 데이터 세트를 품질 검사로 사용하여 모델을 평가할 수 있습니다. `Evaluate` 메서드에 다음 코드를 추가합니다.

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

다음으로, 기계 학습 `model` 매개 변수(변환기)를 사용하여 기능을 입력하고 예측을 반환합니다. `Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

`RegressionContext.Evaluate` 메서드는 지정된 데이터 세트를 사용하여 `PredictionModel`에 대한 품질 메트릭을 계산합니다. 회귀 평가자가 계산한 전체 메트릭이 포함된 <xref:Microsoft.ML.Data.RegressionMetrics> 개체를 반환합니다. 모델의 품질을 확인하기 위해 이러한 메트릭을 표시하려면 먼저 메트릭을 가져와야 합니다. `Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

다음 코드를 추가하여 모델을 평가하고 평가 메트릭을 생성합니다.

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

[RSquared](../resources/glossary.md#coefficient-of-determination)는 회귀 모델의 다른 평가 메트릭입니다. RSquared에서는 0과 1 사이의 값을 사용합니다. 해당 값이 1에 가까울수록 더 나은 모델입니다. RSquared 값을 표시하려면 `Evaluate` 메서드에 다음 코드를 추가합니다.

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse)는 회귀 모델의 평가 메트릭 중 하나입니다. RMS가 낮을수록 더 나은 모델입니다. RMS 값을 표시하려면 `Evaluate` 메서드에 다음 코드를 추가합니다.

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a>예측에 모델 사용


## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a>모델 및 단일 댓글을 사용하여 테스트 데이터 결과를 예측합니다.

다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `TestSinglePrediction` 메서드를 만듭니다.

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

`TestSinglePrediction` 메서드는 다음 작업을 실행합니다.

* 테스트 데이터의 단일 댓글을 만듭니다.
* 테스트 데이터를 기준으로 요금 금액을 예측합니다.
* 보고를 위해 테스트 데이터 및 예측을 결합합니다.
* 예측 결과를 표시합니다.

다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

저장한 zip 파일에서 모델을 로드하려고 하기 때문에 `Load` 메서드를 호출하기 직전에 `FileStream`을 만들겠습니다. `TestSinglePrediction` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

`model`은 여러 데이터 행에서 작동하는 `transformer`이지만, 일반적인 프로덕션 시나리오에서는 개별 예제에 대한 예측이 필요합니다. <xref:Microsoft.ML.PredictionEngine%602>은 `CreatePredictionEngine` 메서드에서 반환되는 래퍼입니다. 다음 코드를 추가하여 `PredictionEngine`을 `TestSinglePrediction` 메서드의 다음 줄로 만듭니다.

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
이 자습서에서는 이 클래스 내에서 하나의 테스트 이동을 사용합니다. 나중에 이 모델로 실험할 다른 시나리오를 추가할 수 있습니다. `TaxiTrip` 인스턴스를 만들어 주행을 추가하여 `TestSinglePrediction` 메서드에서 학습된 모델의 비용 예측을 테스트합니다.

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 해당 메서드를 사용하여 택시 주행 데이터의 단일 인스턴스를 기준으로 운임을 예측할 수 있습니다. 예측을 가져오려면 데이터에 대해 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>을 사용합니다. 입력 데이터는 문자열이고 모델은 기능화를 포함합니다. 파이프라인은 학습 및 예측 중에 동기화됩니다. 특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

지정한 주행의 예상 운임을 표시하려면 `TestSinglePrediction` 메서드에 다음 코드를 추가합니다.

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

프로그램을 실행하여 테스트 사례에 대해 예측된 택시 요금을 확인합니다.

지금까지 택시 요금 예측을 위한 기계 학습 모델을 성공적으로 빌드하고, 정확도를 평가하고, 예측하는 데 사용했습니다. [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="next-steps"></a>다음 단계

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.
> [!div class="checklist"]
> * 문제 이해
> * 적절한 기계 학습 작업 선택
> * 데이터 준비 및 이해
> * 학습 파이프라인 만들기
> * 데이터 로드 및 변환
> * 학습 알고리즘 선택
> * 모델 학습
> * 모델 평가
> * 예측에 모델 사용

다음 자습서로 이동하여 자세히 알아보세요.
> [!div class="nextstepaction"]
> [아이리스 클러스터링](iris-clustering.md)

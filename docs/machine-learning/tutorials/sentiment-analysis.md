---
title: 감정 분석 이진 분류 시나리오에서 ML.NET 사용
description: 감정 예측을 통해 적절한 작업을 수행하는 방법을 이해하기 위해 이진 분류 시나리오에서 ML.NET을 사용하는 방법을 살펴봅니다.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: e88a85b96c1e5d33d748332991cb9480222a9c66
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612097"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>자습서: 감정 분석 이진 분류 시나리오에서 ML.NET 사용

이 샘플 자습서에서는 Visual Studio 2017에서 C#을 사용하는 .NET Core 콘솔 애플리케이션을 통해 긍정적 또는 부정적 감정을 예측하기 위해 ML.NET을 사용하여 감정 분류자를 만드는 방법에 대해 설명합니다. 기계 학습 환경에서 이 예측 유형을 이진 분류라고 합니다.

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 자습서와 관련 샘플에서는 현재 **ML.NET 버전 0.11**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
> * 문제 이해
> * 적절한 기계 학습 알고리즘 선택
> * 데이터 준비
> * 데이터 변환
> * 모델 학습
> * 모델 평가
> * 학습된 모델을 통해 예측
> * 로드된 모델을 통해 배포 및 예측

## <a name="sentiment-analysis-sample-overview"></a>감정 분석 샘플 개요

샘플은 ML.NET을 사용하여 감정을 긍정적 또는 부정적으로 분류하고 예측하는 모델을 학습시키는 콘솔 앱입니다. Yelp 감정 데이터 세트는 UCI(University of California, Irvine)에서 제공되고 학습 데이터 세트와 테스트 데이터 세트로 분할됩니다. 샘플은 품질 분석을 위해 테스트 데이터 세트를 사용하여 모델을 평가합니다.

[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="prerequisites"></a>전제 조건

* “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017).

* [UCI Sentiment Labeled Sentences 데이터 세트 zip 파일](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a>기계 학습 워크플로

이 자습서는 프로세스가 체계적으로 이동할 수 있도록 하는 기계 학습 워크플로를 따릅니다.

워크플로 단계는 다음과 같습니다.

1. **문제 이해**
2. **데이터 준비**
   * **데이터 로드**
   * **기능 추출(데이터 변환)**
3. **빌드 및 학습**
   * **모델 학습**
   * **모델 평가**
4. **모델 배포**
   * **예측 모델 사용**

### <a name="understand-the-problem"></a>문제 이해

먼저 문제를 이해해야 하므로 모델 빌드 및 학습을 지원할 수 있는 부분으로 문제를 구분할 수 있습니다. 문제를 구분하면 결과를 예측하고 평가할 수 있습니다.

이 자습서의 문제는 들어오는 웹 사이트 댓글 감정을 이해하여 적절한 작업을 수행하는 것입니다.

모델 학습에 사용할 데이터의 감정 텍스트와 감정 값 및 평가 후 조작에 사용할 수 있는 예측 감정 값으로 문제를 구분할 수 있습니다.

그런 다음, 기계 학습 작업 선택에 도움이 되는 감정을 **확인**해야 합니다.

## <a name="select-the-appropriate-machine-learning-algorithm"></a>적절한 기계 학습 알고리즘 선택

이 문제에서 다음 사실을 알 수 있습니다.

학습 데이터: 웹 사이트 댓글은 긍정적(1) 또는 부정적(0)(**감정**)일 수 있습니다.

다음 예제와 같이 새로운 웹 사이트 댓글의 **감정**을 긍정적 또는 부정적으로 예측합니다.

* 종업원들이 매우 마음에 듭니다. 정말 최고입니다.
* 여기 수프는 최악입니다.

이 시나리오에서는 분류 기계 학습 알고리즘이 가장 적합합니다.

### <a name="about-the-classification-algorithm"></a>분류 알고리즘 정보

분류는 데이터를 사용하여 데이터 항목 또는 행의 범주, 형식 또는 클래스를 **확인**하는 기계 학습 알고리즘입니다. 예를 들어 분류를 사용하여 다음을 수행할 수 있습니다.

* 감정을 긍정적 또는 부정적으로 식별합니다.
* 전자 메일을 스팸, 정크 또는 정상으로 분류합니다.
* 환자의 실험실 샘플이 종양성인지 확인합니다.
* 영업 캠페인에 응답하는 고객의 성향을 기준으로 고객을 분류합니다.

일반적으로 분류 알고리즘은 다음 형식 중 하나입니다.

* 이진: A 또는 B.
* 다중 클래스: 단일 모델을 사용하여 예측할 수 있는 여러 범주.

웹 사이트 댓글은 긍정적 또는 부정적으로 분류해야 하므로 이진 분류 알고리즘을 사용합니다.

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

1. Visual Studio 2017을 엽니다. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다. 그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다. **이름** 텍스트 상자에 “SentimentAnalysis”를 입력한 다음, **확인** 단추를 선택합니다.

2. 프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합 파일을 저장합니다.

    **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다. “Data”를 입력하고 Enter 키를 누릅니다.

3. **Microsoft.ML NuGet 패키지**를 설치합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다. “nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.

### <a name="prepare-your-data"></a>데이터 준비

1. [UCI Sentiment Labeled Sentences 데이터 세트 zip 파일(다음 참고의 인용 참조)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)을 다운로드하여 압축을 풉니다.

2. 만든 *Data* 디렉터리에 `yelp_labelled.txt` 파일을 복사합니다.

> [!NOTE]
> 이 자습서에서 사용하는 데이터 세트는 ‘From Group to Individual Labels using Deep Features’(Kotzias 외, KDD 2015)에서 제공되고 UCI Machine Learning Repository(Dua, D. 및 Karra Taniskidou, E. (2017))에서 호스트됩니다. UCI Machine Learning Repository[http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

3. 솔루션 탐색기에서 `yelp_labeled.txt` 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.

### <a name="create-classes-and-define-paths"></a>클래스 만들기 및 경로 정의

*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

최근에 다운로드한 데이터 세트 파일 경로 및 저장된 모델 파일 경로를 포함할 두 개의 전역 필드를 만들어야 합니다.

* `_dataPath`에는 모델을 학습시키는 데 사용되는 데이터 세트의 경로가 포함됩니다.
* `_modelPath`에는 학습된 모델이 저장되는 경로가 포함됩니다.

`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로를 지정합니다.

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다. 새 클래스를 프로젝트에 추가합니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.

1. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.

    *SentimentData.cs* 파일이 코드 편집기에서 열립니다. 다음 `using` 문을 *SentimentData.cs*의 맨 위에 추가합니다.

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

기존 클래스 정의를 제거하고 두 개의 클래스 `SentimentData` 및 `SentimentPrediction`가 있는 다음 코드를 *SentimentData.cs* 파일에 추가합니다.

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

입력 데이터 세트 클래스인 `SentimentData`에는 댓글에 대한 `string`(`SentimentText`) 및 긍정적/부정적 감정 값을 나타내는 `bool`(`Sentiment`)이 포함됩니다. 두 필드에 모두 <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> 특성이 연결되어 있습니다. 이 특성은 데이터 파일의 각 필드 순서를 설명합니다.  또한 `Sentiment` 속성에는 필드를 `Label` 필드로 지정하는 <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A>가 있습니다. `SentimentPrediction`은 모델이 학습된 후 예측에 사용되는 클래스입니다. 여기에는 단일 부울(`Sentiment`)과 `PredictedLabel` `ColumnName` 특성이 포함됩니다. `Label`은 세트를 만들고 학습시키는 데 사용되며 분할된 테스트 데이터 세트와 함께 모델을 평가하는 데도 사용됩니다. `PredictedLabel`은 예측 및 평가 중에 사용됩니다. 평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.

ML .NET를 사용하여 모델을 작성하는 경우 먼저 <xref:Microsoft.ML.MLContext>를 만듭니다. `MLContext`는 Entity Framework에서 `DbContext`를 사용하는 것과 비슷한 개념입니다. 환경은 예외 추적 및 로깅에 사용할 수 있는 ML 작업의 컨텍스트를 제공합니다.

### <a name="initialize-variables-in-main"></a>Main에서 변수 초기화

`mlContext`라는 변수를 만들고 `MLContext`의 새 인스턴스로 초기화합니다.  `Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

`Main` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.

[!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

`LoadData` 메서드는 다음 작업을 실행합니다.

* 데이터를 로드합니다.
* 로드된 데이터 세트를 학습 및 테스트 세트로 분할합니다.
* 분할된 학습 및 테스트 데이터 세트를 반환합니다.

다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `LoadData` 메서드를 만듭니다.

```csharp
public static TrainCatalogBase.TrainTestData LoadData(MLContext mlContext)
{

}
```

## <a name="load-the-data"></a>데이터 로드

이전에 만든 `SentimentData` 데이터 모델 유형이 데이터 세트 스키마와 일치하므로 [LoadFromTextFile 메서드](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)에 대해 `MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 초기화, 매핑 및 데이터 세트 로드를 하나의 코드 줄로 결합할 수 있습니다. <xref:Microsoft.Data.DataView.IDataView>가 반환됩니다.

`Transforms`의 입력 및 출력으로 사용되는 `DataView`는 `LINQ`의 `IEnumerable`과 비슷한 기본적인 데이터 파이프라인 형식입니다.

ML.NET에서 데이터는 SQL 뷰와 유사합니다. 지연 계산되고, 스키마화되며, 형식이 다릅니다. 개체가 파이프라인의 첫 번째 부분이며 데이터를 로드합니다. 이 자습서에서 개체는 댓글과 해당하는 악의적 또는 비악의적 감정을 포함하는 데이터 세트를 로드합니다. 이 데이터 세트는 모델을 만들고 학습시키는 데 사용됩니다.

다음 코드를 `LoadData` 메서드의 첫 번째 줄로 추가합니다.

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a>데이터 세트를 모델 학습 및 테스트용으로 분할

다음으로, 모델을 학습시키기 위한 학습 데이터 세트와 모델을 평가하기 위한 테스트 데이터 세트가 둘 다 필요합니다. <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A>를 래핑하는 `MLContext.BinaryClassification.TrainTestSplit`를 사용하여 로드된 데이터 세트를 학습 및 테스트 데이터 세트로 분할하고 <xref:Microsoft.ML.TrainCatalogBase.TrainTestData> 내부에서 분할된 데이터 세트를 반환합니다. `testFraction` 매개 변수로 테스트 세트의 일부 데이터를 지정할 수 있습니다. 기본값은 10%이지만, 이 경우에는 20%를 사용하여 평가에 더 많은 데이터를 사용합니다.

로드된 데이터를 필요한 데이터 세트로 분할하려면 `LoadData` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

`splitDataView` 메서드의 끝에 `LoadData`를 반환합니다.

[!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a>모델 빌드 및 학습

`BuildAndTrainModel` 메서드에 다음 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

`BuildAndTrainModel` 메서드는 다음 작업을 실행합니다.

* 데이터를 추출하고 변환합니다.
* 모델을 학습시킵니다.
* 테스트 데이터를 기반으로 감정을 예측합니다.
* 모델을 반환합니다.

다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `BuildAndTrainModel` 메서드를 만듭니다.

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

두 개의 매개 변수가 Train 메서드에 전달됩니다. 하나는 컨텍스트(`mlContext`)를 나타내는 `MLContext`이고, 다른 하나는 학습 데이터 세트(`splitTrainSet`)를 나타내는 `IDataView`입니다.

## <a name="extract-and-transform-the-data"></a>데이터 추출 및 변환

데이터 전처리 및 정리는 데이터 세트가 기계 학습에 효과적으로 사용되기 전에 수행되는 중요한 작업입니다. 원시 데이터는 종종 정리되지 않고 불안정하며 값이 누락될 수 있습니다. 이러한 모델링 작업 없이 데이터를 사용하면 잘못된 결과를 얻을 수 있습니다.

ML.NET의 변환 파이프라인은 학습 또는 테스트 전에 데이터에 적용되는 사용자 지정 변환 세트로 구성됩니다. 변환의 기본 목적은 데이터 [기능화](../resources/glossary.md#feature-engineering)입니다. 기계 학습 알고리즘은 [기능화된](../resources/glossary.md#feature) 데이터를 인식하므로 다음 단계는 텍스트 데이터를 ML 알고리즘이 인식하는 형식으로 변환하는 것입니다. 해당 형식은 [숫자 벡터](../resources/glossary.md#numerical-feature-vector)입니다.

다음으로, 텍스트(`SentimentText`) 열을 기계 학습 알고리즘에서 사용되는 `Features`라는 숫자 벡터로 기능화하는 `mlContext.Transforms.Text.FeaturizeText`를 호출합니다. 이는 실제로 파이프라인이 될 <xref:Microsoft.ML.Data.EstimatorChain%601>을 반환하는 래퍼 호출입니다. 이 학습자를 `EstimatorChain`에 추가할 때 `pipeline`으로 이름을 지정합니다. 아래 코드를 다음 코드 줄로 추가합니다.

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> ML.NET 버전 0.10은 변환 매개 변수의 순서를 변경했습니다. 이렇게 하면 애플리케이션을 실행하고 모델을 빌드할 때까지 오류가 발생하지 않습니다. 이전 코드 조각에 설명된 것처럼 변환에 매개 변수 이름을 사용합니다.

이것이 전처리/기능화 단계입니다. ML.NET에서 사용 가능한 추가 구성 요소를 사용하면 모델에서 더 나은 결과를 얻을 수 있습니다.

## <a name="choose-a-learning-algorithm"></a>학습 알고리즘 선택

학습자를 추가하려면 <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> 개체를 반환하는 `mlContext.BinaryClassification.Trainers.FastTree` 래퍼 메서드를 호출합니다. 이 개체는 이 파이프라인에서 사용할 의사 결정 트리 학습자입니다. `FastTreeBinaryClassificationTrainer`는 `pipeline`에 추가되며, 기록 데이터에서 학습할 기능화된 `SentimentText`(`Features`) 및 `Label` 입력 매개 변수를 수락합니다.

`BuildAndTrainModel` 메서드에 다음 코드를 추가합니다.

[!code-csharp[FastTreeBinaryClassificationTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a>모델 학습

로드되고 변환된 데이터 세트를 기반으로 <xref:Microsoft.ML.Data.TransformerChain%601> 모델을 학습시킵니다. 추정기가 정의된 후, 이미 로드된 학습 데이터를 제공하는 동시에 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> 메서드를 사용하여 모델을 학습시킵니다. 그러면 예측에 사용할 모델이 반환됩니다. `pipeline.Fit()`은 파이프라인을 학습시키고, 전달된 `DataView`에 따라 `Transformer`를 반환합니다. `.Fit()` 메서드가 실행될 때까지 실험이 실행되지 않습니다.

`BuildAndTrainModel` 메서드에 다음 코드를 추가합니다.

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>평가에 사용하기 위해 학습된 모델 저장 및 반환

이 시점에는 기존 또는 새 .NET 애플리케이션에 통합할 수 있는 <xref:Microsoft.ML.Data.TransformerChain%601> 형식의 모델이 있습니다. `BuildAndTrainModel` 메서드의 끝에 모델을 반환합니다.

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a>모델 평가

이제 모델을 만들고 학습시켰으므로 품질 보증 및 유효성 검사를 위해 다른 데이터 세트를 사용하여 평가해야 합니다. `Evaluate` 메서드에서는 `BuildAndTrainModel`에서 만들어진 모델을 전달하여 평가합니다. 다음 코드와 같이 `BuildAndTrainModel` 바로 뒤에 `Evaluate` 메서드를 만듭니다.

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

`Evaluate` 메서드는 다음 작업을 실행합니다.

* 테스트 데이터 세트를 로드합니다.
* binaryclassification 평가기를 만듭니다.
* 모델을 평가하고 메트릭을 만듭니다.
* 메트릭을 표시합니다.

다음 코드를 사용하여 `Train` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

다음으로, 기계 학습 `model` 매개 변수(변환기)와 `splitTestSet` 매개 변수를 사용하여 기능을 입력하고 예측을 반환합니다. `Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

`mlContext.BinaryClassification.Evaluate` 메서드는 지정된 데이터 세트를 사용하여 `PredictionModel`에 대한 품질 메트릭을 계산합니다. 이진 분류 평가자가 계산한 전체 메트릭이 포함된 <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> 개체를 반환합니다. 모델의 품질을 확인하기 위해 이러한 메트릭을 표시하려면 먼저 메트릭을 가져와야 합니다. `Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>모델 유효성 검사를 위해 메트릭 표시

다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

반환하기 전에 모델을 .zip 파일로 저장하려면 `SaveModelAsFile` 메서드를 호출하는 아래 코드를 `Evaluate`에 다음 줄로 추가합니다.

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a>모델을 .zip 파일로 저장

다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `SaveModelAsFile` 메서드를 만듭니다.

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

`SaveModelAsFile` 메서드는 다음 작업을 실행합니다.

* 모델을 .zip 파일로 저장합니다.

다음으로, 다른 애플리케이션에서 다시 사용하고 이용할 수 있도록 모델을 저장하는 메서드를 만듭니다. `ITransformer`에는 `_modelPath` 전역 필드를 사용하는 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 메서드와 <xref:System.IO.Stream>이 있습니다. 이 파일을 zip 파일로 저장하기 위해 `SaveTo` 메서드를 호출하기 직전에 `FileStream`을 만들겠습니다. `SaveModelAsFile` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

다음 코드를 사용해서 `_modelPath`가 포함된 콘솔 메시지를 작성하여 파일이 작성된 위치를 표시할 수도 있습니다.

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a>저장된 모델을 사용하여 테스트 데이터 결과 예측

다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `UseModelWithSingleItem` 메서드를 만듭니다.

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

`UseModelWithSingleItem` 메서드는 다음 작업을 실행합니다.

* 테스트 데이터의 단일 댓글을 만듭니다.
* 테스트 데이터를 기반으로 감정을 예측합니다.
* 보고를 위해 테스트 데이터 및 예측을 결합합니다.
* 예측 결과를 표시합니다.

다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.

[!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

`model`은 여러 데이터 행에서 작동하는 `transformer`이지만, 일반적인 프로덕션 시나리오에서는 개별 예제에 대한 예측이 필요합니다. <xref:Microsoft.ML.PredictionEngine%602>은 `CreatePredictionEngine` 메서드에서 반환되는 래퍼입니다. 다음 코드를 추가하여 `PredictionEngine`을 `Predict` 메서드의 첫째 줄로 만듭니다.

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

`SentimentData` 인스턴스를 만들어 댓글을 추가하여 `Predict` 메서드에서 학습된 모델의 예측을 테스트합니다.

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 해당 메서드를 사용하여 댓글 데이터의 단일 인스턴스에서 긍정적 또는 부정적 감정을 예측할 수 있습니다. 예측을 가져오려면 데이터에 대해 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>을 사용합니다. 입력 데이터는 문자열이고 모델은 기능화를 포함합니다. 파이프라인은 학습 및 예측 중에 동기화됩니다. 특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a>모델 사용: 예측

결과를 공유하고 이에 따라 작업을 수행하기 위해 `SentimentText` 및 해당 감정 예측을 표시합니다. 이것을 반환된 데이터를 운영 정책의 일부로 사용하는 연산화라고 합니다. 다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과 표시를 만듭니다.

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a>로드된 모델을 통해 배포 및 예측

다음 코드를 사용하여 `SaveModelAsFile` 메서드 바로 앞에 `UseLoadedModelWithBatchItems` 메서드를 만듭니다.

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

`UseLoadedModelWithBatchItems` 메서드는 다음 작업을 실행합니다.

* 일괄 처리 테스트 데이터를 만듭니다.
* 테스트 데이터를 기반으로 감정을 예측합니다.
* 보고를 위해 테스트 데이터 및 예측을 결합합니다.
* 예측 결과를 표시합니다.

다음 코드를 사용하여 `UseModelWithSingleItem` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.

[!code-csharp[CallPredictModelLoaded](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

몇몇 댓글을 추가하여 `UseLoadedModelWithBatchItems` 메서드에서 학습된 모델의 예측을 테스트합니다.

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

모델 로드

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

이제 모델이 있으므로 해당 모델을 통해 <xref:Microsoft.ML.ITransformer.Transform%2A> 메서드를 사용하여 댓글 데이터의 악의적 또는 비악의적 감정을 예측할 수 있습니다. 예측을 가져오려면 새 데이터에서 `Predict`를 사용합니다. 입력 데이터는 문자열이고 모델은 기능화를 포함합니다. 파이프라인은 학습 및 예측 중에 동기화됩니다. 특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다. 예측을 위해 `UseLoadedModelWithBatchItems` 메서드에 다음 코드를 추가합니다.

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a>예측에 로드된 모델 사용

결과를 공유하고 이에 따라 작업을 수행하기 위해 `SentimentText` 및 해당 감정 예측을 표시합니다. 이것을 반환된 데이터를 운영 정책의 일부로 사용하는 연산화라고 합니다. 다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과에 대한 헤더를 만듭니다.

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

예측 결과를 표시하기 전에 감정과 예측을 결합하여 예측된 감정이 있는 원래 주석을 확인합니다. 다음 코드는 <xref:System.Linq.Enumerable.Zip%2A> 메서드를 사용하여 작업이 수행되도록 하므로, 다음으로 해당 코드를 추가합니다.

[!code-csharp[BuildTuples](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

이제 `SentimentText` 및 `Sentiment`를 클래스로 결합했으므로 <xref:System.Console.WriteLine?displayProperty=nameWithType> 메서드를 사용하여 결과를 표시할 수 있습니다.

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

유추된 튜플 요소 이름은 C# 7.1의 새로운 기능이고 프로젝트의 기본 언어 버전은 C# 7.0이므로 언어 버전을 C# 7.1 이상으로 변경해야 합니다.
이 작업을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **빌드** 탭을 선택하고 **고급** 단추를 선택합니다. 드롭다운에서 **C# 7.1**(또는 이상 버전)을 선택합니다. **확인** 단추를 선택합니다.

## <a name="results"></a>결과

다음과 같은 결과가 나타나야 합니다. 파이프라인이 처리할 때 메시지를 표시합니다. 경고 또는 메시지 처리를 확인할 수 있습니다. 이해하기 쉽도록 이러한 결과는 다음 결과에서 제거되었습니다.

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

지금까지 이제 메시지 감정을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.

성공한 모델 빌드하는 것은 반복적인 프로세스입니다. 자습서에서는 작은 데이터 세트를 사용하여 빠른 모델 학습을 제공하므로 이 모델은 초기 품질이 좋지 않습니다. 모델 품질에 만족하지 않는 경우 더 큰 학습 데이터 세트를 제공하거나 각 알고리즘에 대한 다양한 하이퍼 매개 변수와 함께 다양한 학습 알고리즘을 선택하여 모델 품질을 개선할 수 있습니다.

[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="next-steps"></a>다음 단계

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.

> [!div class="checklist"]
> * 문제 이해
> * 적절한 기계 학습 알고리즘 선택
> * 데이터 준비
> * 데이터 변환
> * 모델 학습
> * 모델 평가
> * 학습된 모델을 통해 예측
> * 로드된 모델을 통해 배포 및 예측

다음 자습서로 이동하여 자세히 알아보기

> [!div class="nextstepaction"]
> [문제 분류](github-issue-classification.md)

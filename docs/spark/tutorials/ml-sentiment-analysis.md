---
title: .NET for Apache Spark 및 ML.NET을 사용한 감정 분석 자습서
description: 이 자습서에서는 감정 분석을 위해 .NET for Apache Spark와 함께 ML.NET을 사용하는 방법을 알아봅니다.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: 1c2c966a4ff50a9d2f6951e20d909c5c20c75bfb
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688243"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a>자습서: .NET for Apache Spark 및 ML.NET을 사용한 감정 분석

이 자습서에서는 ML.NET 및 .NET for Apache Spark를 사용하여 온라인 리뷰에 대한 감정 분석을 수행하는 방법을 배웁니다. [ML.NET](http://dot.net/ml)은 무료 플랫폼 간 오픈 소스 기계 학습 프레임워크입니다. ML.NET을 .NET for Apache Spark와 함께 사용하여 기계 학습 알고리즘의 학습 및 예측을 확장할 수 있습니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> * Visual Studio에서 ML.NET 모델 작성기를 사용하여 감정 분석 모델을 만듭니다.
> * .NET for Apache Spark 콘솔 앱을 만듭니다.
> * 사용자 정의 함수를 작성하고 구현합니다.
> * .NET for Apache Spark 콘솔 앱을 실행합니다.

## <a name="prerequisites"></a>사전 요구 사항

* .NET for Apache Spark 애플리케이션을 개발한 적이 없다면 [자습서 시작](get-started.md)부터 시작하여 기본 사항을 숙지하세요. 이 자습서를 계속 진행하기 전에 시작 자습서에 대한 모든 필수 구성 요소를 완료합니다.

* 이 자습서에서는 Visual Studio에서 사용할 수 있는 시각적 인터페이스인 ML.NET 모델 작성기(미리 보기)를 사용합니다. Visual Studio가 아직 없는 경우 [Visual Studio의 Community 버전을 무료로 다운로드](https://visualstudio.microsoft.com/downloads/)할 수 있습니다.

* ML.NET 모델 작성기(미리 보기)를 [다운로드 및 설치](https://marketplace.visualstudio.com/items?itemName=MLNET.07)합니다.

* [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) 및 [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) 리뷰 데이터 세트를 다운로드합니다.

## <a name="review-the-data"></a>데이터 검토

Yelp 리뷰 데이터 세트는 다양한 서비스에 대한 온라인 Yelp 리뷰를 포함합니다. [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv)를 열고 데이터 구조를 확인합니다. 첫 번째 열에는 리뷰 텍스트가 포함되고 두 번째 열에는 감정 점수가 포함됩니다. 감정 점수가 1이면 리뷰는 긍정적이고 감정 점수가 0이면 리뷰는 부정적입니다.

다음 표는 샘플 데이터입니다.

|ReviewText|감정|
|-|-|
|우와... 여기가 좋았습니다.|    1|
|크러스트가 좋지 않습니다.|    0|

## <a name="build-your-machine-learning-model"></a>기계 학습 모델 빌드

1. Visual Studio를 열고 새 C# 콘솔 앱(.NET Core)을 만듭니다. 프로젝트 이름을 *MLSparkModel* 로 지정합니다.

1. **솔루션 탐색기** 에서 *MLSparkModel* 프로젝트를 마우스 오른쪽 단추로 클릭합니다. 그런 다음 **추가 > Machine Learning** 을 선택합니다.

1. ML.NET 모델 작성기에서 **감정 분석** 시나리오 타일을 선택합니다.

1. **데이터 추가** 페이지에서 *yelptrain.csv* 데이터 세트를 업로드합니다.

1. **예측할 열** 드롭다운에서 *감정* 을 선택합니다.

1. **학습** 페이지에서 학습 시간을 *60초* 로 설정하고 **학습 시작** 을 선택합니다. **진행률** 에서 학습 상태를 확인합니다.

1. 모델 작성기가 학습을 완료하면 학습 결과를 **평가** 합니다. **모델 테스트** 아래 텍스트 상자에 구를 입력하고 **예측** 을 선택하여 출력을 볼 수 있습니다.

1. **코드** 를 선택한 다음 **프로젝트 추가** 를 선택하여 ML 모델을 솔루션에 추가합니다.

1. 다음 두 프로젝트가 솔루션에 추가됩니다. **MLSparkModelML.ConsoleApp** 및 **MLSparkModelML.Model**.

1. *MLSpark* C# 프로젝트를 두 번 클릭하면 다음 프로젝트 참조가 추가된 것을 확인할 수 있습니다.

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a>콘솔 앱 만들기

모델 작성기는 콘솔 앱을 자동으로 만듭니다.

1. 솔루션 탐색기에서 **MLSparkModelML** 을 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리** 를 선택합니다.

1. **Microsoft.Spark** 를 검색하여 패키지를 설치합니다. **Microsoft.ML** 은 모델 작성기에 의해 자동으로 설치됩니다.

### <a name="create-a-sparksession"></a>SparkSession 만들기

1. **MLSparkModelML.ConsoleApp** 에 대한 *Program.cs* 파일을 엽니다. 이 파일은 모델 작성기가 자동으로 생성한 것입니다. `using` 문, Main() 메서드의 내용 및 `CreateSingleDataSample` 영역을 삭제합니다.

1. *Program.cs* 의 맨 위에 다음 `using` 문을 추가합니다.

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. `DATA_FILEPATH`를 *yelptest.csv* 의 경로로 변경합니다.

1. `Main` 메서드에 다음 코드를 추가하여 새 `SparkSession`을 만듭니다. Spark 세션은 Dataset 및 DataFrame API를 사용하여 Spark를 프로그래밍하기 위한 진입점입니다.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   위에서 만든 *spark* 개체를 호출하면 프로그램 전체에서 Spark 및 DataFrame 기능에 액세스할 수 있습니다.

### <a name="create-a-dataframe-and-print-to-console"></a>데이터 프레임을 만들고 콘솔에 인쇄

*yelptest.csv* 파일에서 `DataFrame`으로 Yelp 리뷰 데이터를 읽습니다. `header` 및 `inferSchema` 옵션을 포함시킵니다. `header` 옵션은 *yelptest.csv* 의 첫 번째 줄을 데이터가 아니라 열 이름으로 읽습니다. `inferSchema` 옵션은 데이터를 기반으로 열 형식을 유추합니다.

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a>사용자 정의 함수 등록

Spark 애플리케이션에서 *UDF(사용자 정의 함수)* 를 사용하여 데이터에 대한 계산 및 분석을 수행할 수 있습니다. 이 자습서에서는 ML.NET을 UDF와 함께 사용하여 각 Yelp 리뷰를 평가합니다.

`Main` 메서드에 다음 코드를 추가하여 `MLudf`라는 UDF를 등록합니다.

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

이 UDF는 Yelp 리뷰 문자열을 입력으로 사용하고 긍정적 또는 부정적 감정 각각에 대해 true 또는 false를 출력합니다. 이후 단계에서 정의하는 *predict()* 메서드를 사용합니다.

### <a name="use-spark-sql-to-call-the-udf"></a>Spark SQL을 사용하여 UDF 호출

이제 데이터를 읽고 ML을 통합했으므로 Spark SQL을 사용하여 데이터 프레임의 각 행에 감정 분석을 실행하는 UDF를 호출합니다. `Main` 메서드에 다음 코드를 추가합니다.

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a>predict() 메서드 만들기

`Main()` 메서드 앞에 다음 코드를 추가합니다. 이 코드는 *ConsumeModel.cs* 에서 모델 작성기에 의해 생성된 코드와 비슷합니다. 이 메서드를 콘솔로 이동하면 앱을 실행할 때마다 모델을 로드합니다.

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a>콘솔 앱에 모델 추가

솔루션 탐색기에서 **MLSparkModelML.Model** 프로젝트의 *MLModel.zip* 파일을 복사하여 **MLSparkModelML.ConsoleApp** 프로젝트에 붙여넣습니다. *MLSparkModelML.ConsoleApp.csproj* 에 참조가 자동으로 추가됩니다.

## <a name="run-your-code"></a>코드 실행

`spark-submit`을 사용하여 코드를 실행합니다. 명령 프롬프트를 사용하여 콘솔 앱의 루트 폴더로 이동하고 다음 명령을 실행합니다.

먼저 앱을 정리하고 게시합니다.

```dotnetcli
dotnet clean
dotnet publish
```

그런 다음 콘솔 앱의 게시 폴더로 이동하고 다음 `spark-submit` 명령을 실행합니다. 이 명령을 Microsoft Spark jar 파일의 실제 경로로 업데이트해야 합니다.

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2-4_2.11-1.0.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a>코드 가져오기

이 자습서는 [빅 데이터를 사용한 감정 분석](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) 예제의 코드와 비슷합니다.

## <a name="next-steps"></a>다음 단계

다음 문서로 이동하면 .NET for Apache Spark를 사용하여 구조적 스트리밍을 수행하는 방법을 알아볼 수 있습니다.
> [!div class="nextstepaction"]
> [자습서: .NET for Apache Spark를 사용한 구조적 스트리밍](streaming.md)

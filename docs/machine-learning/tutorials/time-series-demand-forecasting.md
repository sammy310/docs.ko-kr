---
title: '자습서: 자전거 대여 수요 예측 - 시계열'
description: 이 자습서에서는 시계열 분석 및 ML.NET를 사용하여 자전거 대여 서비스 수요를 예측하는 방법을 보여 줍니다.
ms.date: 11/07/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 2482709abfadad0505a40f4c37fd58cee4a2634c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978196"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a>자습서: 시계열 분석 및 ML.NET를 사용하여 자전거 대여 서비스 수요 예측

ML.NET를 통해 SQL Server 데이터베이스에 저장된 데이터에 대한 단일 시계열 분석을 사용하여 자전거 대여 서비스 수요를 예측하는 방법을 알아봅니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
>
> * 문제 이해
> * 데이터베이스에서 데이터 로드
> * 예측 모델 만들기
> * 예측 모델 평가
> * 예측 모델 저장
> * 예측 모델 사용

## <a name="prerequisites"></a>전제 조건

- “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017).

## <a name="time-series-forecasting-sample-overview"></a>시계열 예측 샘플 개요

이 샘플은 단일 스펙트럼 분석이라고 하는 일변량 시계열 분석 알고리즘을 사용하여 자전거 대여 수요를 예측하는 **C# .NET Core 콘솔 애플리케이션**입니다. 이 샘플의 코드는 GitHub의 [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand)에서 찾을 수 있습니다.

## <a name="understand-the-problem"></a>문제 이해

효율적인 작업을 실행하기 위해 재고 관리는 주요 역할을 담당합니다. 재고가 너무 많은 제품이 있다면 제품이 판매되지 않은 채 진열대에 쌓여 아무런 수익을 창출하지 않는 것과 같습니다. 제품 수가 너무 적으면 판매 및 고객 손실이 발생하여 경쟁사에게 고객을 빼앗길 수 있습니다. 따라서 가장 적합한 재고 보유량에 대해 끊임없는 질문을 던져야 합니다. 시계열 분석은 기록 데이터를 보고 패턴을 식별하고 이 정보를 사용하여 나중에 값을 예측하는 방식으로 이러한 질문에 대한 답을 제공합니다.

이 자습서에서 사용되는 데이터를 분석하는 방법은 일변량 시계열 분석입니다. 일변량 시계열 분석은 월별 판매량 같은 특정 간격으로 일정 기간의 단일 수치를 확인합니다.

이 자습서에서 사용되는 알고리즘은 [SSA(단일 스펙트럼 분석)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf)입니다. SSA는 시계열을 주요 구성 요소 집합으로 분리하는 방식으로 작동합니다. 이러한 구성 요소는 추세, 노이즈, 계절성 및 기타 여러 요소에 해당하는 신호의 일부분으로 해석될 수 있습니다. 그런 다음 이러한 구성 요소가 재구성되어 나중에 값을 예측하는 데 사용됩니다.

## <a name="create-console-application"></a>콘솔 애플리케이션 만들기

1. "BikeDemandForecasting"이라는 새 **C# .NET Core 애플리케이션**을 만듭니다.
1. **Microsoft.ML** 버전 **1.4.0** NuGet 패키지를 설치합니다.
    1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.
    1. 패키지 소스로 “nuget.org”를 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색합니다.
    1. **시험판 포함** 확인란을 선택합니다.
    1. **설치** 단추를 선택합니다.
    1. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 [라이선스 승인] 대화 상자에서 **동의함** 단추를 선택합니다.
    1. **System.Data.SqlClient** 버전 **4.7.0** 및 **Microsoft.ML.TimeSeries** 버전 **1.4.0**에 대해 이러한 단계를 반복하세요.

### <a name="prepare-and-understand-the-data"></a>데이터 준비 및 이해

1. *데이터* 디렉터리를 만듭니다.
1. [*DailyDemand.mdf* 데이터베이스 파일](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf)을 다운로드하여 *데이터* 디렉터리에 저장합니다.

> [!NOTE]
> 이 자습서에서 사용되는 데이터는 [UCI 자전거 공유 데이터 세트](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset)에서 제공됩니다. Fanaee-T, Hadi, Gama, Joao, 'Event labeling combining ensemble detectors and background knowledge', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [웹 링크](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).

원본 데이터 세트에는 계절성 및 날씨에 해당하는 여러 열이 포함되어 있습니다. 간단히 하기 위해 이 자습서에서 사용되는 알고리즘에는 단일 숫자 열의 값만 필요하므로 원본 데이터 세트는 다음 열만 포함하도록 압축되었습니다.

- **dteday**: 관측 날짜입니다.
- **year**: 인코딩된 관측 연도입니다(0=2011, 1=2012).
- **cnt**: 해당 일에 대한 총 자전거 대여 수입니다.

원본 데이터 세트는 SQL Server 데이터베이스에서 다음 스키마를 포함하는 데이터베이스 테이블에 매핑됩니다.

```SQL
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

다음은 데이터 샘플입니다.

| RentalDate | Year | TotalRentals |
| --- | --- | --- |
|1/1/2011|0|985|
|1/2/2011|0|801|
|1/3/2011|0|1349|

### <a name="create-input-and-output-classes"></a>입력 및 출력 클래스 만들기

1. *Program.cs* 파일을 열고 기존 `using` 문을 다음으로 바꿉니다.

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. `ModelInput` 클래스를 만듭니다. `Program` 클래스 아래에 다음 코드를 추가합니다.

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    `ModelInput` 클래스에는 다음 열이 포함됩니다.

    - **RentalDate**: 관측 날짜입니다.
    - **Year**: 인코딩된 관측 연도입니다(0=2011, 1=2012).
    - **TotalRentals**: 해당 일에 대한 총 자전거 대여 수입니다.

1. 새로 만든 `ModelInput` 클래스 아래에 `ModelOutput` 클래스를 만듭니다.

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    `ModelOutput` 클래스에는 다음 열이 포함됩니다.

    - **ForecastedRentals**: 예측 기간의 예측 값입니다.
    - **LowerBoundRentals**: 예측 기간의 예측 최소값입니다.
    - **UpperBoundRentals**: 예측 기간의 예측 최대값입니다.

### <a name="define-paths-and-initialize-variables"></a>경로 정의 및 변수 초기화

1. `Main` 메서드 내에서 데이터의 위치, 연결 문자열 및 학습된 모델을 저장할 위치를 저장하는 변수를 정의합니다.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. `Main` 메서드에 다음 줄을 추가하여 [`MLContext`](xref:Microsoft.ML.MLContext)의 새로운 인스턴스로 `mlContext` 변수를 초기화합니다.

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    [`MLContext`](xref:Microsoft.ML.MLContext) 클래스는 모든 ML.NET 작업의 시작점이며, mlContext를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다. 개념적으로 Entity Framework의 `DBContext`와 유사합니다.

## <a name="load-the-data"></a>데이터 로드

1. `ModelInput` 형식의 레코드를 로드하는 `DatabaseLoader`를 만듭니다.

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. 데이터베이스에서 데이터를 로드하는 쿼리를 정의합니다.

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    ML.NET 알고리즘은 데이터를 [`Single`](xref:System.Single) 형식으로 간주합니다. 따라서 [`Real`](xref:System.Data.SqlDbType) 형식이 아닌 데이터베이스에서 가져온 숫자 값(단정밀도 부동 소수점 값)은 [`Real`](xref:System.Data.SqlDbType)로 변환해야 합니다.

    `Year` 및 `TotalRental` 열은 모두 데이터베이스의 정수 형식입니다. `CAST` 기본 제공 함수를 사용하여 `Real`로 캐스팅됩니다.

1. 데이터베이스에 연결하고 쿼리를 실행하는 `DatabaseSource`를 만듭니다.

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. 데이터를 `IDataView`에 로드합니다.

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. 데이터 세트에는 두 개 연도 분량의 데이터가 포함됩니다. 첫 번째 연도의 데이터만 학습에 사용되고, 두 번째 연도는 모델에서 생성된 예측과 실제 값을 비교하는 데 사용됩니다. [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) 변환을 사용하여 데이터를 필터링합니다.

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    첫 번째 연도의 경우 `upperBound` 매개 변수를 1로 설정하여 `Year` 열의 값만 선택합니다. 반면 두 번째 연도의 경우 `lowerBound` 매개 변수를 1로 설정하여 1 이상의 값을 선택합니다.

## <a name="define-time-series-analysis-pipeline"></a>시계열 분석 파이프라인 정의

1. [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator)를 사용하여 시계열 데이터 세트의 값을 예측하는 파이프라인을 정의합니다.

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    `forecastingPipeline`은 첫 번째 연도와 샘플에 대해 365개의 데이터 요소를 사용하거나 시계열 데이터 세트를 `seriesLength` 매개 변수에 지정된 대로 30일(월별) 간격으로 분할합니다. 이러한 각 샘플은 주별 또는 7일 기간을 통해 분석됩니다. 다음 기간에 대한 예측 값을 결정할 때 이전 7일의 값을 사용하여 예측을 수행합니다. 모델은 `horizon` 매개 변수로 정의된 대로 향후 7일의 기간을 예측하도록 설정됩니다. 예측은 추측이므로 항상 100% 정확하지는 않습니다. 따라서 상한 및 하한으로 정의된 최선 및 최악의 시나리오 값 범위를 파악하고 있는 것이 좋습니다. 이 경우 하한 및 상한에 대한 신뢰 수준은 95%로 설정됩니다. 신뢰 수준을 적절하게 높이거나 줄일 수 있습니다. 값이 높을수록 원하는 수준의 신뢰도를 얻기 위해 상한 및 하한 간 범위가 넓어집니다.

1. [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) 메서드를 사용하여 모델을 학습하고 이전에 정의된 `forecastingPipeline`에 데이터를 맞춥니다.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a>모델 평가

다음 연도의 데이터를 예측하고 실제 값과 비교하여 모델이 얼마나 잘 수행하고 있는지 평가합니다.

1. `Main` 메서드 아래 `Evaluate`라는 새 유틸리티 메서드를 만듭니다.

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. `Evaluate` 메서드 내에서 학습된 모델과 함께 [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) 메서드를 사용하여 두 번째 연도의 데이터를 예측합니다.

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) 메서드를 사용하여 데이터에서 실제 값을 가져옵니다.

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) 메서드를 사용하여 예측 값을 가져옵니다.

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. 일반적으로 오류라고 하는 실제 값과 예측 값의 차이를 계산합니다.

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. 절대 평균 오차 및 제곱 평균 오차 값을 계산하여 성능을 측정합니다.

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    성능을 평가하기 위해 다음 메트릭이 사용됩니다.

    - **절대 평균 오차**: 예측이 실제 값과 얼마나 근접한지 측정합니다. 이 값의 범위는 0과 무한대 사이입니다. 0에 가까울수록 모델의 품질이 좋습니다.
    - **제곱 평균 오차**: 모델의 오류를 요약합니다. 이 값의 범위는 0과 무한대 사이입니다. 0에 가까울수록 모델의 품질이 좋습니다.

1. 메트릭을 콘솔에 출력합니다.

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. `Main` 메서드 내에 `Evaluate` 메서드를 사용합니다.

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a>모델 저장

모델에 만족하는 경우 나중에 다른 애플리케이션에서 사용할 수 있도록 저장합니다.

1. `Main` 메서드에서 [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602)을 만듭니다. [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602)은 단일 예측을 만드는 편리한 메서드입니다.

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. 이전에 정의된 `modelPath` 변수에 지정된 대로 `MLModel.zip`이라는 파일에 모델을 저장합니다. [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) 메서드를 사용하여 모델을 저장합니다.

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a>모델을 사용하여 수요 예측

1. `Evaluate` 메서드 아래 `Forecast`라는 새 유틸리티 메서드를 만듭니다.

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. `Forecast` 메서드 내에서 [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) 메서드를 사용하여 다음 7일 동안의 대여를 예측합니다.

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. 7일간의 실제 값과 예측 값을 맞춥니다.

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. 예측 출력을 반복하여 콘솔에 표시합니다.

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a>애플리케이션 실행

1. `Main` 메서드 내에서 `Forecast` 메서드를 호출합니다.

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. 애플리케이션을 실행합니다. 아래와 유사한 출력이 콘솔에 표시됩니다. 간단히 표시하기 위해 출력이 압축되었습니다.

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

실제 값 및 예측 값을 검사하면 다음과 같은 관계가 표시됩니다.

![실제 및 예측 비교](./media/time-series-demand-forecasting/forecast.png)

예측 값이 정확한 대여 수를 예측하지는 않지만 더 좁은 범위의 값을 제공하여 작업에서 리소스 사용을 최적화할 수 있습니다.

지금까지 이제 자전거 대여 수요를 예측하는 시계열 기계 학습 모델을 성공적으로 빌드했습니다.

[dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [ML.NET의 기계 학습 작업](../resources/tasks.md)
- [모델 정확도 향상](../resources/improve-machine-learning-model-ml-net.md)

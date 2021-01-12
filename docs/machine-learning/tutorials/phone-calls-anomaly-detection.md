---
title: '자습서: 전화 통화의 변칙 검색'
description: 시계열 데이터에 대한 변칙 검색 애플리케이션을 빌드하는 방법을 알아봅니다. 이 자습서에서는 Visual Studio 2019에서 C#을 사용하여 .NET Core 콘솔 애플리케이션을 만듭니다.
ms.date: 12/04/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3451a44f8fa7ae85625687b7d52f120c411df1b6
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97634055"
---
# <a name="tutorial-detect-anomalies-in-time-series-with-mlnet"></a>자습서: ML.NET을 사용하여 시계열의 변칙 검색

시계열 데이터에 대한 변칙 검색 애플리케이션을 빌드하는 방법을 알아봅니다. 이 자습서에서는 Visual Studio 2019에서 C#을 사용하여 .NET Core 콘솔 애플리케이션을 만듭니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
>
> * 데이터 로드
> * 시계열의 기간 검색
> * 정기 시계열의 변칙 검색

[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

* “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2019 버전 16.7.8 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

* [phone-calls.csv 데이터 세트](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv)

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

1. “ProductSalesAnomalyDetection”이라고 하는 **C# .NET Core 콘솔 애플리케이션** 을 만듭니다.

2. 프로젝트에서 *Data* 디렉터리를 만들어 데이터 세트 파일을 저장합니다.

3. **Microsoft.ML NuGet 패키지** 를 설치합니다.

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리** 를 선택합니다. "nuget.org"를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML** 을 검색하고 **설치** 단추를 선택합니다. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다. **Microsoft.ML.TimeSeries** 에 이 단계를 반복합니다.

4. *Program.cs* 파일 맨 위에 다음 `using` 문을 추가합니다.

    [!code-csharp[AddUsings](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>데이터 다운로드

1. 데이터 세트를 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다.

    [phone-calls.csv](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrCnnDetection/Data/phone-calls.csv)를 마우스 오른쪽 단추로 클릭하고 “링크(또는 대상)를 다른 이름으로 저장...”을 선택합니다.

     \*.csv 파일을 *Data* 폴더에 저장하거나 다른 곳에 저장한 후 \*.csv 파일을 *Data* 폴더로 이동합니다.

2. 솔루션 탐색기에서 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다. **고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사** 로 변경합니다.

다음 표는 \*.csv 파일의 데이터 미리 보기입니다.

| timestamp  | 값 |
|--------|--------------|
| 2018/9/3  | 36.69670857  |
| 2018/9/4  | 35.74160571  |
| .....  | .....  |
| 2018/10/3  | 34.49893429  |
| ...    | ....   |

이 파일은 시계열을 나타냅니다. 파일의 각 행은 데이터 요소입니다. 각 데이터 요소에는 각 날짜의 전화 통화 수를 나타내는 두 개의 특성 `timestamp`와 `value`가 있습니다. 전화 통화 수가 둔감도로 변환됩니다.

### <a name="create-classes-and-define-paths"></a>클래스 만들기 및 경로 정의

그런 다음 입력 및 예측 클래스 데이터 구조를 정의합니다.

새 클래스를 프로젝트에 추가합니다.

1. **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **추가 > 새 항목** 을 선택합니다.

2. **새 항목 추가** 대화 상자에서 **클래스** 를 선택하고 **이름** 필드를 *PhoneCallsData.cs* 로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.

   *PhoneCallsData.cs* 파일이 코드 편집기에서 열립니다.

3. *PhoneCallsData.cs* 의 맨 위에 다음 `using` 문을 추가합니다.

   ```csharp
   using Microsoft.ML.Data;
   ```

4. 기존 클래스 정의를 제거하고 두 개의 클래스 `PhoneCallsData` 및 `PhoneCallsPrediction`가 있는 다음 코드를 *PhoneCallsData.cs* 파일에 추가합니다.

    [!code-csharp[DeclareTypes](./snippets/phone-calls-anomaly-detection/csharp/PhoneCallsData.cs#DeclareTypes "Declare data record types")]

    `PhoneCallsData`은 입력 데이터 클래스를 지정합니다. [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 특성은 데이터 세트에서 로드해야 하는 열(열 인덱스 기준)을 지정합니다. 여기에는 데이터 파일의 동일한 특성에 해당하는 2개의 특성 `timestamp`와 `value`가 있습니다.

    `PhoneCallsPrediction`을 통해서는 예측 데이터 클래스를 지정합니다. SR-CNN 탐지기의 경우 예측은 지정된 [검색 모드](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode)에 따라 달라집니다. 이 샘플에서는 `AnomalyAndMargin` 모드를 선택합니다. 출력에는 7개의 열이 포함되어 있습니다. 대부분의 경우 `IsAnomaly`, `ExpectedValue`, `UpperBoundary`, `LowerBoundary`로 정보가 충분합니다. 해당 열을 통해 지점이 비정상인지 여부, 지점에 필요한 값, 지점의 하위/상위 경계 지역을 알 수 있습니다.

5. `Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 데이터 파일의 경로를 지정합니다.

    [!code-csharp[Declare global variables](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a>Main에서 변수 초기화

1. `Main` 메서드의 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 대체하여 `mlContext` 변수를 선언하고 초기화합니다.

    [!code-csharp[CreateMLContext](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    [MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작점이며, `mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다. 개념적으로 Entity Framework의 `DBContext`와 유사합니다.

### <a name="load-the-data"></a>데이터 로드

ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다. `IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다. 데이터를 텍스트 파일 또는 다른 소스(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.

1. 아래 코드를 `Main` 메서드의 다음 줄로 추가합니다.

    [!code-csharp[LoadData](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)은 데이터 스키마를 정의하고 파일에서 읽습니다. 데이터 경로 변수를 가져와서 `IDataView`를 반환합니다.

## <a name="time-series-anomaly-detection"></a>시계열 변칙 검색

시계열 변칙 검색은 시계열 데이터의 이상값, 즉 예상치 않거나 “이상한” 동작이 발생한 지정된 시계열의 지점을 검색하는 프로세스로서, 이러한 변칙은 일반적으로 사용자 계정에 대한 사이버 공격, 정전, 서버의 버스트 RPS, 메모리 누수 등의 문제 도메인과 관련된 이벤트를 나타냅니다.

시계열의 변칙을 찾으려면 먼저 계열의 기간을 확인해야 합니다. 그런 다음 시계열을 `Y = T + S + R`로 여러 구성 요소로 분해할 수 있습니다. 여기서 `Y`는 원래 계열, `T`는 추세 구성 요소, `S`는 계절적 구성 요소, `R`은 계열의 잔여 구성 요소입니다. 이 단계를 [분해](https://en.wikipedia.org/wiki/Decomposition_of_time_series)라고 합니다. 마지막으로 잔여 구성 요소를 검색하여 변칙을 찾습니다. ML.NET에서 SR-CNN 알고리즘은 SR(Spectral Residual) 및 CNN(나선형 신경망)을 기반으로 시계열의 변칙을 검색하는 최신 고급 알고리즘입니다. 이 알고리즘에 대한 자세한 내용은 [Time-Series Anomaly Detection Service at Microsoft](https://arxiv.org/pdf/1906.03821.pdf)(Microsoft의 시계열 변칙 검색 서비스)를 참조하세요.

이 자습서에서는 이러한 프로시저를 두 개의 함수를 사용하여 완료할 수 있습니다.

## <a name="detect-period"></a>검색 기간

첫 번째 단계에서는 `DetectSeasonality` 함수를 호출하여 계열의 기간을 결정합니다.

### <a name="create-the-detectperiod-method"></a>DetectPeriod 메서드 만들기

1. 다음 코드를 사용하여 `Main` 메서드 바로 아래에 `DetectPeriod` 메서드를 만듭니다.

    ```csharp
    static void DetectPeriod(MLContext mlContext, IDataView phoneCalls)
    {

    }
    ```

2. <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> 함수를 사용하여 기간을 검색합니다. 다음 코드를 사용하여 `DetectPeriod` 메서드에 추가합니다.

    [!code-csharp[DetectSeasonality](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectSeasonality)]

3. 다음 내용을 `DetectPeriod` 메서드에서 다음 코드 줄로 추가하여 기간 값을 표시합니다.

    [!code-csharp[DisplayPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayPeriod)]

4. `Main` 메서드의 `DetectPeriod` 메서드에 다음 호출을 추가합니다.

    [!code-csharp[CallDetectPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectPeriod)]

### <a name="period-detection-results"></a>기간 검색 결과

애플리케이션을 실행합니다. 다음과 같은 결과가 나타나야 합니다.

```console
Period of the series is: 7.
```

## <a name="detect-anomaly"></a>변칙 검색

이 단계에서는 <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A> 메서드를 사용하여 변칙을 찾습니다.

### <a name="create-the-detectanomaly-method"></a>DetectAnomaly 메서드 만들기

1. 다음 코드를 사용하여 `DetectPeriod` 메서드 바로 아래에 `DetectAnomaly` 메서드를 만듭니다.

    ```csharp
    static void DetectAnomaly(MLContext mlContext, IDataView phoneCalls, int period)
    {

    }
    ```

2. 다음 코드를 사용하여 <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> 메서드에서 `DetectAnomaly`를 설정합니다.

    [!code-csharp[SetupSrCnnParameters](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#SetupSrCnnParameters)]

3. `DetectAnomaly` 메서드에 다음 코드 줄을 추가하여 SR-CNN 알고리즘으로 변칙을 검색합니다.

    [!code-csharp[DetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectAnomaly)]

4. 쉽게 표시할 수 있도록 다음 코드로 [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) 메서드를 사용하여 출력 데이터 뷰를 강력한 형식의 `IEnumerable`로 변환합니다.

    [!code-csharp[CreateEnumerableForResult](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateEnumerableForResult)]

5. `DetectAnomaly` 메서드에 아래 코드를 사용하여 표시 헤더를 다음 줄로 만듭니다.

    [!code-csharp[DisplayHeader](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayHeader)]

    변화점 검색 결과에서 다음 정보를 표시합니다.

    * `Index`는 각 지점의 인덱스입니다.
    * `Anomaly`는 각 지점이 변칙으로 검색되는지를 나타냅니다.
    * `ExpectedValue`는 각 지점의 예상 값입니다.
    * `LowerBoundary`는 각 지점이 변칙이 아닐 수 있는 최하위 값입니다.
    * `UpperBoundary`는 각 지점이 변칙이 아닐 수 있는 최상위 값입니다.

6. 다음 코드를 사용하여 `predictions` `IEnumerable`을 반복하고 결과를 표시합니다.

    [!code-csharp[DisplayAnomalyDetectionResults](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayAnomalyDetectionResults)]

7. `Main` 메서드의 `DetectAnomaly` 메서드에 다음 호출을 추가합니다.

    [!code-csharp[CallDetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectAnomaly)]

## <a name="anomaly-detection-results"></a>변칙 검색 결과

애플리케이션을 실행합니다. 다음과 같은 결과가 나타나야 합니다. 처리 중 메시지가 표시됩니다. 경고나 처리 메시지를 확인할 수 있습니다. 이해하기 쉽도록 일부 메시지는 다음 결과에서 제거되었습니다.

```console
Detect period of the series
Period of the series is: 7.
Detect anomaly points in the series
Index   Data    Anomaly AnomalyScore    Mag     ExpectedValue   BoundaryUnit    UpperBoundary   LowerBoundary
0,0,36.841787256739266,41.14206982401966,32.541504689458876
1,0,35.67303618137362,39.97331874865401,31.372753614093227
2,0,34.710132999891826,39.029491313022824,30.390774686760828
3,0,33.44765248883495,37.786086547816545,29.10921842985335
4,0,28.937110922276364,33.25646923540736,24.61775260914537
5,0,5.143895892785781,9.444178460066171,0.843613325505391
6,0,5.163325228419392,9.463607795699783,0.8630426611390014
7,0,36.76414836240396,41.06443092968435,32.46386579512357
8,0,35.77908590657007,40.07936847385046,31.478803339289676
9,0,34.547259536635245,38.847542103915636,30.246976969354854
10,0,33.55193524820608,37.871293561337076,29.23257693507508
11,0,29.091800129624648,33.392082696905035,24.79151756234426
12,0,5.154836630338823,9.455119197619213,0.8545540630584334
13,0,5.234332502492464,9.534615069772855,0.934049935212073
14,0,36.54992549471526,40.85020806199565,32.24964292743487
15,0,35.79526470980883,40.095547277089224,31.494982142528443
16,0,34.34099013096804,38.64127269824843,30.040707563687647
17,0,33.61201516582131,37.9122977331017,29.31173259854092
18,0,29.223563320561812,33.5238458878422,24.923280753281425
19,0,5.170512168851533,9.470794736131923,0.8702296015711433
20,0,5.2614938889462834,9.561776456226674,0.9612113216658926
21,0,36.37103858487317,40.67132115215356,32.07075601759278
22,0,35.813544599026855,40.113827166307246,31.513262031746464
23,0,34.05600492733225,38.356287494612644,29.755722360051863
24,0,33.65828319077884,37.95856575805923,29.358000623498448
25,0,29.381125690882463,33.681408258162854,25.080843123602072
26,0,5.261543539820418,9.561826107100808,0.9612609725400283
27,0,5.4873712582971805,9.787653825577571,1.1870886910167897
28,1,36.504694001629254,40.804976568909645,32.20441143434886  <-- alert is on, detected anomaly
...
```

지금까지 이제 정기 계열에서 기간 및 변칙을 검색하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.

[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.
> [!div class="checklist"]
>
> * 데이터 로드
> * 시계열 데이터의 기간 검색
> * 시계열 데이터의 변칙 검색

## <a name="next-steps"></a>다음 단계

Machine Learning 샘플 GitHub 리포지토리를 확인하여 전력 소비 변칙 검색 샘플을 살펴보세요.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples GitHub 리포지토리](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

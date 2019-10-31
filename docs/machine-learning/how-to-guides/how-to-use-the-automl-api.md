---
title: ML.NET 자동화 ML API 사용 방법
description: ML.NET 자동화 ML API는 모델 빌드 프로세스를 자동화하고 배포 준비된 모델을 생성합니다. 자동화된 기계 학습 작업을 구성하기 위해 사용할 수 있는 옵션에 대해 알아보세요.
ms.date: 04/24/2019
ms.custom: mvc,how-to
ms.openlocfilehash: bb1cd66e7341f2ada57d533d8b2dcbb48f08f726
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774560"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="58461-104">ML.NET 자동화 기계 학습 API 사용 방법</span><span class="sxs-lookup"><span data-stu-id="58461-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="58461-105">자동화된 기계 학습(AutoML)은 기계 학습을 데이터에 적용하는 프로세스를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="58461-106">데이터 세트가 있는 경우 AutoML **실험**을 실행하여 다른 데이터 기능화, 기계 학습 알고리즘, 하이퍼 매개 변수에 대해 반복하여 최상의 모델을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="58461-107">이 항목은 현재 미리 보기 중인 ML.NET용 자동화된 기계 학습 API에 대해 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="58461-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="58461-108">자료가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="58461-109">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="58461-109">Load data</span></span>

<span data-ttu-id="58461-110">자동화된 기계 학습은 [IDataView](xref:Microsoft.ML.IDataView)로 데이터 세트 불러오기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="58461-111">데이터의 형식은 탭으로 구분된 값(TSV) 파일과 쉼표로 구분된 값(CSV) 파일이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="58461-112">예:</span><span class="sxs-lookup"><span data-stu-id="58461-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="58461-113">기계 학습 작업 유형 선택</span><span class="sxs-lookup"><span data-stu-id="58461-113">Select the machine learning task type</span></span>
<span data-ttu-id="58461-114">실험을 만들기 전에 해결하려는 기계 학습 문제의 유형을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="58461-115">자동화 기계 학습에서는 다음 ML 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="58461-116">이진 분류</span><span class="sxs-lookup"><span data-stu-id="58461-116">Binary Classification</span></span>
* <span data-ttu-id="58461-117">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="58461-117">Multiclass Classification</span></span>
* <span data-ttu-id="58461-118">재발</span><span class="sxs-lookup"><span data-stu-id="58461-118">Regression</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="58461-119">실험 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="58461-119">Create experiment settings</span></span>

<span data-ttu-id="58461-120">파악된 ML 작업 유형에 대한 실험 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="58461-120">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="58461-121">이진 분류</span><span class="sxs-lookup"><span data-stu-id="58461-121">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="58461-122">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="58461-122">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="58461-123">재발</span><span class="sxs-lookup"><span data-stu-id="58461-123">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="58461-124">실험 설정 구성</span><span class="sxs-lookup"><span data-stu-id="58461-124">Configure experiment settings</span></span>

<span data-ttu-id="58461-125">실험은 구성 기능이 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="58461-125">Experiments are highly configurable.</span></span> <span data-ttu-id="58461-126">구성 설정 전체 목록은 [AutoML API 문서](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58461-126">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet) for a full list of configuration settings.</span></span>

<span data-ttu-id="58461-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-127">Some examples include:</span></span>

1. <span data-ttu-id="58461-128">실험을 실행할 수 있는 최대 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-128">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="58461-129">완료를 예약하기 전에 실험을 취소할 취소 토큰을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-129">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="58461-130">다른 최적화 메트릭을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-130">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="58461-131">`CacheDirectory` 설정은 AutoML 작업 중 학습된 모든 모델이 저장될 디렉터리의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58461-131">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="58461-132">`CacheDirectory`가 null로 설정된 경우 모델은 디스크로 기록되는 대신 메모리에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-132">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="58461-133">특정 트레이너를 사용하지 않도록 자동화된 ML을 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-133">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="58461-134">최적화할 트레이너의 기본 목록은 작업당 탐색됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-134">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="58461-135">이 목록은 각 실험에 대해 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-135">This list can be modified for each experiment.</span></span> <span data-ttu-id="58461-136">예를 들어 데이터 세트에서 느리게 실행되는 트레이너는 목록에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-136">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="58461-137">하나의 특정 트레이너 호출 `experimentSettings.Trainers.Clear()`를 최적화하려면 사용하려는 트레이너를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-137">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="58461-138">ML 작업당 지원되는 트레이너 목록은 아래의 해당 링크에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-138">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="58461-139">지원되는 이진 분류 알고리즘</span><span class="sxs-lookup"><span data-stu-id="58461-139">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="58461-140">지원되는 다중 클래스 분류 알고리즘</span><span class="sxs-lookup"><span data-stu-id="58461-140">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="58461-141">지원되는 회귀 알고리즘</span><span class="sxs-lookup"><span data-stu-id="58461-141">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="58461-142">최적화 메트릭</span><span class="sxs-lookup"><span data-stu-id="58461-142">Optimizing metric</span></span>

<span data-ttu-id="58461-143">위의 예와 같이 최적화 메트릭은 모델 학습 중 최적화할 메트릭을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-143">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="58461-144">선택할 수 있는 최적화 메트릭은 사용자가 선택하는 작업 유형에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-144">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="58461-145">다음은 사용 가능한 메트릭 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="58461-145">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="58461-146">이진 분류</span><span class="sxs-lookup"><span data-stu-id="58461-146">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="58461-147">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="58461-147">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="58461-148">재발</span><span class="sxs-lookup"><span data-stu-id="58461-148">Regression</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="58461-149">정확도</span><span class="sxs-lookup"><span data-stu-id="58461-149">Accuracy</span></span>| <span data-ttu-id="58461-150">LogLoss</span><span class="sxs-lookup"><span data-stu-id="58461-150">LogLoss</span></span> | <span data-ttu-id="58461-151">RSquared</span><span class="sxs-lookup"><span data-stu-id="58461-151">RSquared</span></span>
|<span data-ttu-id="58461-152">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="58461-152">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="58461-153">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="58461-153">LogLossReduction</span></span> | <span data-ttu-id="58461-154">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="58461-154">MeanAbsoluteError</span></span>
|<span data-ttu-id="58461-155">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="58461-155">AreaUnderRocCurve</span></span> | <span data-ttu-id="58461-156">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="58461-156">MacroAccuracy</span></span> | <span data-ttu-id="58461-157">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="58461-157">MeanSquaredError</span></span>
|<span data-ttu-id="58461-158">F1Score</span><span class="sxs-lookup"><span data-stu-id="58461-158">F1Score</span></span> | <span data-ttu-id="58461-159">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="58461-159">MicroAccuracy</span></span> | <span data-ttu-id="58461-160">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="58461-160">RootMeanSquaredError</span></span>
|<span data-ttu-id="58461-161">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="58461-161">NegativePrecision</span></span> | <span data-ttu-id="58461-162">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="58461-162">TopKAccuracy</span></span>
|<span data-ttu-id="58461-163">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="58461-163">NegativeRecall</span></span> |
|<span data-ttu-id="58461-164">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="58461-164">PositivePrecision</span></span>
|<span data-ttu-id="58461-165">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="58461-165">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="58461-166">데이터 사전 처리 및 기능화</span><span class="sxs-lookup"><span data-stu-id="58461-166">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="58461-167">기능 열은 <xref:System.Boolean>, <xref:System.Single> 및 <xref:System.String> 형식만 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-167">The feature column only supported types of <xref:System.Boolean>, <xref:System.Single>, and <xref:System.String>.</span></span>

<span data-ttu-id="58461-168">데이터 사전 처리는 기본적으로 발생하며 사용자를 위해 다음 단계가 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-168">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="58461-169">유용한 정보가 없는 기능 삭제</span><span class="sxs-lookup"><span data-stu-id="58461-169">Drop features with no useful information</span></span>

    <span data-ttu-id="58461-170">학습 및 유효성 검사 세트에서 유용한 정보가 없는 기능 삭제</span><span class="sxs-lookup"><span data-stu-id="58461-170">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="58461-171">여기에는 모든 누락된 값, 모든 행 전체에서 동일한 값, 또는 카디널리티가 매우 높은(예: 해시, ID 또는 GUID) 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-171">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="58461-172">누락 값 표시 및 귀속</span><span class="sxs-lookup"><span data-stu-id="58461-172">Missing value indication and imputation</span></span>

    <span data-ttu-id="58461-173">데이터 형식에 대한 기본값으로 누락 값 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="58461-173">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="58461-174">입력 열과 동일한 슬롯 개수로 표시기 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-174">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="58461-175">입력 열이 누락된 경우 추가된 표시기 기능의 값은 `1`이며, 그렇지 않으면 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="58461-175">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="58461-176">추가 기능 생성</span><span class="sxs-lookup"><span data-stu-id="58461-176">Generate additional features</span></span>

    <span data-ttu-id="58461-177">텍스트 기능: 유니그램 및 트라이그램을 사용하는 BOW(Bag of words) 기능</span><span class="sxs-lookup"><span data-stu-id="58461-177">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>

    <span data-ttu-id="58461-178">범주 기능: 카디널리티가 낮은 기능에 대한 원 핫 인코딩(One-hot encoding), 카디널리티가 높은 범주 기능에 대한 원 핫 해시 인코딩(one-hot-hash encoding)</span><span class="sxs-lookup"><span data-stu-id="58461-178">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="58461-179">변환 및 인코딩</span><span class="sxs-lookup"><span data-stu-id="58461-179">Transformations and encodings</span></span>

    <span data-ttu-id="58461-180">범주 기능으로 변환된 매우 적은 고유 값이 있는 텍스트 기능</span><span class="sxs-lookup"><span data-stu-id="58461-180">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="58461-181">범주 기능의 카디널리티에 따라 원 핫 인코딩(One-hot encoding) 또는 원 핫 해시 인코딩(one-hot-hash encoding)을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-181">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="58461-182">종료 기준</span><span class="sxs-lookup"><span data-stu-id="58461-182">Exit criteria</span></span>

<span data-ttu-id="58461-183">작업을 완료하는 기준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-183">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="58461-184">일정한 시간 후 종료 - 실험 설정에서 `MaxExperimentTimeInSeconds`를 사용하여 작업을 계속 실행할 수 있는 시간(초)를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-184">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="58461-185">취소 토큰 시 종료 - 완료를 예정하기 전에 작업을 취소할 수 있는 취소 토큰을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-185">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="58461-186">실험 만들기</span><span class="sxs-lookup"><span data-stu-id="58461-186">Create an experiment</span></span>

<span data-ttu-id="58461-187">실험 설정을 구성했다면 실험을 만들 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="58461-187">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="58461-188">실험 실행</span><span class="sxs-lookup"><span data-stu-id="58461-188">Run the experiment</span></span>

<span data-ttu-id="58461-189">실험을 실행하면 데이터 전처리, 학습 알고리즘 선택 및 하이퍼 매개 변수 튜닝이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-189">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="58461-190">AutoML은 `MaxExperimentTimeInSeconds`에 도달하거나 실험이 종료되기 전까지 기능화, 학습 알고리즘 및 하이퍼 매개 변수 조합을 계속 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-190">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="58461-191">유효성 검사 데이터에서 통과하고 싶은 경우 `Execute()`에 대한 기타 오버로드, 열 목적을 나타내는 열 정보 또는 prefeaturizer를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="58461-191">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="58461-192">학습 모드</span><span class="sxs-lookup"><span data-stu-id="58461-192">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="58461-193">학습 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="58461-193">Training dataset</span></span>

<span data-ttu-id="58461-194">AutoML은 학습 데이터를 제공할 수 있는 오버로드된 실험 Execute 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-194">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="58461-195">내부적으로 자동화된 ML은 데이터를 학습-검증 분할로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="58461-195">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="58461-196">사용자 지정 유효성 검사 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="58461-196">Custom validation dataset</span></span>

<span data-ttu-id="58461-197">보통 시계열 데이터가 있는 케이스이기 때문에 임의 분할이 허용되지 않는 경우 사용자 지정 유효성 검사 데이터 세트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58461-197">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="58461-198">사용자 고유의 유효성 검사 데이터 세트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-198">You can specify your own validation dataset.</span></span> <span data-ttu-id="58461-199">이 모델은 하나 이상의 임의 데이터 세트 대신 지정된 유효성 검사 데이터 세트를 기준으로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-199">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a><span data-ttu-id="58461-200">모델 메트릭 탐색</span><span class="sxs-lookup"><span data-stu-id="58461-200">Explore model metrics</span></span>

<span data-ttu-id="58461-201">ML 실험의 각 반복 후 해당 작업과 관련된 메트릭이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="58461-201">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="58461-202">예를 들어, 최적으로 실행된 유효성 검사 메트릭에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58461-202">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="58461-203">다음은 ML 작업당 사용 가능한 모든 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="58461-203">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="58461-204">이진 분류 메트릭</span><span class="sxs-lookup"><span data-stu-id="58461-204">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="58461-205">다중 클래스 분류 메트릭</span><span class="sxs-lookup"><span data-stu-id="58461-205">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="58461-206">재발 메트릭</span><span class="sxs-lookup"><span data-stu-id="58461-206">Regression metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="58461-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58461-207">See also</span></span>

<span data-ttu-id="58461-208">전체 코드 샘플 등에 대한 자세한 내용은 [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub 리포지토리에 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="58461-208">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>

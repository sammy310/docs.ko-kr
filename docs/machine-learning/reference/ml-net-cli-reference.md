---
title: ML.NET CLI 명령 참조
description: ML.NET CLI 도구의 auto-train 명령에 대한 개요, 샘플 및 참조입니다.
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 6f07cd8b4237f8931bbc0ec97bc0bbe18c488f16
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856070"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="6039e-103">ML.NET CLI 명령 참조</span><span class="sxs-lookup"><span data-stu-id="6039e-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="6039e-104">`classification`, `regression` 및 `recommendation` 명령은 ML.NET CLI 도구에서 제공하는 주 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-104">The `classification`, `regression`, and `recommendation` commands are the main commands provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="6039e-105">이 명령을 사용하면 AutoML(자동화된 Machine Learning)을 사용하여 분류, 회귀, 권장 사항 모델을 위한 좋은 품질의 ML.NET 모델과 해당 모델을 실행/채점할 예제 C# 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-105">These commands allow you to generate good quality ML.NET models for classification, regression, and recommendation models using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="6039e-106">또한 모델을 학습할 C# 코드를 생성하여 모델의 알고리즘과 설정을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="6039e-107">이 항목은 현재 미리 보기로 제공되는 ML.NET CLI 및 ML.NET AutoML을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="6039e-108">개요</span><span class="sxs-lookup"><span data-stu-id="6039e-108">Overview</span></span>

<span data-ttu-id="6039e-109">사용 예:</span><span class="sxs-lookup"><span data-stu-id="6039e-109">Example usage:</span></span>

```console
mlnet regression --dataset "cars.csv" --label-col price
```

<span data-ttu-id="6039e-110">`mlnet` ML 작업 명령(`classification`, `regression`, `recommendation`)은 다음과 같은 자산을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-110">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) generate the following assets:</span></span>

- <span data-ttu-id="6039e-111">사용 준비가 된 Serialize된 모델 .zip("최적 모델")</span><span class="sxs-lookup"><span data-stu-id="6039e-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="6039e-112">생성된 모델을 실행/채점할 C# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="6039e-113">해당 모델을 생성하기 위해 사용한 학습 코드가 포함된 C# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="6039e-114">처음 두 개의 자산은 ML 모델로 예측을 수행하기 위해 최종 사용자 앱(ASP.NET Core 웹앱, 서비스, 데스크톱 앱 등)에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="6039e-115">세 번째 자산인 학습 코드는 사용자에게 생성된 모델을 학습하기 위해 CLI에서 사용한 ML.NET API 코드를 표시하므로, 사용자는 특정 알고리즘 및 모델 설정을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="6039e-116">예</span><span class="sxs-lookup"><span data-stu-id="6039e-116">Examples</span></span>

<span data-ttu-id="6039e-117">분류 문제에 가장 간단한 CLI 명령(AutoML은 제공된 데이터에서 대부분의 구성을 추론):</span><span class="sxs-lookup"><span data-stu-id="6039e-117">The simplest CLI command for a classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet classification --dataset "customer-feedback.tsv" --label-col Sentiment
```

<span data-ttu-id="6039e-118">회귀 문제에 대한 다른 간단한 CLI 명령:</span><span class="sxs-lookup"><span data-stu-id="6039e-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet regression --dataset "cars.csv" --label-col Price
```

<span data-ttu-id="6039e-119">학습 데이터 세트, 테스트 데이터 세트 및 추가 사용자 지정 명시적 인수로 분류 모델을 만들고 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-119">Create and train a classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-col "InsuranceRisk" --cache on --train-time 600
```

## <a name="command-options"></a><span data-ttu-id="6039e-120">명령 옵션</span><span class="sxs-lookup"><span data-stu-id="6039e-120">Command options</span></span>

<span data-ttu-id="6039e-121">`mlnet` ML 작업 명령(`classification`, `regression`, `recommendation`)은 제공된 데이터 세트와 ML.NET CLI 옵션을 기반으로 여러 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-121">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) train multiple models based on the provided dataset and ML.NET CLI options.</span></span> <span data-ttu-id="6039e-122">이러한 명령은 또한 최상의 모델을 선택하고, 모델을 직렬화된 .zip 파일로 저장하고, 채점 및 학습을 위한 관련 C# 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-122">These commands also select the best model, save the model as a serialized .zip file, and generate related C# code for scoring and training.</span></span>

### <a name="classification-options"></a><span data-ttu-id="6039e-123">분류 옵션</span><span class="sxs-lookup"><span data-stu-id="6039e-123">Classification options</span></span>

<span data-ttu-id="6039e-124">`mlnet classification`을 실행하면 분류 모델이 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-124">Running `mlnet classification` will train a classification model.</span></span> <span data-ttu-id="6039e-125">ML 모델에서 데이터를 2개 이상의 클래스(예: 감정 분석)로 범주화하려면 이 명령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-125">Choose this command if you want an ML Model to categorize data into 2 or more classes (e.g. sentiment analysis).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="regression-options"></a><span data-ttu-id="6039e-126">회귀 옵션</span><span class="sxs-lookup"><span data-stu-id="6039e-126">Regression options</span></span>

<span data-ttu-id="6039e-127">`mlnet regression`을 실행하면 회귀 모델이 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-127">Running `mlnet regression` will train a regression model.</span></span> <span data-ttu-id="6039e-128">ML 모델에서 숫자 값을 예측(예: 가격 예측)하게 하려면 이 명령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-128">Choose this command if you want an ML Model to predict a numeric value (e.g. price prediction).</span></span>

```console
mlnet regression

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="recommendation-options"></a><span data-ttu-id="6039e-129">권장 사항 옵션</span><span class="sxs-lookup"><span data-stu-id="6039e-129">Recommendation options</span></span>

<span data-ttu-id="6039e-130">`mlnet recommendation`을 실행하면 권장 사항 모델이 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-130">Running `mlnet recommendation` will train a recommendation model.</span></span>  <span data-ttu-id="6039e-131">ML 모델에서 등급(예: 제품 권장 사항)에 따라 사용자에게 항목을 추천하게 하려면 이 명령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-131">Choose this command if you want an ML Model to recommend items to users based on ratings (e.g. product recommendation).</span></span>

```console
mlnet recommendation

--dataset <path> (REQUIRED)

--item-col <col> (REQUIRED)

--rating-col <col> (REQUIRED)

--user-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

<span data-ttu-id="6039e-132">잘못된 입력 옵션으로 인해 CLI 도구는 유효한 입력 목록과 오류 메시지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-132">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="dataset"></a><span data-ttu-id="6039e-133">데이터 세트</span><span class="sxs-lookup"><span data-stu-id="6039e-133">Dataset</span></span>

<span data-ttu-id="6039e-134">`--dataset | -d`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-134">`--dataset | -d` (string)</span></span>

<span data-ttu-id="6039e-135">이 인수는 다음 옵션 중 하나에 대한 파일 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-135">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="6039e-136">*A: 전체 데이터 세트 파일:* 이 옵션을 사용하고 사용자가 `--test-dataset` 및 `--validation-dataset`를 제공하지 않는다면 교차 유효성 검사(k-fold 등) 또는 자동화된 데이터 분할 접근법은 모델의 유효성 검사를 위해 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-136">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="6039e-137">이 경우에 사용자는 데이터 세트 파일 경로를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-137">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="6039e-138">*B: 학습 데이터 세트 파일:* 또한 사용자가 모델 유효성 검사에 데이터 세트를 제공하고 있다면(`--test-dataset` 및 옵션으로 `--validation-dataset`) `--dataset` 인수는 “학습 데이터 세트”만 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-138">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="6039e-139">예를 들어, 모델 품질의 유효성을 검사하고 정확도 메트릭을 획득하기 위해 80% - 20% 접근법을 사용할 경우 “학습 데이터 세트”는 데이터의 80%, “테스트 데이터 세트”는 데이터의 20%를 차지하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-139">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="6039e-140">테스트 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="6039e-140">Test dataset</span></span>

<span data-ttu-id="6039e-141">`--test-dataset | -t`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-141">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="6039e-142">테스트 데이터 세트 파일을 가리키는 파일 경로(예: 정확도 메트릭을 획득하기 위해 정규 유효성 검사 수행 시 80% - 20% 접근법을 사용하는 경우)</span><span class="sxs-lookup"><span data-stu-id="6039e-142">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="6039e-143">`--test-dataset`를 사용한다면 `--dataset`도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-143">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="6039e-144">--유효성 검사-데이터 세트가 사용되지 않을 경우 `--test-dataset` 인수는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-144">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="6039e-145">이 경우, 사용자는 세 개의 인수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-145">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="6039e-146">유효성 검사 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="6039e-146">Validation dataset</span></span>

<span data-ttu-id="6039e-147">`--validation-dataset | -v`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-147">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="6039e-148">유효성 검사 데이터 세트 파일을 가리키는 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-148">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="6039e-149">어떠한 경우에도 유효성 검사 데이터 세트는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-149">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="6039e-150">`validation dataset`를 사용할 경우 동작은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-150">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="6039e-151">`test-dataset` 및 `--dataset` 인수도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-151">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="6039e-152">`validation-dataset` 데이터 세트는 모델 선택에 대한 예측 오류를 예상하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-152">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="6039e-153">`test-dataset`는 최종 선택된 모델의 일반화 오류를 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-153">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="6039e-154">이상적으로, 테스트 세트는 “자격 증명 모음”에 보관되어야 하며 데이터 분석이 끝날 때만 꺼내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-154">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="6039e-155">기본적으로 `validation dataset` 및 `test dataset`를 사용할 경우 유효성 검사 단계는 다음 두 부분으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-155">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="6039e-156">첫 번째 부분에서는 모델을 살펴 보고 유효성 검사 데이터(=유효성 검사)를 사용하는 가장 효과적인 접근법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-156">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="6039e-157">그런 다음, 선택한 접근법의 정확도를 추정합니다(=테스트).</span><span class="sxs-lookup"><span data-stu-id="6039e-157">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="6039e-158">따라서 데이터는 80/10/10 또는 75/15/10으로 분리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-158">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="6039e-159">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="6039e-159">For example:</span></span>

- <span data-ttu-id="6039e-160">`training-dataset` 파일에는 데이터의 75%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-160">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="6039e-161">`validation-dataset` 파일에는 데이터의 15%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-161">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="6039e-162">`test-dataset` 파일에는 데이터의 10%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-162">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="6039e-163">어떠한 경우에도 이러한 백분율은 이미 분할된 파일을 제공할 CLI를 사용하는 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-163">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column"></a><span data-ttu-id="6039e-164">레이블 열</span><span class="sxs-lookup"><span data-stu-id="6039e-164">Label column</span></span>

<span data-ttu-id="6039e-165">`--label-col`(int 또는 문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-165">`--label-col` (int or string)</span></span>

<span data-ttu-id="6039e-166">이 인수를 사용하면 특정 목표/대상 열(예측하려는 변수)은 데이터 세트 헤더에 설정된 열 이름이나 데이터 세트 파일에서 열의 숫자 인덱스(열 인덱스 값은 0에서 시작)를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-166">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="6039e-167">이 인수는 ‘분류’ 및 ‘회귀’ 문제에 사용됩니다. </span><span class="sxs-lookup"><span data-stu-id="6039e-167">This argument is used for *classification* and *regression* problems.</span></span>

## <a name="item-column"></a><span data-ttu-id="6039e-168">항목 열</span><span class="sxs-lookup"><span data-stu-id="6039e-168">Item column</span></span>

<span data-ttu-id="6039e-169">`--item-col`(int 또는 문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-169">`--item-col` (int or string)</span></span>

<span data-ttu-id="6039e-170">항목 열에는 사용자가 평가하는 항목(사용자에게 권장되는 항목)의 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-170">The item column has the list of items that users rate (items are recommended to users).</span></span> <span data-ttu-id="6039e-171">이 열은 데이터 세트 헤더에 설정된 열 이름이나 데이터 세트 파일에서 열의 숫자 인덱스(열 인덱스 값은 0에서 시작)를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-171">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="6039e-172">이 인수는 ‘권장 사항’ 작업에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-172">This argument is used only for the *recommendation* task.</span></span>

## <a name="rating-column"></a><span data-ttu-id="6039e-173">등급 열</span><span class="sxs-lookup"><span data-stu-id="6039e-173">Rating column</span></span>

<span data-ttu-id="6039e-174">`--rating-col`(int 또는 문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-174">`--rating-col` (int or string)</span></span>

<span data-ttu-id="6039e-175">등급 열에는 사용자가 항목에 부여하는 등급의 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-175">The rating column has the list of ratings that are given to items by users.</span></span> <span data-ttu-id="6039e-176">이 열은 데이터 세트 헤더에 설정된 열 이름이나 데이터 세트 파일에서 열의 숫자 인덱스(열 인덱스 값은 0에서 시작)를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-176">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="6039e-177">이 인수는 ‘권장 사항’ 작업에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-177">This argument is used only for the *recommendation* task.</span></span>

## <a name="user-column"></a><span data-ttu-id="6039e-178">사용자 열</span><span class="sxs-lookup"><span data-stu-id="6039e-178">User column</span></span>

<span data-ttu-id="6039e-179">`--user-col`(int 또는 문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-179">`--user-col` (int or string)</span></span>

<span data-ttu-id="6039e-180">사용자 열에는 항목에 등급을 부여하는 사용자의 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-180">The user column has the list of users that give ratings to items.</span></span> <span data-ttu-id="6039e-181">이 열은 데이터 세트 헤더에 설정된 열 이름이나 데이터 세트 파일에서 열의 숫자 인덱스(열 인덱스 값은 0에서 시작)를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-181">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="6039e-182">이 인수는 ‘권장 사항’ 작업에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-182">This argument is used only for the *recommendation* task.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="6039e-183">열 무시</span><span class="sxs-lookup"><span data-stu-id="6039e-183">Ignore columns</span></span>

<span data-ttu-id="6039e-184">`--ignore-columns`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-184">`--ignore-columns` (string)</span></span>

<span data-ttu-id="6039e-185">이 인수를 사용하면 훈련 프로세스에서 로드되어 사용되지 않도록 데이터 세트 파일에서 기존 열을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-185">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="6039e-186">무시하려는 열 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-186">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="6039e-187">', '(공백이 있는 쉼표) 또는 ' '(공백)을 사용하여 여러 열 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-187">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="6039e-188">공백이 있는 열 이름에 큰따옴표를 사용할 수 있습니다(예: "logged in").</span><span class="sxs-lookup"><span data-stu-id="6039e-188">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="6039e-189">예:</span><span class="sxs-lookup"><span data-stu-id="6039e-189">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="6039e-190">헤더 있음</span><span class="sxs-lookup"><span data-stu-id="6039e-190">Has header</span></span>

<span data-ttu-id="6039e-191">`--has-header`(bool)</span><span class="sxs-lookup"><span data-stu-id="6039e-191">`--has-header` (bool)</span></span>

<span data-ttu-id="6039e-192">데이터 세트 파일에 헤더 행이 있는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-192">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="6039e-193">가능한 값은</span><span class="sxs-lookup"><span data-stu-id="6039e-193">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="6039e-194">사용자가 이 인수를 지정하지 않은 경우 ML.NET CLI에서 이 속성을 검색하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-194">The ML.NET CLI will try to detect this property if this argument is not specified by the user.</span></span>

## <a name="train-time"></a><span data-ttu-id="6039e-195">학습 시간</span><span class="sxs-lookup"><span data-stu-id="6039e-195">Train time</span></span>

<span data-ttu-id="6039e-196">`--train-time`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-196">`--train-time` (string)</span></span>

<span data-ttu-id="6039e-197">기본적으로 최대 탐색/학습 시간은 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-197">By default, the maximum exploration / train time is 30 minutes.</span></span>

<span data-ttu-id="6039e-198">이 인수는 프로세스에서 여러 트레이너와 구성을 검색하는 최대 시간(초 단위)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-198">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="6039e-199">단일 반복에 지정된 시간이 너무 짧을 경우(예를 들어 2초) 구성된 값이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-199">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="6039e-200">이 경우에 실제 시간은 단일 반복에서 하나의 모델 구성을 생성하는 데 필요한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-200">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="6039e-201">반복에 필요한 시간은 데이터 세트의 크기에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-201">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="6039e-202">캐시</span><span class="sxs-lookup"><span data-stu-id="6039e-202">Cache</span></span>

<span data-ttu-id="6039e-203">`--cache`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-203">`--cache` (string)</span></span>

<span data-ttu-id="6039e-204">캐싱을 사용할 경우 전체 학습 데이터 세트는 메모리에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-204">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="6039e-205">중소 규모의 데이터 세트의 경우, 캐시를 사용하면 학습 성능을 크게 개선할 수 있습니다. 즉, 캐시를 사용하지 않을 때보다 학습 시간을 단축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-205">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="6039e-206">단, 대규모 데이터 세트의 경우 메모리에 모든 데이터를 로드하면 메모리가 부족해져 좋지 않은 영향을 끼칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-206">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="6039e-207">대규모 데이터 세트 파일로 학습하고 캐시를 사용하지 않을 경우 ML.NET은 학습하는 동안 더 많은 데이터를 로드해야 할 때 드라이브에서 데이터 청크를 스트리밍하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-207">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="6039e-208">다음 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-208">You can specify the following values:</span></span>

<span data-ttu-id="6039e-209">`on`: 학습 시 캐시를 사용하도록 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-209">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="6039e-210">`off`: 학습 시 캐시를 사용하지 않도록 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-210">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="6039e-211">`auto`: AutoML 추론에 따라 캐시는 사용되거나 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-211">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="6039e-212">일반적으로, 중/소 규모의 데이터 세트는 캐시를 사용하고 대규모 데이터 세트는 사용자가 `auto` 선택을 사용할 경우 캐시를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-212">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="6039e-213">`--cache` 매개 변수를 지정하지 않는다면 캐시 `auto` 구성이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-213">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="6039e-214">이름</span><span class="sxs-lookup"><span data-stu-id="6039e-214">Name</span></span>

<span data-ttu-id="6039e-215">`--name`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-215">`--name` (string)</span></span>

<span data-ttu-id="6039e-216">생성된 출력 프로젝트 또는 솔루션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-216">The name for the created output project or solution.</span></span> <span data-ttu-id="6039e-217">지정된 이름이 없을 경우 `sample-{mltask}`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-217">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="6039e-218">ML.NET 모델 파일(.ZIP 파일)도 같은 이름을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-218">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="6039e-219">출력 경로</span><span class="sxs-lookup"><span data-stu-id="6039e-219">Output path</span></span>

<span data-ttu-id="6039e-220">`--output | -o`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-220">`--output | -o` (string)</span></span>

<span data-ttu-id="6039e-221">생성된 출력을 저장할 루트 위치/폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-221">Root location/folder to place the generated output.</span></span> <span data-ttu-id="6039e-222">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-222">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="6039e-223">자세한 정도</span><span class="sxs-lookup"><span data-stu-id="6039e-223">Verbosity</span></span>

<span data-ttu-id="6039e-224">`--verbosity | -v`(문자열)</span><span class="sxs-lookup"><span data-stu-id="6039e-224">`--verbosity | -v` (string)</span></span>

<span data-ttu-id="6039e-225">표준 출력의 자세한 정도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-225">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="6039e-226">허용된 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-226">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="6039e-227">`m[inimal]`(기본값)</span><span class="sxs-lookup"><span data-stu-id="6039e-227">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="6039e-228">`diag[nostic]`(로깅 정보 수준)</span><span class="sxs-lookup"><span data-stu-id="6039e-228">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="6039e-229">기본적으로 CLI 도구는 작동 중인지와 가능하다면 남은 시간 또는 완료된 시간 비율을 언급하는 등 일부 최소 피드백(`minimal`)을 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-229">By default, the CLI tool should show some minimum feedback (`minimal`) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="6039e-230">도움말</span><span class="sxs-lookup"><span data-stu-id="6039e-230">Help</span></span>

`-h |--help`

<span data-ttu-id="6039e-231">각 명령의 매개 변수에 대한 설명과 함께 명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6039e-231">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="6039e-232">참조</span><span class="sxs-lookup"><span data-stu-id="6039e-232">See also</span></span>

- [<span data-ttu-id="6039e-233">ML.NET CLI 도구를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="6039e-233">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="6039e-234">ML.NET CLI 개요</span><span class="sxs-lookup"><span data-stu-id="6039e-234">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="6039e-235">자습서: ML.NET CLI를 사용하여 감정 분석</span><span class="sxs-lookup"><span data-stu-id="6039e-235">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="6039e-236">ML.NET CLI의 원격 분석</span><span class="sxs-lookup"><span data-stu-id="6039e-236">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

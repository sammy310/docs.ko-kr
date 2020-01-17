---
title: ML.NET CLI 명령 참조
description: ML.NET CLI 도구의 auto-train 명령에 대한 개요, 샘플 및 참조입니다.
ms.date: 12/18/2019
ms.openlocfilehash: 5e59eba91721b26622360818a73adb07a654dc28
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636122"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="07d7b-103">ML.NET CLI 명령 참조</span><span class="sxs-lookup"><span data-stu-id="07d7b-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="07d7b-104">`auto-train` 명령은 ML.NET CLI 도구에서 제공하는 주 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-104">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="07d7b-105">이 명령을 사용하면 AutoML(자동화된 Machine Learning)을 사용하여 좋은 품질의 ML.NET 모델과 해당 모델을 실행/채점할 예제 C# 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-105">The command allows you to generate a good quality ML.NET model using automated machine learning (AutoML) as well as the the example C# code to run/score that model.</span></span> <span data-ttu-id="07d7b-106">또한 모델을 학습할 C# 코드를 생성하여 모델의 알고리즘과 설정을 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="07d7b-107">이 항목은 현재 미리 보기로 제공되는 ML.NET CLI 및 ML.NET AutoML을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="07d7b-108">개요</span><span class="sxs-lookup"><span data-stu-id="07d7b-108">Overview</span></span>

<span data-ttu-id="07d7b-109">사용 예:</span><span class="sxs-lookup"><span data-stu-id="07d7b-109">Example usage:</span></span>

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="07d7b-110">`mlnet auto-train` 명령은 다음 자산을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-110">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="07d7b-111">사용 준비가 된 Serialize된 모델 .zip("최적 모델")</span><span class="sxs-lookup"><span data-stu-id="07d7b-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="07d7b-112">생성된 모델을 실행/채점할 C# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="07d7b-113">해당 모델을 생성하기 위해 사용한 학습 코드가 포함된 C# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="07d7b-114">처음 두 개의 자산은 ML 모델로 예측을 수행하기 위해 최종 사용자 앱(ASP.NET Core 웹앱, 서비스, 데스크톱 앱 등)에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="07d7b-115">세 번째 자산인 학습 코드는 사용자에게 생성된 모델을 학습하기 위해 CLI에서 사용한 ML.NET API 코드를 표시하므로, 사용자는 특정 알고리즘 및 모델 설정을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="07d7b-116">예</span><span class="sxs-lookup"><span data-stu-id="07d7b-116">Examples</span></span>

<span data-ttu-id="07d7b-117">이진 분류 문제에 가장 간단한 CLI 명령(AutoML은 제공된 데이터에서 대부분의 구성을 추론):</span><span class="sxs-lookup"><span data-stu-id="07d7b-117">The simplest CLI command for a binary classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="07d7b-118">회귀 문제에 대한 다른 간단한 CLI 명령:</span><span class="sxs-lookup"><span data-stu-id="07d7b-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="07d7b-119">학습 데이터 세트, 테스트 데이터 세트 및 추가 사용자 지정 명시적 인수로 이진 분류 모델을 만들고 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-119">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a><span data-ttu-id="07d7b-120">명령 옵션</span><span class="sxs-lookup"><span data-stu-id="07d7b-120">Command options</span></span>

<span data-ttu-id="07d7b-121">`mlnet auto-train`은 제공된 데이터 세트에 따라 여러 모델을 학습하고 최종적으로 최적 모델을 선택한 후 직렬화된 .zip 파일로 저장하고 채점 및 학습을 위해 관련된 C# 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-121">`mlnet auto-train` trains multiple models based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

```console
mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

<span data-ttu-id="07d7b-122">잘못된 입력 옵션으로 인해 CLI 도구는 유효한 입력 목록과 오류 메시지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-122">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="task"></a><span data-ttu-id="07d7b-123">작업</span><span class="sxs-lookup"><span data-stu-id="07d7b-123">Task</span></span>

<span data-ttu-id="07d7b-124">`--task | --mltask | -T`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-124">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="07d7b-125">해결할 ML 문제를 제공하는 단일 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-125">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="07d7b-126">예를 들어, 다음 작업 중 하나(CLI는 결과적으로 AutoML에서 지원되는 모든 작업을 지원함):</span><span class="sxs-lookup"><span data-stu-id="07d7b-126">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="07d7b-127">`regression` - 숫자 값을 예측하기 위해 ML 모델을 사용할지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-127">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="07d7b-128">`binary-classification` - ML 모델 결과에 두 개의 가능한 범주 부울 값(0 또는 1)이 있는지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-128">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="07d7b-129">`multiclass-classification` - ML 모델 결과에 여러 개의 가능한 범주 값이 있는지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-129">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="07d7b-130">이 인수에는 단 하나의 ML 작업만 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-130">Only one ML task should be provided in this argument.</span></span>

## <a name="dataset"></a><span data-ttu-id="07d7b-131">데이터 세트</span><span class="sxs-lookup"><span data-stu-id="07d7b-131">Dataset</span></span>

<span data-ttu-id="07d7b-132">`--dataset | -d`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-132">`--dataset | -d` (string)</span></span>

<span data-ttu-id="07d7b-133">이 인수는 다음 옵션 중 하나에 대한 파일 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-133">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="07d7b-134">*A: 전체 데이터 세트 파일:* 이 옵션을 사용하고 사용자가 `--test-dataset` 및 `--validation-dataset`를 제공하지 않는다면 교차 유효성 검사(k-fold 등) 또는 자동화된 데이터 분할 접근법은 모델의 유효성 검사를 위해 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-134">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="07d7b-135">이 경우에 사용자는 데이터 세트 파일 경로를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-135">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="07d7b-136">*B: 학습 데이터 세트 파일:* 또한 사용자가 모델 유효성 검사에 데이터 세트를 제공하고 있다면(`--test-dataset` 및 옵션으로 `--validation-dataset`) `--dataset` 인수는 “학습 데이터 세트”만 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-136">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="07d7b-137">예를 들어, 모델 품질의 유효성을 검사하고 정확도 메트릭을 획득하기 위해 80% - 20% 접근법을 사용할 경우 “학습 데이터 세트”는 데이터의 80%, “테스트 데이터 세트”는 데이터의 20%를 차지하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-137">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="07d7b-138">테스트 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="07d7b-138">Test dataset</span></span>

<span data-ttu-id="07d7b-139">`--test-dataset | -t`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-139">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="07d7b-140">테스트 데이터 세트 파일을 가리키는 파일 경로(예: 정확도 메트릭을 획득하기 위해 정규 유효성 검사 수행 시 80% - 20% 접근법을 사용하는 경우)</span><span class="sxs-lookup"><span data-stu-id="07d7b-140">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="07d7b-141">`--test-dataset`를 사용한다면 `--dataset`도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-141">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="07d7b-142">--유효성 검사-데이터 세트가 사용되지 않을 경우 `--test-dataset` 인수는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-142">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="07d7b-143">이 경우, 사용자는 세 개의 인수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-143">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="07d7b-144">유효성 검사 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="07d7b-144">Validation dataset</span></span>

<span data-ttu-id="07d7b-145">`--validation-dataset | -v`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-145">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="07d7b-146">유효성 검사 데이터 세트 파일을 가리키는 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-146">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="07d7b-147">어떠한 경우에도 유효성 검사 데이터 세트는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-147">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="07d7b-148">`validation dataset`를 사용할 경우 동작은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-148">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="07d7b-149">`test-dataset` 및 `--dataset` 인수도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-149">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="07d7b-150">`validation-dataset` 데이터 세트는 모델 선택에 대한 예측 오류를 예상하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-150">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="07d7b-151">`test-dataset`는 최종 선택된 모델의 일반화 오류를 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-151">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="07d7b-152">이상적으로, 테스트 세트는 “자격 증명 모음”에 보관되어야 하며 데이터 분석이 끝날 때만 꺼내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-152">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="07d7b-153">기본적으로 `validation dataset` 및 `test dataset`를 사용할 경우 유효성 검사 단계는 다음 두 부분으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-153">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="07d7b-154">첫 번째 부분에서는 모델을 살펴 보고 유효성 검사 데이터(=유효성 검사)를 사용하는 가장 효과적인 접근법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-154">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="07d7b-155">그런 다음, 선택한 접근법의 정확도를 추정합니다(=테스트).</span><span class="sxs-lookup"><span data-stu-id="07d7b-155">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="07d7b-156">따라서 데이터는 80/10/10 또는 75/15/10으로 분리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-156">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="07d7b-157">예:</span><span class="sxs-lookup"><span data-stu-id="07d7b-157">For example:</span></span>

- <span data-ttu-id="07d7b-158">`training-dataset` 파일에는 데이터의 75%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-158">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="07d7b-159">`validation-dataset` 파일에는 데이터의 15%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-159">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="07d7b-160">`test-dataset` 파일에는 데이터의 10%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-160">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="07d7b-161">어떠한 경우에도 이러한 백분율은 이미 분할된 파일을 제공할 CLI를 사용하는 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-161">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column-name"></a><span data-ttu-id="07d7b-162">레이블 열 이름</span><span class="sxs-lookup"><span data-stu-id="07d7b-162">Label column name</span></span>

<span data-ttu-id="07d7b-163">`--label-column-name | -n`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-163">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="07d7b-164">이 인수를 사용하면 특정 목표/대상 열(예측하려는 변수)은 데이터 세트의 헤더에서 지정된 열 이름을 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-164">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="07d7b-165">이 인수는 *분류 문제* 등의 감독된 ML 작업에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-165">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="07d7b-166">*클러스터링* 등의 감독되지 않은 ML 작업에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-166">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="label-column-index"></a><span data-ttu-id="07d7b-167">레이블 열 인덱스</span><span class="sxs-lookup"><span data-stu-id="07d7b-167">Label column index</span></span>

<span data-ttu-id="07d7b-168">`--label-column-index | -i`(int)</span><span class="sxs-lookup"><span data-stu-id="07d7b-168">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="07d7b-169">이 인수를 사용하면 특정 목표/대상 열(예측하려는 변수)은 데이터 세트 파일에서 열의 숫자 인덱스(열 인덱스 값은 1에서 시작)를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="07d7b-170">*참고:* 또한 사용자가 `--label-column-name`을 사용하고 있는 경우 `--label-column-name`도 사용되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-170">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="07d7b-171">이 인수는 *분류 문제* 등의 감독된 ML 작업에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-171">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="07d7b-172">*클러스터링* 등의 감독되지 않은 ML 작업에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-172">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="07d7b-173">열 무시</span><span class="sxs-lookup"><span data-stu-id="07d7b-173">Ignore columns</span></span>

<span data-ttu-id="07d7b-174">`--ignore-columns | -I`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-174">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="07d7b-175">이 인수를 사용하면 훈련 프로세스에서 로드되어 사용되지 않도록 데이터 세트 파일에서 기존 열을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-175">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="07d7b-176">무시하려는 열 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-176">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="07d7b-177">', '(공백이 있는 쉼표) 또는 ' '(공백)을 사용하여 여러 열 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-177">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="07d7b-178">공백이 있는 열 이름에 큰따옴표를 사용할 수 있습니다(예: "logged in").</span><span class="sxs-lookup"><span data-stu-id="07d7b-178">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="07d7b-179">예:</span><span class="sxs-lookup"><span data-stu-id="07d7b-179">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="07d7b-180">헤더 있음</span><span class="sxs-lookup"><span data-stu-id="07d7b-180">Has header</span></span>

<span data-ttu-id="07d7b-181">`--has-header | -h`(bool)</span><span class="sxs-lookup"><span data-stu-id="07d7b-181">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="07d7b-182">데이터 세트 파일에 헤더 행이 있는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-182">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="07d7b-183">가능한 값은</span><span class="sxs-lookup"><span data-stu-id="07d7b-183">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="07d7b-184">사용자가 이 인수를 지정하지 않은 경우 기본 값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-184">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="07d7b-185">`--label-column-name` 인수를 사용하려면 데이터 세트 파일에 헤더가 있고 `--has-header`가 `true`로 설정되어 있어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="07d7b-185">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

## <a name="max-exploration-time"></a><span data-ttu-id="07d7b-186">최대 탐색 시간</span><span class="sxs-lookup"><span data-stu-id="07d7b-186">Max exploration time</span></span>

<span data-ttu-id="07d7b-187">`--max-exploration-time | -x`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-187">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="07d7b-188">기본적으로, 최대 검색 시간은 30분입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-188">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="07d7b-189">이 인수는 프로세스에서 여러 트레이너와 구성을 검색하는 최대 시간(초 단위)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-189">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="07d7b-190">단일 반복에 지정된 시간이 너무 짧을 경우(예를 들어 2초) 구성된 값이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-190">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="07d7b-191">이 경우에 실제 시간은 단일 반복에서 하나의 모델 구성을 생성하는 데 필요한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-191">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="07d7b-192">반복에 필요한 시간은 데이터 세트의 크기에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-192">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="07d7b-193">캐시</span><span class="sxs-lookup"><span data-stu-id="07d7b-193">Cache</span></span>

<span data-ttu-id="07d7b-194">`--cache | -c`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="07d7b-195">캐싱을 사용할 경우 전체 학습 데이터 세트는 메모리에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="07d7b-196">중소 규모의 데이터 세트의 경우, 캐시를 사용하면 학습 성능을 크게 개선할 수 있습니다. 즉, 캐시를 사용하지 않을 때보다 학습 시간을 단축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="07d7b-197">단, 대규모 데이터 세트의 경우 메모리에 모든 데이터를 로드하면 메모리가 부족해져 좋지 않은 영향을 끼칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="07d7b-198">대규모 데이터 세트 파일로 학습하고 캐시를 사용하지 않을 경우 ML.NET은 학습하는 동안 더 많은 데이터를 로드해야 할 때 드라이브에서 데이터 청크를 스트리밍하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="07d7b-199">다음 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-199">You can specify the following values:</span></span>

<span data-ttu-id="07d7b-200">`on`: 학습 시 캐시를 사용하도록 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="07d7b-201">`off`: 학습 시 캐시를 사용하지 않도록 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="07d7b-202">`auto`: AutoML 추론에 따라 캐시는 사용되거나 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="07d7b-203">일반적으로, 중/소 규모의 데이터 세트는 캐시를 사용하고 대규모 데이터 세트는 사용자가 `auto` 선택을 사용할 경우 캐시를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="07d7b-204">`--cache` 매개 변수를 지정하지 않는다면 캐시 `auto` 구성이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="07d7b-205">이름</span><span class="sxs-lookup"><span data-stu-id="07d7b-205">Name</span></span>

<span data-ttu-id="07d7b-206">`--name | -N`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-206">`--name | -N` (string)</span></span>

<span data-ttu-id="07d7b-207">생성된 출력 프로젝트 또는 솔루션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-207">The name for the created output project or solution.</span></span> <span data-ttu-id="07d7b-208">지정된 이름이 없을 경우 `sample-{mltask}`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-208">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="07d7b-209">ML.NET 모델 파일(.ZIP 파일)도 같은 이름을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-209">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="07d7b-210">출력 경로</span><span class="sxs-lookup"><span data-stu-id="07d7b-210">Output path</span></span>

<span data-ttu-id="07d7b-211">`--output-path | -o`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-211">`--output-path | -o` (string)</span></span>

<span data-ttu-id="07d7b-212">생성된 출력을 저장할 루트 위치/폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-212">Root location/folder to place the generated output.</span></span> <span data-ttu-id="07d7b-213">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-213">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="07d7b-214">자세한 정도</span><span class="sxs-lookup"><span data-stu-id="07d7b-214">Verbosity</span></span>

<span data-ttu-id="07d7b-215">`--verbosity | -V`(문자열)</span><span class="sxs-lookup"><span data-stu-id="07d7b-215">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="07d7b-216">표준 출력의 자세한 정도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-216">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="07d7b-217">허용된 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-217">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="07d7b-218">`m[inimal]`(기본값)</span><span class="sxs-lookup"><span data-stu-id="07d7b-218">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="07d7b-219">`diag[nostic]`(로깅 정보 수준)</span><span class="sxs-lookup"><span data-stu-id="07d7b-219">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="07d7b-220">기본적으로, CLI 도구는 작동 중인지 그리고, 가능하면 남은 시간 또는 완료된 시간 비율을 언급하는 등, 일부 최소 피드백(최소)을 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-220">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="07d7b-221">도움말</span><span class="sxs-lookup"><span data-stu-id="07d7b-221">Help</span></span>

`-h|--help`

<span data-ttu-id="07d7b-222">각 명령의 매개 변수에 대한 설명과 함께 명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="07d7b-222">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="07d7b-223">참조</span><span class="sxs-lookup"><span data-stu-id="07d7b-223">See also</span></span>

- [<span data-ttu-id="07d7b-224">ML.NET CLI 도구를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="07d7b-224">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="07d7b-225">ML.NET CLI 개요</span><span class="sxs-lookup"><span data-stu-id="07d7b-225">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="07d7b-226">자습서: ML.NET CLI를 사용하여 감정 분석</span><span class="sxs-lookup"><span data-stu-id="07d7b-226">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="07d7b-227">ML.NET CLI의 원격 분석</span><span class="sxs-lookup"><span data-stu-id="07d7b-227">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

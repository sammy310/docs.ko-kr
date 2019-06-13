---
title: ML.NET CLI 도구의 auto-train 명령
description: ML.NET CLI 도구의 auto-train 명령에 대한 개요, 샘플 및 참조입니다.
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: ce5994f392c492e80676b9e65ce54fe010cf03ab
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722606"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a><span data-ttu-id="a1b2f-103">ML.NET CLI의 'auto-train' 명령</span><span class="sxs-lookup"><span data-stu-id="a1b2f-103">The 'auto-train' command in ML.NET CLI</span></span>

> [!NOTE]
> <span data-ttu-id="a1b2f-104">이 항목은 현재 미리 보기 중인 ML.NET CLI 및 ML.NET AutoML에 대해 다루며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-104">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="a1b2f-105">`auto-train` 명령은 ML.NET CLI 도구에서 제공하는 주 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-105">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="a1b2f-106">이 명령을 사용하면 좋은 품질의 ML.NET 모델(연속된 모델 .zip 파일)과 해당 모델을 실행/채점할 예제 C# 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-106">The command allows you to generate a good quality ML.NET model (serialized model .zip file) plus the example C# code to run/score that model.</span></span> <span data-ttu-id="a1b2f-107">또한, 사용자가 일반화된 “최적 모델”에 사용 중인 알고리즘과 설정을 살펴볼 수 있도록 해당 모델을 생성/학습할 C# 코드도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-107">In addition, the C# code to create/train that model is also generated for you to research what algorithm and settings it is using for that generated "best model".</span></span>

<span data-ttu-id="a1b2f-108">직접 코딩하지 않고 자체 데이터 세트에서 이러한 자산을 생성할 수 있으므로, 이미 ML.NET을 알고 있는 경우에도 생산성이 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-108">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="a1b2f-109">현재 ML.NET CLI에서 지원하는 ML 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-109">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`

- <span data-ttu-id="a1b2f-110">이후: 기타 기계 학습 작업, 예:</span><span class="sxs-lookup"><span data-stu-id="a1b2f-110">Future: Other machine learning tasks, such as</span></span>
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

<span data-ttu-id="a1b2f-111">명령 프롬프트에서 사용 예제:</span><span class="sxs-lookup"><span data-stu-id="a1b2f-111">Example of usage on the command prompt:</span></span>

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="a1b2f-112">`mlnet auto-train` 명령은 다음 자산을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-112">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="a1b2f-113">사용 준비가 된 Serialize된 모델 .zip("최적 모델")</span><span class="sxs-lookup"><span data-stu-id="a1b2f-113">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="a1b2f-114">해당 생성된 모델을 실행/채점할 C# 코드(해당 모델으로 최종 사용자 앱에서 예측하기 위한)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-114">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
- <span data-ttu-id="a1b2f-115">해당 모델(학습 목적)을 생성하기 위해 사용한 학습 코드가 포함된 C# 코드</span><span class="sxs-lookup"><span data-stu-id="a1b2f-115">C# code with the training code used to generate that model (Learning purposes).</span></span>

<span data-ttu-id="a1b2f-116">처음 두 개의 자산은 생성된 ML 모델로 예측을 수행하기 위해 최종 사용자 앱(ASP.NET Core 웹앱, 서비스, 데스크톱 앱 등)에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-116">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="a1b2f-117">세 번째 자산 학습 코드는 생성된 모델을 학습하기 위해 CLI에서 사용한 ML.NET API 코드를 보여주므로, CLI 및 ML.NET AutoML 엔진에서 선택한 특정 트레이너/알고리즘과 하이퍼 매개 변수를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-117">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-paramenters were selected by the CLI and the ML.NET AutoML engine.</span></span>

## <a name="the-auto-train-command-uses-the-automl-engine"></a><span data-ttu-id="a1b2f-118">'auto-train' 명령은 AutoML 엔진을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-118">The 'auto-train' command uses the AutoML engine</span></span>

<span data-ttu-id="a1b2f-119">CLI는 ML.NET AutoML 엔진(NuGet 패키지)을 사용하여 아래 다이어그램에 표시된 대로 최적 품질 모델을 인텔리전트하게 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-119">The CLI uses the ML.NET AutoML engine (NuGet package) to intelligently search for the best quality models, as shown in the following diagram:</span></span>

<span data-ttu-id="a1b2f-120">![이미지](./media/ml-net-automl-working-diagram.png "ML.NET CLI 내에서 작동하는 AutoML 엔진")</span><span class="sxs-lookup"><span data-stu-id="a1b2f-120">![image](./media/ml-net-automl-working-diagram.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="a1b2f-121">auto-train 명령으로 ML.NET CLI 도구를 실행하면 이 도구가 다양한 알고리즘과 구성 조합으로 많은 반복을 시도하는 것을 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-121">When running the ML.NET CLI tool with the \`auto-train- command, you'll see the tool trying many iterations with different algorithms and combinations of configuration.</span></span>

## <a name="reference-for-auto-train-command"></a><span data-ttu-id="a1b2f-122">'auto-train' 명령에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a1b2f-122">Reference for 'auto-train' command</span></span>

## <a name="examples"></a><span data-ttu-id="a1b2f-123">예제</span><span class="sxs-lookup"><span data-stu-id="a1b2f-123">Examples</span></span>

<span data-ttu-id="a1b2f-124">이진 분류 문제에 가장 간단한 CLI 명령(AutoML은 제공된 데이터에서 대부분의 구성을 추론해야 함):</span><span class="sxs-lookup"><span data-stu-id="a1b2f-124">Simplest CLI command for a binary classification problem (AutoML will need to infer most of the configuration from the provided data):</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="a1b2f-125">회귀 문제에 대한 다른 간단한 CLI 명령:</span><span class="sxs-lookup"><span data-stu-id="a1b2f-125">Another simple CLI command for a regression problem:</span></span>

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="a1b2f-126">학습 데이터 세트, 테스트 데이터 세트 및 추가 사용자 지정 명시적 인수로 이진 분류 모델을 만들고 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-126">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a><span data-ttu-id="a1b2f-127">name</span><span class="sxs-lookup"><span data-stu-id="a1b2f-127">Name</span></span>

<span data-ttu-id="a1b2f-128">`mlnet auto-train` - 제공된 데이터 세트에 따라 여러 모델(‘n’ 반복)을 학습하고 최종적으로 최적 모델을 선택한 후 Serialize된 .zip 파일로 저장하고 채점 및 학습을 위해 관련된 C# 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-128">`mlnet auto-train` - Trains multiple models ('n' iterations) based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a1b2f-129">개요</span><span class="sxs-lookup"><span data-stu-id="a1b2f-129">Synopsis</span></span>

```console
> mlnet auto-train

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

<span data-ttu-id="a1b2f-130">잘못된 입력 옵션을 사용할 경우 CLI 도구는 유효한 입력 목록과 해당 인수가 누락되었음을 설명하는 오류 메시지를 표시합니다(해당하는 경우).</span><span class="sxs-lookup"><span data-stu-id="a1b2f-130">Invalid input options should cause the CLI tool to emit a list of valid inputs and an error message explaining which arg is missing, if that is the case.</span></span>

## <a name="options"></a><span data-ttu-id="a1b2f-131">옵션</span><span class="sxs-lookup"><span data-stu-id="a1b2f-131">Options</span></span>

 ----------------------------------------------------------

<span data-ttu-id="a1b2f-132">`--task | --mltask | -T`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-132">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="a1b2f-133">해결할 ML 문제를 제공하는 단일 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-133">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="a1b2f-134">예를 들어, 다음 작업 중 하나(CLI는 결과적으로 AutoML에서 지원되는 모든 작업을 지원함):</span><span class="sxs-lookup"><span data-stu-id="a1b2f-134">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="a1b2f-135">`regression` - 숫자 값을 예측하기 위해 ML 모델을 사용할지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-135">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="a1b2f-136">`binary-classification` - ML 모델 결과에 두 개의 가능한 범주 부울 값(0 또는 1)이 있는지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-136">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="a1b2f-137">`multiclass-classification` - ML 모델 결과에 여러 개의 가능한 범주 값이 있는지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-137">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="a1b2f-138">이후 릴리스에서는 `recommendations`, `clustering` 및 `ranking` 등의 추가적인 ML 작업 및 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-138">In future releases additional ML Tasks and scenarios such as `recommendations`, `clustering` and `ranking` will be supported.</span></span>

 <span data-ttu-id="a1b2f-139">이 인수에는 단 하나의 ML 작업만 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-139">Only one ML task should be provided in this argument.</span></span>

 ----------------------------------------------------------

<span data-ttu-id="a1b2f-140">`--dataset | -d`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-140">`--dataset | -d` (string)</span></span>

<span data-ttu-id="a1b2f-141">이 인수는 다음 옵션 중 하나에 대한 파일 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-141">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="a1b2f-142">*A: 전체 데이터 세트 파일:* 이 옵션을 사용하고 사용자가 `--test-dataset` 및 `--validation-dataset`를 제공하지 않는다면 교차 유효성 검사(k-fold 등) 또는 자동화된 데이터 분할 접근법은 모델의 유효성 검사를 위해 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-142">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="a1b2f-143">이 경우에 사용자는 데이터 세트 파일 경로를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-143">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="a1b2f-144">*B: 학습 데이터 세트 파일:* 또한 사용자가 모델 유효성 검사에 데이터 세트를 제공하고 있다면(`--test-dataset` 및 옵션으로 `--validation-dataset`) `--dataset` 인수는 “학습 데이터 세트”만 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-144">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="a1b2f-145">예를 들어, 모델 품질의 유효성을 검사하고 정확도 메트릭을 획득하기 위해 80% - 20% 접근법을 사용할 경우 “학습 데이터 세트”는 데이터의 80%, “테스트 데이터 세트”는 데이터의 20%를 차지하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-145">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-146">`--test-dataset | -t`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-146">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="a1b2f-147">테스트 데이터 세트 파일을 가리키는 파일 경로(예: 정확도 메트릭을 획득하기 위해 정규 유효성 검사 수행 시 80% - 20% 접근법을 사용하는 경우)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-147">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="a1b2f-148">`--test-dataset`를 사용한다면 `--dataset`도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-148">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="a1b2f-149">--유효성 검사-데이터 세트가 사용되지 않을 경우 `--test-dataset` 인수는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-149">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="a1b2f-150">이 경우, 사용자는 세 개의 인수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-150">In that case, the user must use the three arguments.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-151">`--validation-dataset | -v`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-151">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="a1b2f-152">유효성 검사 데이터 세트 파일을 가리키는 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-152">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="a1b2f-153">어떠한 경우에도 유효성 검사 데이터 세트는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-153">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="a1b2f-154">`validation dataset`를 사용할 경우 동작은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-154">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="a1b2f-155">`test-dataset` 및 `--dataset` 인수도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-155">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="a1b2f-156">`validation-dataset` 데이터 세트는 모델 선택에 대한 예측 오류를 예상하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-156">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="a1b2f-157">`test-dataset`는 최종 선택된 모델의 일반화 오류를 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-157">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="a1b2f-158">이상적으로, 테스트 세트는 “자격 증명 모음”에 보관되어야 하며 데이터 분석이 끝날 때만 꺼내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-158">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="a1b2f-159">기본적으로 `validation dataset` 및 `test dataset`를 사용할 경우 유효성 검사 단계는 다음 두 부분으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-159">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="a1b2f-160">첫 번째 부분에서는 모델을 살펴 보고 유효성 검사 데이터(=유효성 검사)를 사용하는 가장 효과적인 접근법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-160">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="a1b2f-161">그런 다음, 선택한 접근법의 정확도를 추정합니다(=테스트).</span><span class="sxs-lookup"><span data-stu-id="a1b2f-161">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="a1b2f-162">따라서 데이터는 80/10/10 또는 75/15/10으로 분리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-162">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="a1b2f-163">예:</span><span class="sxs-lookup"><span data-stu-id="a1b2f-163">For example:</span></span>

- <span data-ttu-id="a1b2f-164">`training-dataset` 파일에는 데이터의 75%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-164">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="a1b2f-165">`validation-dataset` 파일에는 데이터의 15%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-165">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="a1b2f-166">`test-dataset` 파일에는 데이터의 10%가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-166">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="a1b2f-167">어떠한 경우에도 이러한 백분율은 이미 분할된 파일을 제공할 CLI를 사용하는 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-167">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-168">`--label-column-name | -n`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-168">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="a1b2f-169">이 인수를 사용하면 특정 목표/대상 열(예측하려는 변수)은 데이터 세트의 헤더에서 지정된 열 이름을 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="a1b2f-170">이 인수는 *분류 문제* 등의 감독된 ML 작업에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-170">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="a1b2f-171">*클러스터링* 등의 감독되지 않은 ML 작업에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-171">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-172">`--label-column-index | -i`(int)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-172">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="a1b2f-173">이 인수를 사용하면 특정 목표/대상 열(예측하려는 변수)은 데이터 세트 파일에서 열의 숫자 인덱스(열 인덱스 값은 1에서 시작)를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-173">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="a1b2f-174">*참고:* 또한 사용자가 `--label-column-name`을 사용하고 있는 경우 `--label-column-name`도 사용되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-174">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="a1b2f-175">이 인수는 *분류 문제* 등의 감독된 ML 작업에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-175">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="a1b2f-176">*클러스터링* 등의 감독되지 않은 ML 작업에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-176">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-177">`--ignore-columns | -I`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-177">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="a1b2f-178">이 인수를 사용하면 훈련 프로세스에서 로드되어 사용되지 않도록 데이터 세트 파일에서 기존 열을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-178">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="a1b2f-179">무시하려는 열 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-179">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="a1b2f-180">', '(공백이 있는 쉼표) 또는 ' '(공백)을 사용하여 여러 열 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-180">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="a1b2f-181">공백이 있는 열 이름에 큰따옴표를 사용할 수 있습니다(예: "logged in").</span><span class="sxs-lookup"><span data-stu-id="a1b2f-181">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="a1b2f-182">예제:</span><span class="sxs-lookup"><span data-stu-id="a1b2f-182">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

<span data-ttu-id="a1b2f-183">`--has-header | -h`(bool)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-183">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="a1b2f-184">데이터 세트 파일에 헤더 행이 있는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-184">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="a1b2f-185">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-185">Possible values are:</span></span>
- `true`
- `false`

<span data-ttu-id="a1b2f-186">사용자가 이 인수를 지정하지 않은 경우 기본 값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-186">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="a1b2f-187">`--label-column-name` 인수를 사용하려면 데이터 세트 파일에 헤더가 있고 `--has-header`가 `true`로 설정되어 있어야 합니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="a1b2f-187">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-188">`--max-exploration-time | -x`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-188">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="a1b2f-189">기본적으로, 최대 검색 시간은 10초입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-189">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="a1b2f-190">이 인수는 프로세스에서 여러 트레이너와 구성을 검색하는 최대 시간(초 단위)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-190">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="a1b2f-191">단일 반복에 지정된 시간이 너무 짧을 경우(예를 들어 2초) 구성된 값이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-191">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="a1b2f-192">이 경우에 실제 시간은 단일 반복에서 하나의 모델 구성을 생성하는 데 필요한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-192">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="a1b2f-193">반복에 필요한 시간은 데이터 세트의 크기에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-193">The needed time for iterations can vary depending on the size of the dataset.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-194">`--cache | -c`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="a1b2f-195">캐싱을 사용할 경우 전체 학습 데이터 세트는 메모리에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="a1b2f-196">중소 규모의 데이터 세트의 경우, 캐시를 사용하면 학습 성능을 크게 개선할 수 있습니다. 즉, 캐시를 사용하지 않을 때보다 학습 시간을 단축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="a1b2f-197">단, 대규모 데이터 세트의 경우 메모리에 모든 데이터를 로드하면 메모리가 부족해져 좋지 않은 영향을 끼칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="a1b2f-198">대규모 데이터 세트 파일로 학습하고 캐시를 사용하지 않을 경우 ML.NET은 학습하는 동안 더 많은 데이터를 로드해야 할 때 드라이브에서 데이터 청크를 스트리밍하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="a1b2f-199">다음 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-199">You can specify the following values:</span></span>

<span data-ttu-id="a1b2f-200">`on`: 학습 시 캐시를 사용하도록 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="a1b2f-201">`off`: 학습 시 캐시를 사용하지 않도록 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="a1b2f-202">`auto`: AutoML 추론에 따라 캐시는 사용되거나 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="a1b2f-203">일반적으로, 중/소 규모의 데이터 세트는 캐시를 사용하고 대규모 데이터 세트는 사용자가 `auto` 선택을 사용할 경우 캐시를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="a1b2f-204">`--cache` 매개 변수를 지정하지 않는다면 캐시 `auto` 구성이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-205">`--name | -N`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-205">`--name | -N` (string)</span></span>

<span data-ttu-id="a1b2f-206">생성된 출력 프로젝트 또는 솔루션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-206">The name for the created output project or solution.</span></span> <span data-ttu-id="a1b2f-207">지정된 이름이 없을 경우 `sample-{mltask}`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-207">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="a1b2f-208">ML.NET 모델 파일(.ZIP 파일)도 같은 이름을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-208">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-209">`--output-path | -o`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-209">`--output-path | -o` (string)</span></span>

<span data-ttu-id="a1b2f-210">생성된 출력을 저장할 루트 위치/폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-210">Root location/folder to place the generated output.</span></span> <span data-ttu-id="a1b2f-211">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-211">The default is the current directory.</span></span>

----------------------------------------------------------

<span data-ttu-id="a1b2f-212">`--verbosity | -V`(문자열)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-212">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="a1b2f-213">표준 출력의 자세한 정도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-213">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="a1b2f-214">허용된 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-214">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="a1b2f-215">`m[inimal]`(기본값)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-215">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="a1b2f-216">`diag[nostic]`(로깅 정보 수준)</span><span class="sxs-lookup"><span data-stu-id="a1b2f-216">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="a1b2f-217">기본적으로, CLI 도구는 작동 중인지 그리고, 가능하면 남은 시간 또는 완료된 시간 비율을 언급하는 등, 일부 최소 피드백(최소)을 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-217">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

----------------------------------------------------------

`-h|--help`

<span data-ttu-id="a1b2f-218">각 명령의 매개 변수에 대한 설명과 함께 명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b2f-218">Prints out help for the command with a description for each command's parameter.</span></span>

----------------------------------------------------------

## <a name="see-also"></a><span data-ttu-id="a1b2f-219">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1b2f-219">See also</span></span>

- [<span data-ttu-id="a1b2f-220">ML.NET CLI 도구 설치 방법</span><span class="sxs-lookup"><span data-stu-id="a1b2f-220">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="a1b2f-221">ML.NET CLI로 모델 학습 자동화</span><span class="sxs-lookup"><span data-stu-id="a1b2f-221">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="a1b2f-222">자습서: ML.NET CLI를 사용하여 이진 분류자 자동 생성</span><span class="sxs-lookup"><span data-stu-id="a1b2f-222">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="a1b2f-223">ML.NET CLI의 원격 분석</span><span class="sxs-lookup"><span data-stu-id="a1b2f-223">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

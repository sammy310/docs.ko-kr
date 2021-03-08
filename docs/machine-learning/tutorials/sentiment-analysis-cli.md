---
title: ML.NET CLI를 사용하여 감정 분석
description: 샘플 데이터 세트에서 ML 모델 및 관련된 C# 모드를 자동으로 생성
author: cesardl
ms.author: cesardl
ms.date: 06/03/2020
ms.custom: mvc,mlnet-tooling
ms.topic: tutorial
ms.openlocfilehash: 47c38bb0b66a6fc08dd319583847dd83baedcd1e
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103701"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a><span data-ttu-id="3a56b-103">ML.NET CLI를 사용하여 감정 분석</span><span class="sxs-lookup"><span data-stu-id="3a56b-103">Analyze sentiment using the ML.NET CLI</span></span>

<span data-ttu-id="3a56b-104">ML.NET CLI를 사용하여 ML.NET 모델 및 기본 C# 코드를 자동으로 생성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-104">Learn how to use ML.NET CLI to automatically generate an ML.NET model and underlying C# code.</span></span> <span data-ttu-id="3a56b-105">구현하려는 기계 학습 작업과 데이터 세트를 제공하고 CLI는 AutoML 엔진을 사용하여 분류 모델뿐만 아니라 모델 생성 및 배포 소스 코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-105">You provide your dataset and the machine learning task you want to implement, and the CLI uses the AutoML engine to create model generation and deployment source code, as well as the classification model.</span></span>

<span data-ttu-id="3a56b-106">이 자습서에서는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-106">In this tutorial, you will do the following steps:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="3a56b-107">선택된 기계 학습 작업에 사용할 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="3a56b-107">Prepare your data for the selected machine learning task</span></span>
> - <span data-ttu-id="3a56b-108">CLI에서 ‘mlnet classification’ 명령 실행</span><span class="sxs-lookup"><span data-stu-id="3a56b-108">Run the 'mlnet classification' command from the CLI</span></span>
> - <span data-ttu-id="3a56b-109">품질 메트릭 결과 검토</span><span class="sxs-lookup"><span data-stu-id="3a56b-109">Review the quality metric results</span></span>
> - <span data-ttu-id="3a56b-110">생성된 C# 코드를 이해하여 애플리케이션에서 모델 사용</span><span class="sxs-lookup"><span data-stu-id="3a56b-110">Understand the generated C# code to use the model in your application</span></span>
> - <span data-ttu-id="3a56b-111">모델 학습에 사용된 생성된 C# 코드 검색</span><span class="sxs-lookup"><span data-stu-id="3a56b-111">Explore the generated C# code that was used to train the model</span></span>

> [!NOTE]
> <span data-ttu-id="3a56b-112">이 항목은 현재 미리 보기 중인 ML.NET CLI 도구를 참조하며 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-112">This topic refers to the ML.NET CLI tool, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="3a56b-113">자세한 내용은 [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a56b-113">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="3a56b-114">ML.NET CLI는 ML.NET의 일부이며, ML.NET 학습 시 .NET 개발자를 위해 ML.NET을 “자유롭게”하여 시작할 때 사용자가 처음부터 코딩할 필요가 없게 하는 것이 기본 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-114">The ML.NET CLI is part of ML.NET and its main goal is to "democratize" ML.NET for .NET developers when learning ML.NET so you don't need to code from scratch to get started.</span></span>

<span data-ttu-id="3a56b-115">어떤 명령-프롬프트(Windows, Mac 또는 Linux)에서도 ML.NET CLI를 실행하여 사용자가 제공하는 학습 데이터 세트에 기반하여 좋은 품질의 ML.NET 모델 및 소스 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-115">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) to generate good quality ML.NET models and source code based on training datasets you provide.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="3a56b-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3a56b-116">Pre-requisites</span></span>

- <span data-ttu-id="3a56b-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1) 이상</span><span class="sxs-lookup"><span data-stu-id="3a56b-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1) or later</span></span>
- <span data-ttu-id="3a56b-118">(선택 사항) [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="3a56b-118">(Optional) [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)</span></span>
- [<span data-ttu-id="3a56b-119">ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="3a56b-119">ML.NET CLI</span></span>](../how-to-guides/install-ml-net-cli.md)

<span data-ttu-id="3a56b-120">Visual Studio 또는 `dotnet run`(.NET Core CLI)으로 생성된 C# 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-120">You can either run the generated C# code projects from Visual Studio or with `dotnet run` (.NET Core CLI).</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="3a56b-121">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="3a56b-121">Prepare your data</span></span>

<span data-ttu-id="3a56b-122">이진 분류 기계 학습 작업인 ‘감정 분석’ 시나리오에 사용한 기존 데이터 세트를 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-122">We are going to use an existing dataset used for a 'Sentiment Analysis' scenario, which is a binary classification machine learning task.</span></span> <span data-ttu-id="3a56b-123">유사한 방식으로 자체 데이터 세트를 사용할 수 있으며 사용자를 위한 모델과 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-123">You can use your own dataset in a similar way, and the model and code will be generated for you.</span></span>

1. <span data-ttu-id="3a56b-124">[The UCI Sentiment Labeled Sentences dataset zip 파일(다음 참고에서 인용 내용 참조)](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)을 다운로드하고 사용자가 선택한 폴더에 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-124">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip it on any folder you choose.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a56b-125">이 자습서의 데이터 세트에서는 다음 데이터 세트를 사용합니다. 'From Group to Individual Labels using Deep Features', Kotzias et al,.</span><span class="sxs-lookup"><span data-stu-id="3a56b-125">The datasets this tutorial uses a dataset from the 'From Group to Individual Labels using Deep Features', Kotzias et al,.</span></span> <span data-ttu-id="3a56b-126">KDD 2015)에서 제공되고 UCI Machine Learning Repository(Dua, D. 및 Karra Taniskidou, E. (2017))에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-126">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="3a56b-127">UCI Machine Learning Repository[http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="3a56b-127">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="3a56b-128">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="3a56b-128">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

2. <span data-ttu-id="3a56b-129">`yelp_labelled.txt` 파일을 이전에 만든 폴더(예: `/cli-test`)에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-129">Copy the `yelp_labelled.txt` file into any folder you previously created (such as `/cli-test`).</span></span>

3. <span data-ttu-id="3a56b-130">기본 설정된 명령 프롬프트를 열고 데이터 세트 파일을 복사한 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-130">Open your preferred command prompt and move to the folder where you copied the dataset file.</span></span> <span data-ttu-id="3a56b-131">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="3a56b-131">For example:</span></span>

    ```console
    cd /cli-test
    ```

    <span data-ttu-id="3a56b-132">Visual Studio Code 등의 텍스트 편집기를 사용하여 `yelp_labelled.txt` 데이터 세트 파일을 열고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-132">Using any text editor such as Visual Studio Code, you can open, and explore the `yelp_labelled.txt` dataset file.</span></span> <span data-ttu-id="3a56b-133">다음과 같은 구조를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-133">You can see that the structure is:</span></span>

    - <span data-ttu-id="3a56b-134">파일에는 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-134">The file has no header.</span></span> <span data-ttu-id="3a56b-135">열의 인덱스를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-135">You will use the column's index.</span></span>

    - <span data-ttu-id="3a56b-136">단 두 개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-136">There are just two columns:</span></span>

        | <span data-ttu-id="3a56b-137">텍스트(열 인덱스 0)</span><span class="sxs-lookup"><span data-stu-id="3a56b-137">Text (Column index 0)</span></span> | <span data-ttu-id="3a56b-138">레이블(열 인덱스 1)</span><span class="sxs-lookup"><span data-stu-id="3a56b-138">Label (Column index 1)</span></span>|
        |--------------------------|-------|
        | <span data-ttu-id="3a56b-139">와우... 여기가 좋았습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-139">Wow... Loved this place.</span></span> | <span data-ttu-id="3a56b-140">1</span><span class="sxs-lookup"><span data-stu-id="3a56b-140">1</span></span> |
        | <span data-ttu-id="3a56b-141">크러스트가 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-141">Crust is not good.</span></span> | <span data-ttu-id="3a56b-142">0</span><span class="sxs-lookup"><span data-stu-id="3a56b-142">0</span></span> |
        | <span data-ttu-id="3a56b-143">맛있지는 않고 식감도 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-143">Not tasty and the texture was just nasty.</span></span> | <span data-ttu-id="3a56b-144">0</span><span class="sxs-lookup"><span data-stu-id="3a56b-144">0</span></span> |
        | <span data-ttu-id="3a56b-145">...더 많은 텍스트 행...</span><span class="sxs-lookup"><span data-stu-id="3a56b-145">...MANY MORE TEXT ROWS...</span></span> | <span data-ttu-id="3a56b-146">...(1 또는 0)...</span><span class="sxs-lookup"><span data-stu-id="3a56b-146">...(1 or 0)...</span></span> |

    <span data-ttu-id="3a56b-147">편집기에서 데이터 세트 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-147">Make sure you close the dataset file from the editor.</span></span>

    <span data-ttu-id="3a56b-148">이제 ‘감정 분석’ 시나리오에 CLI를 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-148">Now, you are ready to start using the CLI for this 'Sentiment Analysis' scenario.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a56b-149">이 자습서를 마친 후에는 ‘이진 분류’, ‘분류’, ‘회귀’ 및 ‘권장 사항’ 등 ML.NET CLI 미리 보기에서 현재 지원되는 ML 작업에 사용할 준비가 되었다면 자체 데이터 세트로 시도해 볼 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3a56b-149">After finishing this tutorial you can also try with your own datasets as long as they are ready to be used for any of the ML tasks currently supported by the ML.NET CLI Preview which are *'Binary Classification', 'Classification', 'Regression',* and *'Recommendation'*.</span></span>

## <a name="run-the-mlnet-classification-command"></a><span data-ttu-id="3a56b-150">‘mlnet classification’ 명령 실행</span><span class="sxs-lookup"><span data-stu-id="3a56b-150">Run the 'mlnet classification' command</span></span>

1. <span data-ttu-id="3a56b-151">다음 ML.NET CLI 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-151">Run the following ML.NET CLI command:</span></span>

    ```console
    mlnet classification --dataset "yelp_labelled.txt" --label-col 1 --has-header false --train-time 10
    ```

    <span data-ttu-id="3a56b-152">이 명령은 **`mlnet classification` 명령** 을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-152">This command runs the **`mlnet classification` command**:</span></span>
    - <span data-ttu-id="3a56b-153">*classification* 의 **ML 작업**</span><span class="sxs-lookup"><span data-stu-id="3a56b-153">for the **ML task** of *classification*</span></span>
    - <span data-ttu-id="3a56b-154">학습 및 테스트 데이터 세트로 **데이터 세트 파일 `yelp_labelled.txt`** 사용(내부적으로 CLI는 교차 유효성 검증을 사용하거나, 하나는 학습, 그리고 하나는 테스트용으로 두 개의 데이터 세트로 분할함)</span><span class="sxs-lookup"><span data-stu-id="3a56b-154">uses the **dataset file `yelp_labelled.txt`** as training and testing dataset (internally the CLI will either use cross-validation or split it in two datasets, one for training and one for testing)</span></span>
    - <span data-ttu-id="3a56b-155">여기서 예측하려는 **목표/대상 열**(일반적으로 **'레이블'** )은 **인덱스 1이 있는 열**(즉, 인덱스가 0 기반이므로 두 번째 열)임</span><span class="sxs-lookup"><span data-stu-id="3a56b-155">where the **objective/target column** you want to predict (commonly called **'label'**) is the **column with index 1** (that is the second column, since the index is zero-based)</span></span>
    - <span data-ttu-id="3a56b-156">이 특정 데이터 세트 파일에는 헤더가 없으므로 열 이름으로 **파일 헤더를 사용하지 않음**</span><span class="sxs-lookup"><span data-stu-id="3a56b-156">does **not use a file header** with column names since this particular dataset file doesn't have a header</span></span>
    - <span data-ttu-id="3a56b-157">실험의 **목표 검색/학습 시간** 은 **10초** 임</span><span class="sxs-lookup"><span data-stu-id="3a56b-157">the **targeted exploration/train time** for the experiment is **10 seconds**</span></span>

    <span data-ttu-id="3a56b-158">CLI의 출력은 다음과 같이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-158">You will see output from the CLI, similar to:</span></span>

    ![PowerShell의 ML.NET CLI 분류](./media/mlnet-cli/mlnet-classification-powershell.gif)

    <span data-ttu-id="3a56b-160">이 특정 사례에서는 단 10초만에, 그리고 제공된 소규모의 데이터 세트를 사용하여 CLI 도구는 아주 적은 반복을 실행할 수 있었습니다. 즉, 다른 내부 데이터 변형과 알고리즘의 하이퍼 매개 변수로 다른 조합의 알고리즘/구성에 기반하여 여러 차례 학습했음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-160">In this particular case, in only 10 seconds and with the small dataset provided, the CLI tool was able to run quite a few iterations, meaning training multiple times based on different combinations of algorithms/configuration with different internal data transformations and algorithm's hyper-parameters.</span></span>

    <span data-ttu-id="3a56b-161">마지막으로, 10초만에 발견된 “최적 품질” 모델은 어떠한 특정 구성으로 특별한 트레이너/알고리즘을 사용하는 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-161">Finally, the "best quality" model found in 10 seconds is a model using a particular trainer/algorithm with any specific configuration.</span></span> <span data-ttu-id="3a56b-162">검색 시간에 따라 명령은 다른 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-162">Depending on the exploration time, the command can produce a different result.</span></span> <span data-ttu-id="3a56b-163">선택은 표시된 다중 메트릭(예: `Accuracy`)에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-163">The selection is based on the multiple metrics shown, such as `Accuracy`.</span></span>

    <span data-ttu-id="3a56b-164">**모델의 품질 메트릭 이해**</span><span class="sxs-lookup"><span data-stu-id="3a56b-164">**Understanding the model's quality metrics**</span></span>

    <span data-ttu-id="3a56b-165">이진 분류 모델을 평가하는 첫 번째 그리고 가장 쉬운 메트릭은 이해하기 간단한 정확도입니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-165">The first and easiest metric to evaluate a binary-classification model is the accuracy, which is simple to understand.</span></span> <span data-ttu-id="3a56b-166">"정확도는 테스트 데이터 세트 사용 시 올바른 예측의 비율입니다.”</span><span class="sxs-lookup"><span data-stu-id="3a56b-166">"Accuracy is the proportion of correct predictions with a test data set.".</span></span> <span data-ttu-id="3a56b-167">100%(1.00)에 가까울 수록 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-167">The closer to 100% (1.00), the better.</span></span>

    <span data-ttu-id="3a56b-168">단, 정확도 메트릭으로 측정하는 것으로 충분하지 않은, 특히 테스트 데이터 세트에서 레이블(이 경우에는 0과 1)의 균형이 맞지 않는 경우가 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-168">However, there are cases where just measuring with the Accuracy metric is not enough, especially when the label (0 and 1 in this case) is unbalanced in the test dataset.</span></span>

    <span data-ttu-id="3a56b-169">다른 모델을 평가하는 데 사용하는 정확도, AUC, AUCPR, F1-점수 등의 **메트릭에 대한 보다 자세한 정보** 와 추가 메트릭은 [ML.NET 메트릭 이해](../resources/metrics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a56b-169">For additional metrics and more **detailed information about the metrics** such as Accuracy, AUC, AUCPR, and F1-score used to evaluate the different models, see [Understanding ML.NET metrics](../resources/metrics.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a56b-170">이 매우 동일한 데이터 세트를 사용해 보고 `--max-exploration-time`에 몇 분을 지정하여(예를 들어, 3분은 180초) 이 데이터 세트에 대한 다른 학습 파이프라인 구성(매우 작음, 1000개 행)에 더 나은 “최적 모델”을 찾게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-170">You can try this very same dataset and specify a few minutes for `--max-exploration-time` (for instance three minutes so you specify 180 seconds) which will find a better "best model" for you with a different training pipeline configuration for this dataset (which is pretty small, 1000 rows).</span></span>

    <span data-ttu-id="3a56b-171">더 큰 데이터 세트를 목표로 하는 “프로덕션 준비 모델”인 “최적/좋은 품질”의 모델을 찾기 위해서는 데이터 세트의 크기에 따라 일반적으로 훨씬 더 많은 검색 시간을 지정하는 CLI로 실험해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-171">In order to find a "best/good quality" model that is a "production-ready model" targeting larger datasets, you should make experiments with the CLI usually specifying much more exploration time depending on the size of the dataset.</span></span> <span data-ttu-id="3a56b-172">사실 대부분의 경우, 특히 데이터 세트의 행과 열이 큰 경우에는 몇 시간의 검색 시간이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-172">In fact, in many cases you might require multiple hours of exploration time especially if the dataset is large on rows and columns.</span></span>

1. <span data-ttu-id="3a56b-173">이전 명령 실행으로 다음 자산을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-173">The previous command execution has generated the following assets:</span></span>

    - <span data-ttu-id="3a56b-174">사용 준비가 된 Serialize된 모델 .zip("최적 모델")</span><span class="sxs-lookup"><span data-stu-id="3a56b-174">A serialized model .zip ("best model") ready to use.</span></span>
    - <span data-ttu-id="3a56b-175">해당 생성된 모델을 실행/채점할 C# 코드(해당 모델으로 최종 사용자 앱에서 예측하기 위한)</span><span class="sxs-lookup"><span data-stu-id="3a56b-175">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="3a56b-176">이 모델을 생성하는 데 사용한 C# 학습 코드(학습 목적)</span><span class="sxs-lookup"><span data-stu-id="3a56b-176">C# training code used to generate that model (Learning purposes).</span></span>
    - <span data-ttu-id="3a56b-177">하이퍼 매개 변수 및 데이터 변형 조합으로 시도한 각 알고리즘에 대한 구체적인 세부 정보가 있는 검색된 모든 반복이 있는 로그 파일</span><span class="sxs-lookup"><span data-stu-id="3a56b-177">A log file with all the iterations explored having specific detailed information about each algorithm tried with its combination of hyper-parameters and data transformations.</span></span>

    <span data-ttu-id="3a56b-178">처음 두 자산(.ZIP 파일 모델과 해당 모델을 실행하기 위한 C# 코드)은 생성된 ML 모델로 예측을 수행하기 위해 최종 사용자 앱(ASP.NET Core 웹앱, 서비스, 데스크톱 앱 등)에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-178">The first two assets (.ZIP file model and C# code to run that model) can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

    <span data-ttu-id="3a56b-179">세 번째 자산인 학습 코드는 사용자에게 생성된 모델을 학습하기 위해 CLI에서 사용한 ML.NET API 코드를 표시하므로, 사용자는 CLI에서 선택한 특정 트레이너/알고리즘 및 하이퍼 매개 변수를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-179">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-parameters were selected by the CLI.</span></span>

<span data-ttu-id="3a56b-180">이러한 열거된 자산은 자습서의 다음 단계에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-180">Those enumerated assets are explained in the following steps of the tutorial.</span></span>

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a><span data-ttu-id="3a56b-181">예측을 수행하기 위해 모델 실행에 사용할 생성된 C# 코드 검색</span><span class="sxs-lookup"><span data-stu-id="3a56b-181">Explore the generated C# code to use for running the model to make predictions</span></span>

1. <span data-ttu-id="3a56b-182">Visual Studio(2017 또는 2019)에서, 원래 대상 폴더(자습서에서 `/cli-test`로 이름이 지정된) 내의 `SampleClassification` 폴더에 생성된 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-182">In Visual Studio (2017 or 2019) open the solution generated in the folder named `SampleClassification` within your original destination folder (in the tutorial was named `/cli-test`).</span></span> <span data-ttu-id="3a56b-183">다음과 유사한 솔루션이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-183">You should see a solution similar to:</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a56b-184">자습서에서는 Visual Studio를 사용하도록 제안하고 있지만 텍스트 편집기를 사용하여, 생성된 C# 코드(두 개의 프로젝트)를 검색하고 macOS, Linux 또는 Windows 머신에서 `dotnet CLI`로 생성된 콘솔 앱을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-184">In the tutorial we suggest to use Visual Studio, but you can also explore the generated C# code (two projects) with any text editor and run the generated console app with the `dotnet CLI` on macOS, Linux or Windows machine.</span></span>

    ![CLI로 생성된 VS 솔루션](./media/mlnet-cli/mlnet-cli-solution-explorer.png)

    - <span data-ttu-id="3a56b-186">Serialize된 ML 모델(.zip 파일)과 데이터 클래스(데이터 모델)를 포함한 생성된 **클래스 라이브러리** 는 클래스 라이브러리를 직접 참조하거나(원한다면 코드를 이동하여) 최종 사용자 애플리케이션에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-186">The generated **class library** containing the serialized ML model (.zip file) and the data classes (data models) is something you can directly use in your end-user application, even by directly referencing that class library (or moving the code, as you prefer).</span></span>
    - <span data-ttu-id="3a56b-187">생성된 **콘솔 앱** 에는 사용자가 검토해야 하는 실행 코드가 있습니다. 그런 다음, 사용자가 예측하려는 최종 사용자 애플리케이션으로 해당 단순 코드(단 몇 개의 줄)를 이동하여 ‘채점 코드’(예측하기 위해 ML 모델을 실행하는 코드)를 재사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-187">The generated **console app** contains execution code that you must review and then you usually reuse the 'scoring code' (code that runs the ML model to make predictions) by moving that simple code (just a few lines) to your end-user application where you want to make the predictions.</span></span>

1. <span data-ttu-id="3a56b-188">클래스 라이브러리 프로젝트에서 **ModelInput.cs** 및 **ModelOutput.cs** 클래스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-188">Open the **ModelInput.cs** and **ModelOutput.cs** class files within the class library project.</span></span> <span data-ttu-id="3a56b-189">이러한 클래스는 데이터를 보유하기 위해 사용하는 ‘데이터 클래스’ 또는 POCO 클래스임을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-189">You will see that these classes are 'data classes' or POCO classes used to hold data.</span></span> <span data-ttu-id="3a56b-190">'상용구 코드’지만 데이터 세트에 수십 또는 수백 개의 열이 있는 경우 생성하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-190">It is 'boilerplate code' but useful to have it generated if your dataset has tens or even hundreds of columns.</span></span>
    - <span data-ttu-id="3a56b-191">`ModelInput` 클래스는 데이터 세트에서 데이터를 읽을 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-191">The `ModelInput` class is used when reading data from the dataset.</span></span>
    - <span data-ttu-id="3a56b-192">`ModelOutput` 클래스는 예측 결과(예측 데이터)를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-192">The `ModelOutput` class is used to get the prediction result (prediction data).</span></span>

1. <span data-ttu-id="3a56b-193">Program.cs 파일을 열고 코드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-193">Open the Program.cs file and explore the code.</span></span> <span data-ttu-id="3a56b-194">단 몇 개의 줄로 모델을 실행하고 단순 예측을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-194">In just a few lines, you are able to run the model and make a sample prediction.</span></span>

    ```csharp
    static void Main(string[] args)
    {
        // Create single instance of sample data from first line of dataset for model input
        ModelInput sampleData = new ModelInput()
        {
            Col0 = @"Wow... Loved this place.",
        };

        // Make a single prediction on the sample data and print results
        var predictionResult = ConsumeModel.Predict(sampleData);

        Console.WriteLine("Using model to make single prediction -- Comparing actual Col1 with predicted Col1 from sample data...\n\n");
        Console.WriteLine($"Col0: {sampleData.Col0}");
        Console.WriteLine($"\n\nPredicted Col1 value {predictionResult.Prediction} \nPredicted Col1 scores: [{String.Join(",", predictionResult.Score)}]\n\n");
        Console.WriteLine("=============== End of process, hit any key to finish ===============");
        Console.ReadKey();
    }
    ```

    - 첫 번째 코드 줄은 ‘단일 샘플 데이터’를 만들며, 이 경우에는 예측에 사용할 데이터 세트의 첫 번째 행을 기반으로 합니다. <span data-ttu-id="3a56b-196">코드를 업데이트하여 ‘하드 코드된’ 데이터를 직접 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-196">You can also create you own 'hard-coded' data by updating the code:</span></span>

        ```csharp
        ModelInput sampleData = new ModelInput()
        {
            Col0 = "The ML.NET CLI is great for getting started. Very cool!"
        };
        ```

    - <span data-ttu-id="3a56b-197">다음 코드 줄에서는 지정된 입력 데이터의 `ConsumeModel.Predict()` 메서드를 사용하여 예측을 만들고 결과를 반환합니다(ModelOutput.cs 스키마 기반).</span><span class="sxs-lookup"><span data-stu-id="3a56b-197">The next line of code uses the `ConsumeModel.Predict()` method on the specified input data to make a prediction and return the results (based on the ModelOutput.cs schema).</span></span>
    - <span data-ttu-id="3a56b-198">코드의 마지막 줄은 샘플 데이터의 속성(이 경우 주석)뿐만 아니라 감정 예측 및 긍정 감정 (1) 및 부정 감정 (2)에 해당하는 점수를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-198">The last lines of code print out the properties of the sample data (in this case the Comment) as well as the Sentiment prediction and corresponding Scores for positive sentiment (1) and negative sentiment (2).</span></span>

1. <span data-ttu-id="3a56b-199">데이터 세트의 첫 번째 행에서 로드된 원래 샘플 데이터를 사용하거나 자체 사용자 지정 하드 코드된 샘플 데이터를 제공하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-199">Run the project, either using the original sample data loaded from the first row of the dataset or by providing your own custom hard-coded sample data.</span></span> <span data-ttu-id="3a56b-200">다음과 견줄만한 예측을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-200">You should get a prediction comparable to:</span></span>

![ML.NET CLI가 Visual Studio에서 앱 실행](./media/mlnet-cli/mlnet-cli-console-app.png)<span data-ttu-id="3a56b-202">)</span><span class="sxs-lookup"><span data-stu-id="3a56b-202">)</span></span>

1. <span data-ttu-id="3a56b-203">하드 코드된 샘플 데이터를 다른 감정의 다른 문장으로 변경해 보고 모델이 긍정 또는 부정적인 감정을 예측하는 방식을 살펴 봅니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-203">Try changing the hard-coded sample data to other sentences with different sentiment and see how the model predicts positive or negative sentiment.</span></span>

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a><span data-ttu-id="3a56b-204">최종 사용자 애플리케이션에 ML 모델 예측 입력</span><span class="sxs-lookup"><span data-stu-id="3a56b-204">Infuse your end-user applications with ML model predictions</span></span>

<span data-ttu-id="3a56b-205">유사한 ‘ML 모델 채점 코드’를 사용하여 최종 사용자 애플리케이션에서 모델을 실행하고 예측을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-205">You can use similar 'ML model scoring code' to run the model in your end-user application and make predictions.</span></span>

<span data-ttu-id="3a56b-206">예를 들어 이 코드를 **WPF** 및 **WinForms** 등의 Windows 데스크톱 애플리케이션으로 직접 이동하고 콘솔 앱에서 실행된 것과 동일한 방식으로 모델을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-206">For instance, you could directly move that code to any Windows desktop application such as **WPF** and **WinForms** and run the model in the same way than it was done in the console app.</span></span>

<span data-ttu-id="3a56b-207">그러나 ML 모델을 실행하기 위해 이러한 코드 줄을 구현하는 방식은 최적화되어야 하며(즉, 모델 .zip 파일을 캐싱하고 한 번 로드), 특히 다음 섹션에서 설명된 대로 웹 애플리케이션 또는 분산 서비스와 같이 애플리케이션이 확장 가능해야 하는 경우에는 모든 요청마다 만드는 대신, 싱글톤 개체가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-207">However, the way you implement those lines of code to run an ML model should be optimized (that is, cache the model .zip file and load it once) and have singleton objects instead of creating them on every request, especially if your application needs to be scalable such as a web application or distributed service, as explained in the following section.</span></span>

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a><span data-ttu-id="3a56b-208">확장 가능한 ASP.NET Core 웹앱 및 서비스(다중 스레드 앱)에서 ML.NET 모델 실행</span><span class="sxs-lookup"><span data-stu-id="3a56b-208">Running ML.NET models in scalable ASP.NET Core web apps and services (multi-threaded apps)</span></span>

<span data-ttu-id="3a56b-209">모델 개체(모델의 .zip 파일에서 로드한 `ITransformer`) 및 `PredictionEngine` 개체 만들기는 특히 확장 가능한 웹앱과 분산 서비스에서 실행할 경우 최적화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-209">The creation of the model object (`ITransformer` loaded from a model's .zip file) and the `PredictionEngine` object should be optimized especially when running on scalable web apps and distributed services.</span></span> <span data-ttu-id="3a56b-210">첫 번째 경우, 모델 개체(`ITransformer`)에서 최적화는 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-210">For the first case, the model object (`ITransformer`) the optimization is straightforward.</span></span> <span data-ttu-id="3a56b-211">`ITransformer` 개체는 스레드로부터 안전하므로, 한 번에 모델을 로드할 수 있도록 싱글톤 또는 정적 개체로 해당 개체를 캐싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-211">Since the `ITransformer` object is thread-safe, you can cache the object as a singleton or static object so you load the model once.</span></span>

<span data-ttu-id="3a56b-212">두 번째 개체, `PredictionEngine` 개체의 경우 `PredictionEngine` 개체가 스레드로부터 안전하지 않아 이 개체를 ASP.NET Core 앱에서 싱글톤 또는 정적 개체로 인스턴스화할 수 없으므로 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-212">For the second object, the `PredictionEngine` object, it is not so easy because the `PredictionEngine` object is not thread-safe, therefore you cannot instantiate this object as singleton or static object in an ASP.NET Core app.</span></span> <span data-ttu-id="3a56b-213">이 스레드로부터 안전한, 그리고 확장성 문제는 [블로그 게시물](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/)에서 자세히 다루고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-213">This thread-safe and scalability problem is deeply discussed in this [Blog Post](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>

<span data-ttu-id="3a56b-214">그러나 블로그 게시물에 설명된 것보다 훨씬 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-214">However, things got a lot easier for you than what's explained in that blog post.</span></span> <span data-ttu-id="3a56b-215">사용자를 위해 보다 단순한 접근법에 노력을 기울였으며 애플리케이션 DI 서비스(종속성 주입 서비스)에서 등록하여 ASP.NET Core 앱 및 서비스에서 쉽게 사용한 다음, 사용자 코드에서 직접 사용할 수 있는 괜찮은 **'.NET Core 통합 패키지'** 를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-215">We worked on a simpler approach for you and have created a nice **'.NET Core Integration Package'** that you can  easily use in your ASP.NET Core apps and services by registering it in the application DI services (Dependency Injection services) and then directly use it from your code.</span></span> <span data-ttu-id="3a56b-216">다음 자습서와 수행 예제를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3a56b-216">Check the following tutorial and example for doing that:</span></span>

- [<span data-ttu-id="3a56b-217">자습서: ASP.NET Core 웹앱 및 WebAPI에서 ML.NET 모델 실행</span><span class="sxs-lookup"><span data-stu-id="3a56b-217">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)
- [<span data-ttu-id="3a56b-218">샘플: ASP.NET Core WebAPI의 확장 가능한 ML.NET 모델</span><span class="sxs-lookup"><span data-stu-id="3a56b-218">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a><span data-ttu-id="3a56b-219">“최적 품질” 모델을 학습하기 위해 사용한 생성된 C# 코드 검색</span><span class="sxs-lookup"><span data-stu-id="3a56b-219">Explore the generated C# code that was used to train the "best quality" model</span></span>

<span data-ttu-id="3a56b-220">보다 고급의 학습 목적을 위해 생성된 모델을 학습하기 위해 CLI 도구에서 사용한 생성된 C# 코드를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-220">For more advanced learning purposes, you can also explore the generated C# code that was used by the CLI tool to train the generated model.</span></span>

<span data-ttu-id="3a56b-221">이 ‘학습 모델 코드’는 현재 이름이 `ModelBuilder`인 생성된 사용자 지정 클래스에 생성되어 있으므로, 이 학습 코드를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-221">That 'training model code' is currently generated in the custom class generated named `ModelBuilder` so you can investigate that training code.</span></span>

<span data-ttu-id="3a56b-222">무엇보다도 이 특별한 시나리오(감정 분석 모델)의 경우 다음 자습서에 설명된 코드와 생성된 학습 코드를 비교할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-222">More importantly, for this particular scenario (Sentiment Analysis model) you can also compare that generated training code with the code explained in the following tutorial:</span></span>

- <span data-ttu-id="3a56b-223">비교: [자습서: 감정 분석 이진 분류 시나리오에서 ML.NET 사용](sentiment-analysis.md)</span><span class="sxs-lookup"><span data-stu-id="3a56b-223">Compare: [Tutorial: Use ML.NET in a sentiment analysis binary classification scenario](sentiment-analysis.md).</span></span>

<span data-ttu-id="3a56b-224">CLI 도구를 통해 생성된 코드와 자습서에서 선택된 알고리즘 및 파이프라인 구성을 비교하는 것이 흥미롭습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-224">It is interesting to compare the chosen algorithm and pipeline configuration in the tutorial with the code generated by the CLI tool.</span></span> <span data-ttu-id="3a56b-225">더 나은 모델을 찾기 위해 반복하고 검색하는 데 소요된 시간에 따라, 선택된 알고리즘은 특정 하이퍼 매개 변수 및 파이프라인 구성과 함께 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-225">Depending on how much time you spend iterating and searching for better models, the chosen algorithm might be different along with its particular hyper-parameters and pipeline configuration.</span></span>

<span data-ttu-id="3a56b-226">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a56b-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="3a56b-227">선택한 ML 작업(해결할 문제)에 사용할 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="3a56b-227">Prepare your data for the selected ML task (problem to solve)</span></span>
> - <span data-ttu-id="3a56b-228">CLI 도구에서 ‘mlnet classification’ 명령 실행</span><span class="sxs-lookup"><span data-stu-id="3a56b-228">Run the 'mlnet classification' command in the CLI tool</span></span>
> - <span data-ttu-id="3a56b-229">품질 메트릭 결과 검토</span><span class="sxs-lookup"><span data-stu-id="3a56b-229">Review the quality metric results</span></span>
> - <span data-ttu-id="3a56b-230">모델을 실행하기 위해 생성된 C# 코드(최종 사용자 앱에서 사용할 코드) 이해</span><span class="sxs-lookup"><span data-stu-id="3a56b-230">Understand the generated C# code to run the model (Code to use in your end-user app)</span></span>
> - <span data-ttu-id="3a56b-231">“최적 품질” 모델(학습 목적)을 학습시키기 위해 사용한 생성된 C# 코드 검색</span><span class="sxs-lookup"><span data-stu-id="3a56b-231">Explore the generated C# code that was used to train the "best quality" model (earning purposes)</span></span>

## <a name="see-also"></a><span data-ttu-id="3a56b-232">참조</span><span class="sxs-lookup"><span data-stu-id="3a56b-232">See also</span></span>

- [<span data-ttu-id="3a56b-233">ML.NET CLI로 모델 학습 자동화</span><span class="sxs-lookup"><span data-stu-id="3a56b-233">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="3a56b-234">자습서: ASP.NET Core 웹앱 및 WebAPI에서 ML.NET 모델 실행</span><span class="sxs-lookup"><span data-stu-id="3a56b-234">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)
- [<span data-ttu-id="3a56b-235">샘플: ASP.NET Core WebAPI의 확장 가능한 ML.NET 모델</span><span class="sxs-lookup"><span data-stu-id="3a56b-235">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [<span data-ttu-id="3a56b-236">ML.NET CLI auto-train 명령 참조 가이드</span><span class="sxs-lookup"><span data-stu-id="3a56b-236">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="3a56b-237">ML.NET CLI의 원격 분석</span><span class="sxs-lookup"><span data-stu-id="3a56b-237">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

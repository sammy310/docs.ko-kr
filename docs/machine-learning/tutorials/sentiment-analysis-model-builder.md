---
title: '자습서: 감정 분석 - 이진 분류'
description: 이 자습서에서는 웹 사이트 주석에서 감정을 분류하고 적절한 조치를 취하는 Razor Pages 애플리케이션을 만드는 방법을 보여 줍니다. 감정 이진 분류자는 Visual Studio에서 모델 작성기를 사용합니다.
ms.date: 11/21/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: 7761240055c90ae9c713b1c460e9e83316d256f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/29/2020
ms.locfileid: "81278953"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="bf5c2-104">자습서: ML.NET 모델 작성기를 사용하여 웹 애플리케이션에서 웹 사이트 댓글 감정 분석</span><span class="sxs-lookup"><span data-stu-id="bf5c2-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="bf5c2-105">웹 애플리케이션에서 실시간으로 댓글의 감정을 분석하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-105">Learn how to analyze sentiment from comments in real time inside a web application.</span></span>

<span data-ttu-id="bf5c2-106">이 자습서에서는 실시간으로 웹 사이트 댓글에서 감정을 분류하는 ASP.NET Core Razor Pages 애플리케이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real time.</span></span>

<span data-ttu-id="bf5c2-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="bf5c2-108">ASP.NET Core Razor Pages 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="bf5c2-108">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="bf5c2-109">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="bf5c2-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="bf5c2-110">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="bf5c2-110">Choose a scenario</span></span>
> - <span data-ttu-id="bf5c2-111">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="bf5c2-111">Load the data</span></span>
> - <span data-ttu-id="bf5c2-112">모델 학습</span><span class="sxs-lookup"><span data-stu-id="bf5c2-112">Train the model</span></span>
> - <span data-ttu-id="bf5c2-113">모델 평가</span><span class="sxs-lookup"><span data-stu-id="bf5c2-113">Evaluate the model</span></span>
> - <span data-ttu-id="bf5c2-114">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="bf5c2-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="bf5c2-115">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="bf5c2-116">[dotnet/samples](https://github.com/dotnet/machinelearning-samples) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="bf5c2-117">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bf5c2-117">Pre-requisites</span></span>

<span data-ttu-id="bf5c2-118">필수 구성 요소 및 설치 지침 목록을 보려면 [모델 작성기 설치 가이드](../how-to-guides/install-model-builder.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="bf5c2-119">Razor Pages 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="bf5c2-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="bf5c2-120">**ASP.NET Core Razor Pages 애플리케이션** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="bf5c2-121">Visual Studio를 열고 메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span>
    1. <span data-ttu-id="bf5c2-122">[새 프로젝트] 대화 상자에서 **Visual C#** 노드와 **Web** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span>
    1. <span data-ttu-id="bf5c2-123">그런 다음, **ASP.NET Core 웹 애플리케이션** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-123">Then select the **ASP.NET Core Web Application** project template.</span></span>
    1. <span data-ttu-id="bf5c2-124">**이름** 텍스트 상자에 "SentimentRazor"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="bf5c2-125">**솔루션 및 프로젝트를 같은 디렉터리에 배치** 가 **선택 취소** 되었는지(VS 2019) 또는 **솔루션의 디렉터리 만들기** 가 **선택되었는지**(VS 2017)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-125">Make sure **Place solution and project in the same directory** is **unchecked** (VS 2019), or **Create directory for solution** is **checked** (VS 2017).</span></span>
    1. <span data-ttu-id="bf5c2-126">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-126">Select the **OK** button.</span></span>
    1. <span data-ttu-id="bf5c2-127">다른 유형의 ASP.NET Core 프로젝트를 표시하는 창에서 **웹 애플리케이션** 을 선택하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-127">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="bf5c2-128">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="bf5c2-128">Prepare and understand the data</span></span>

<span data-ttu-id="bf5c2-129">[Wikipedia detox 데이터 세트](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-129">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="bf5c2-130">웹 페이지가 열리면 페이지를 마우스 오른쪽 단추로 클릭하고 **다른 이름으로 저장** 을 선택하여 컴퓨터의 아무 위치에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-130">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span>

<span data-ttu-id="bf5c2-131">*wikipedia-detox-250-line-data.tsv* 데이터 세트의 각 행은 사용자가 Wikipedia에 남긴 다른 검토를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-131">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="bf5c2-132">첫 번째 열은 텍스트의 감정(0은 무해, 1은 유해)를 나타내고, 두 번째 열은 사용자가 남긴 댓글을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-132">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="bf5c2-133">열은 탭으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-133">The columns are separated by tabs.</span></span> <span data-ttu-id="bf5c2-134">데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-134">The data looks like the following:</span></span>

| <span data-ttu-id="bf5c2-135">감정</span><span class="sxs-lookup"><span data-stu-id="bf5c2-135">Sentiment</span></span> | <span data-ttu-id="bf5c2-136">SentimentText</span><span class="sxs-lookup"><span data-stu-id="bf5c2-136">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="bf5c2-137">1</span><span class="sxs-lookup"><span data-stu-id="bf5c2-137">1</span></span> | <span data-ttu-id="bf5c2-138">==RUDE== Dude, you are rude upload that carl picture back, or else.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-138">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="bf5c2-139">1</span><span class="sxs-lookup"><span data-stu-id="bf5c2-139">1</span></span> | <span data-ttu-id="bf5c2-140">== OK!</span><span class="sxs-lookup"><span data-stu-id="bf5c2-140">== OK!</span></span> <span data-ttu-id="bf5c2-141">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span><span class="sxs-lookup"><span data-stu-id="bf5c2-141">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="bf5c2-142">0</span><span class="sxs-lookup"><span data-stu-id="bf5c2-142">0</span></span> | <span data-ttu-id="bf5c2-143">I hope this helps.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-143">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="bf5c2-144">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="bf5c2-144">Choose a scenario</span></span>

![Visual Studio의 모델 작성기 마법사](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="bf5c2-146">모델을 학습하려면 모델 작성기에서 제공하는 사용 가능한 기계 학습 시나리오 목록에서 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-146">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span>

1. <span data-ttu-id="bf5c2-147">**솔루션 탐색기** 에서 *SentimentRazor* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **Machine Learning** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-147">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="bf5c2-148">이 샘플에서 감정 분석은 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-148">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="bf5c2-149">모델 분석기 도구의 *시나리오* 단계에서 **감정 분석** 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-149">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="bf5c2-150">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="bf5c2-150">Load the data</span></span>

<span data-ttu-id="bf5c2-151">모델 작성기는 SQL Server 데이터베이스 또는 로컬 파일 `csv` 또는 `tsv` 형식의 두 가지 소스에서 데이터를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-151">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="bf5c2-152">모델 작성기 도구의 데이터 단계의 데이터 원본 드롭다운에서 **파일** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-152">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="bf5c2-153">**파일 선택** 텍스트 상자 옆의 있는 단추를 선택하고 파일 탐색기를 사용하여 *wikipedia-detox-250-line-data.tsv* 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-153">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="bf5c2-154">**예측할 열(레이블)** 드롭다운에서 **감정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-154">Choose **Sentiment** in the **Column to Predict (Label)** dropdown.</span></span>
1. <span data-ttu-id="bf5c2-155">**열 입력(기능)** 드롭다운의 기본값을 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-155">Leave the default values for the **Input Columns (Features)** dropdown.</span></span>
1. <span data-ttu-id="bf5c2-156">**학습** 링크를 선택하여 모델 작성기 도구의 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-156">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="bf5c2-157">모델 학습</span><span class="sxs-lookup"><span data-stu-id="bf5c2-157">Train the model</span></span>

<span data-ttu-id="bf5c2-158">이 자습서에서 감정 분석 모델을 학습하는 데 사용되는 기계 학습 작업은 이진 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-158">The machine learning task used to train the sentiment analysis model in this tutorial is binary classification.</span></span> <span data-ttu-id="bf5c2-159">모델 학습 프로세스 중에 모델 작성기는 다른 이진 분류 알고리즘 및 설정을 통해 개별 모델을 학습하여 데이터 세트에 가장 적합한 모델을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-159">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="bf5c2-160">모델을 학습하는 데 필요한 시간은 데이터 양에 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-160">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="bf5c2-161">모델 작성기는 데이터 소스의 크기에 따라 **학습 시간(초)** 의 기본값을 자동으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-161">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="bf5c2-162">모델 작성기는 **학습 시간(초)** 값을 10초로 설정하지만 이 값을 30초로 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-162">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="bf5c2-163">더 긴 시간 동안 학습하면 모델 작성기가 최상의 모델을 찾아 더 많은 알고리즘과 매개 변수의 조합을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-163">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="bf5c2-164">**학습 시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-164">Select **Start Training**.</span></span>

    <span data-ttu-id="bf5c2-165">학습 프로세스 전체에서 진행률 데이터는 학습 단계의 `Progress` 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-165">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="bf5c2-166">상태는 학습 프로세스의 완료 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-166">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="bf5c2-167">가장 높은 정확도는 모델 작성기가 현재까지 찾은 최고 성능 모델의 정확도를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-167">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="bf5c2-168">더 높은 정확도는 테스트 데이터에서 모델이 더 정확하게 예측된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-168">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="bf5c2-169">최상의 알고리즘은 모델 작성기가 현재까지 찾은 최고 성능 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-169">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="bf5c2-170">마지막 알고리즘은 모델 작성기가 가장 최근에 학습하기 위해 사용한 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-170">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="bf5c2-171">학습이 완료되면 **평가** 링크를 선택하여 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-171">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="bf5c2-172">모델 평가</span><span class="sxs-lookup"><span data-stu-id="bf5c2-172">Evaluate the model</span></span>

<span data-ttu-id="bf5c2-173">학습 단계의 결과는 최상의 성능을 가진 하나의 모델이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-173">The result of the training step will be one model that has the best performance.</span></span> <span data-ttu-id="bf5c2-174">모델 작성기 도구의 평가 단계에서 출력 섹션에는 **최상의 모델** 항목의 가장 성능이 좋은 모델에서 사용되는 알고리즘과 더불어 **최상의 모델 정확도** 의 메트릭이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-174">In the evaluate step of the Model Builder tool, the output section will contain the algorithm used by the best-performing model in the **Best Model** entry along with metrics in **Best Model Accuracy**.</span></span> <span data-ttu-id="bf5c2-175">또한 상위 5개 모델 및 해당 메트릭을 포함하는 요약 테이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-175">Additionally, a summary table containing the top five models and their metrics is shown.</span></span>

<span data-ttu-id="bf5c2-176">정확도 메트릭에 만족하지 않는 경우 모델 정확도를 개선하기 위한 몇 가지 쉬운 방법은 모델을 학습하거나 더 많은 데이터를 사용하기 위한 시간을 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-176">If you're not satisfied with your accuracy metrics, some easy ways to try to improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="bf5c2-177">그렇지 않으면 **코드** 링크를 선택하여 모델 작성기 도구의 최종 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-177">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="bf5c2-178">코드를 추가하여 예측하기</span><span class="sxs-lookup"><span data-stu-id="bf5c2-178">Add the code to make predictions</span></span>

<span data-ttu-id="bf5c2-179">학습 프로세스의 결과로 두 개의 프로젝트가 만들어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-179">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="bf5c2-180">학습된 모델 참조</span><span class="sxs-lookup"><span data-stu-id="bf5c2-180">Reference the trained model</span></span>

1. <span data-ttu-id="bf5c2-181">모델 작성기 도구의 *코드* 단계에서 **프로젝트 추가** 를 선택하여 자동 생성된 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-181">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="bf5c2-182">**솔루션 탐색기** 에 다음 프로젝트가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-182">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="bf5c2-183">*SentimentRazorML.ConsoleApp*: 모델 학습 및 예측 코드가 포함된 .NET Core 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-183">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="bf5c2-184">*SentimentRazorML.Model*: 입력 및 출력 모델 데이터의 스키마를 정의하는 데이터 모델뿐만 아니라 학습 중 가장 성능이 뛰어난 모델의 저장된 버전을 포함하는 .NET Standard 클래스 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-184">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the saved version of the best performing model during training.</span></span>

    <span data-ttu-id="bf5c2-185">이 자습서에서는 *SentimentRazorML.Model* 프로젝트만을 사용합니다. 예측이 콘솔이 아니라 *SentimentRazor* 웹 애플리케이션에서 수행되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-185">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="bf5c2-186">*SentimentRazorML.ConsoleApp* 은 점수 매기기에 사용되지 않지만 나중에 새 데이터를 사용하여 모델을 다시 학습하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-186">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="bf5c2-187">재학습은 이 자습서에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-187">Retraining is outside the scope of this tutorial though.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="bf5c2-188">PredictionEngine 풀 구성</span><span class="sxs-lookup"><span data-stu-id="bf5c2-188">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="bf5c2-189">단일 예측을 수행하려면 <xref:Microsoft.ML.PredictionEngine%602>을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-189">To make a single prediction, you have to create a <xref:Microsoft.ML.PredictionEngine%602>.</span></span> <span data-ttu-id="bf5c2-190"><xref:Microsoft.ML.PredictionEngine%602>는 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-190"><xref:Microsoft.ML.PredictionEngine%602> is not thread-safe.</span></span> <span data-ttu-id="bf5c2-191">또한 애플리케이션 내에서 필요한 모든 위치에서 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-191">Additionally, you have to create an instance of it everywhere it's needed within your application.</span></span> <span data-ttu-id="bf5c2-192">애플리케이션이 커지면 이 프로세스를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-192">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="bf5c2-193">성능 및 스레드 보안을 개선하려면 종속성 주입과 `PredictionEnginePool` 서비스를 함께 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 <xref:Microsoft.ML.PredictionEngine%602> 개체의 <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-193">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601> of <xref:Microsoft.ML.PredictionEngine%602> objects for use throughout your application.</span></span>

1. <span data-ttu-id="bf5c2-194">*Microsoft.Extensions.ML* NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-194">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="bf5c2-195">**솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-195">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="bf5c2-196">패키지 원본으로 "nuget.org"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-196">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="bf5c2-197">**찾아보기** 탭을 선택하고 **Microsoft.Extensions.ML** 을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-197">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span>
    1. <span data-ttu-id="bf5c2-198">목록에서 패키지를 선택하고 **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-198">Select the package in the list, and select the **Install** button.</span></span>
    1. <span data-ttu-id="bf5c2-199">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-199">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="bf5c2-200">나열된 패키지 라이선스 조건에 동의하면 **라이선스 수락** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-200">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="bf5c2-201">*SentimentRazor* 프로젝트에서 *Startup.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-201">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="bf5c2-202">*Microsoft.Extensions.ML* NuGet 패키지 및 *SentimentRazorML.Model* 프로젝트를 참조하도록 다음 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-202">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. <span data-ttu-id="bf5c2-203">학습된 모델 파일의 위치를 저장하는 전역 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-203">Create a global variable to store the location of the trained model file.</span></span>

    ```csharp
    private readonly string _modelPath;
    ```

1. <span data-ttu-id="bf5c2-204">모델 파일은 애플리케이션의 어셈블리 파일과 함께 build 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-204">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="bf5c2-205">보다 쉽게 액세스할 수 있도록 `Configure` 메서드를 따라 `GetAbsolutePath`라는 도우미 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-205">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }
    ```

1. <span data-ttu-id="bf5c2-206">`Startup` 클래스 생성자에서 `GetAbsolutePath` 메서드를 사용하여 `_modelPath`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-206">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. <span data-ttu-id="bf5c2-207">`ConfigureServices` 메서드에서 애플리케이션에 대해 `PredictionEnginePool`을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-207">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="bf5c2-208">감정 분석 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="bf5c2-208">Create sentiment analysis handler</span></span>

<span data-ttu-id="bf5c2-209">예측은 애플리케이션의 기본 페이지에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-209">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="bf5c2-210">따라서 사용자 입력을 취하고 `PredictionEnginePool`을 사용하여 예측을 반환하는 메서드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-210">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="bf5c2-211">*Pages* 디렉터리에 있는 *Index.cshtml.cs* 파일을 열고 다음 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-211">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    <span data-ttu-id="bf5c2-212">`Startup` 클래스에서 구성된 `PredictionEnginePool`을 사용하려면 해당 클래스를 사용하려는 모델의 생성자에 삽입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-212">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span>

1. <span data-ttu-id="bf5c2-213">`IndexModel` 클래스 내부에서 `PredictionEnginePool`을 참조하는 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-213">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. <span data-ttu-id="bf5c2-214">`IndexModel` 클래스에서 생성자를 만들고 `PredictionEnginePool` 서비스를 여기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-214">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }
    ```

1. <span data-ttu-id="bf5c2-215">`PredictionEnginePool`을 사용하여 웹 페이지에서 받은 사용자 입력으로부터 예측을 수행하는 메서드 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-215">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="bf5c2-216">`OnGet` 메서드 아래 `OnGetAnalyzeSentiment`라는 새 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-216">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="bf5c2-217">사용자의 입력이 비어 있거나 null인 경우 `OnGetAnalyzeSentiment` 메서드 내에서 *중립* 감정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-217">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. <span data-ttu-id="bf5c2-218">입력이 유효할 경우 `ModelInput`의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-218">Given a valid input, create a new instance of `ModelInput`.</span></span>

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. <span data-ttu-id="bf5c2-219">`PredictionEnginePool`을 사용하여 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-219">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. <span data-ttu-id="bf5c2-220">다음 코드를 사용하여 예측된 `bool` 값을 유해 또는 무해로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-220">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. <span data-ttu-id="bf5c2-221">마지막으로 감정을 웹 페이지로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-221">Finally, return the sentiment back to the web page.</span></span>

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a><span data-ttu-id="bf5c2-222">웹 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="bf5c2-222">Configure the web page</span></span>

<span data-ttu-id="bf5c2-223">`OnGetAnalyzeSentiment`에서 반환하는 결과는 `Index` 웹 페이지에 동적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-223">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="bf5c2-224">*Pages* 디렉터리에서 *Index. cshtml* 파일을 열고 해당 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-224">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span>

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="bf5c2-225">다음으로, *wwwroot\css* 디렉터리에서 *site.css* 페이지 끝에 css 스타일 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-225">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="bf5c2-226">그런 다음 웹 페이지에서 `OnGetAnalyzeSentiment` 처리기로 입력을 보내는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-226">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="bf5c2-227">*wwwroot\js* 디렉터리에 있는 *site.js* 파일에서 `OnGetAnalyzeSentiment` 처리기에 사용자 입력을 사용하여 GET HTTP 요청을 하는 `getSentiment`라는 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-227">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="bf5c2-228">그 아래에 감정이 예측되면 웹 페이지에서 표식의 위치를 동적으로 업데이트하는 `updateMarker`라는 또 다른 함수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-228">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="bf5c2-229">사용자의 입력을 가져와 `getSentiment` 함수를 사용하여 `OnGetAnalyzeSentiment` 함수에 보내고 `updateMarker` 함수를 사용하여 표식을 업데이트하는 `updateSentiment`라는 이벤트 처리기 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-229">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="bf5c2-230">마지막으로 이벤트 처리기를 등록하고 `id=Message` 특성을 사용하여 `textarea` 요소에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-230">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="bf5c2-231">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="bf5c2-231">Run the application</span></span>

<span data-ttu-id="bf5c2-232">이제 애플리케이션이 설정되었으므로 브라우저에서 시작해야 하는 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-232">Now that your application is set up, run the application, which should launch in your browser.</span></span>

<span data-ttu-id="bf5c2-233">애플리케이션이 시작되면 *Model Builder is cool!* 을</span><span class="sxs-lookup"><span data-stu-id="bf5c2-233">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="bf5c2-234">텍스트 영역에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-234">into the text area.</span></span> <span data-ttu-id="bf5c2-235">예측된 감정이 *무해* 로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-235">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![예측된 감정 창이 있는 실행 창](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="bf5c2-237">모델 작성기에서 생성된 프로젝트를 나중에 다른 솔루션 내에서 참조해야 하는 경우 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 디렉터리 내에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-237">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf5c2-238">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf5c2-238">Next steps</span></span>

<span data-ttu-id="bf5c2-239">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-239">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="bf5c2-240">ASP.NET Core Razor Pages 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="bf5c2-240">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="bf5c2-241">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="bf5c2-241">Prepare and understand the data</span></span>
> - <span data-ttu-id="bf5c2-242">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="bf5c2-242">Choose a scenario</span></span>
> - <span data-ttu-id="bf5c2-243">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="bf5c2-243">Load the data</span></span>
> - <span data-ttu-id="bf5c2-244">모델 학습</span><span class="sxs-lookup"><span data-stu-id="bf5c2-244">Train the model</span></span>
> - <span data-ttu-id="bf5c2-245">모델 평가</span><span class="sxs-lookup"><span data-stu-id="bf5c2-245">Evaluate the model</span></span>
> - <span data-ttu-id="bf5c2-246">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="bf5c2-246">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="bf5c2-247">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="bf5c2-247">Additional Resources</span></span>

<span data-ttu-id="bf5c2-248">이 자습서에서 언급한 항목에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf5c2-248">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="bf5c2-249">모델 작성기 시나리오</span><span class="sxs-lookup"><span data-stu-id="bf5c2-249">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenario)
- [<span data-ttu-id="bf5c2-250">이진 분류</span><span class="sxs-lookup"><span data-stu-id="bf5c2-250">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="bf5c2-251">이진 분류 모델 메트릭</span><span class="sxs-lookup"><span data-stu-id="bf5c2-251">Binary Classification Model Metrics</span></span>](../resources/metrics.md#evaluation-metrics-for-binary-classification)

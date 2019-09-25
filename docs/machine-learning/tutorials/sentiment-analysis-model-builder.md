---
title: '자습서: 감정 분석 - 이진 분류'
description: 이 자습서에서는 웹 사이트 주석에서 감정을 분류하고 적절한 조치를 취하는 Razor Pages 애플리케이션을 만드는 방법을 보여 줍니다. 감정 이진 분류자는 Visual Studio에서 모델 작성기를 사용합니다.
ms.date: 09/13/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6184e097daf4604173db9e2a34606e68eb0fdc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054275"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="fb551-104">자습서: ML.NET 모델 작성기를 사용하여 웹 애플리케이션에서 웹 사이트 댓글 감정 분석</span><span class="sxs-lookup"><span data-stu-id="fb551-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="fb551-105">웹 애플리케이션에서 실시간으로 댓글의 감정을 분석하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-105">Learn how to analyze sentiment from comments in real-time inside a web application.</span></span>

<span data-ttu-id="fb551-106">이 자습서에서는 실시간으로 웹 사이트 댓글에서 감정을 분류하는 ASP.NET Core Razor Pages 애플리케이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real-time.</span></span>

<span data-ttu-id="fb551-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="fb551-108">ASP.NET Core Razor Pages 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fb551-108">Create an ASP.NET Core Razor Pages application</span></span>
> * <span data-ttu-id="fb551-109">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="fb551-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="fb551-110">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="fb551-110">Choose a scenario</span></span>
> * <span data-ttu-id="fb551-111">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fb551-111">Load the data</span></span>
> * <span data-ttu-id="fb551-112">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fb551-112">Train the model</span></span>
> * <span data-ttu-id="fb551-113">모델 평가</span><span class="sxs-lookup"><span data-stu-id="fb551-113">Evaluate the model</span></span>
> * <span data-ttu-id="fb551-114">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fb551-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="fb551-115">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="fb551-116">[dotnet/samples](https://github.com/dotnet/machinelearning-samples) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="fb551-117">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fb551-117">Pre-requisites</span></span>

<span data-ttu-id="fb551-118">필수 구성 요소 및 설치 지침 목록을 보려면 [모델 작성기 설치 가이드](../how-to-guides/install-model-builder.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="fb551-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="fb551-119">Razor Pages 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fb551-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="fb551-120">**ASP.NET Core Razor Pages 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="fb551-121">Visual Studio를 열고 메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span> 
    1. <span data-ttu-id="fb551-122">[새 프로젝트] 대화 상자에서 **Visual C#** 노드와 **Web** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> 
    1. <span data-ttu-id="fb551-123">그런 다음, **ASP.NET Core 웹 애플리케이션** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-123">Then select the **ASP.NET Core Web Application** project template.</span></span> 
    1. <span data-ttu-id="fb551-124">**이름** 텍스트 상자에 "SentimentRazor"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="fb551-125">**솔루션용 디렉터리 만들기** 확인란은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-125">The **Create a directory for solution** checkbox should be checked by default.</span></span> <span data-ttu-id="fb551-126">선택되어 있지 않다면 직접 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-126">If that's not the case, check it.</span></span> 
    1. <span data-ttu-id="fb551-127">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-127">Select the **OK** button.</span></span>
    1. <span data-ttu-id="fb551-128">다른 유형의 ASP.NET Core 프로젝트를 표시하는 창에서 **웹 애플리케이션**을 선택하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-128">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="fb551-129">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="fb551-129">Prepare and understand the data</span></span>

<span data-ttu-id="fb551-130">[Wikipedia detox 데이터 세트](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-130">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="fb551-131">웹 페이지가 열리면 페이지를 마우스 오른쪽 단추로 클릭하고 **다른 이름으로 저장**을 선택하여 컴퓨터의 아무 위치에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-131">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span> 

<span data-ttu-id="fb551-132">*wikipedia-detox-250-line-data.tsv* 데이터 세트의 각 행은 사용자가 Wikipedia에 남긴 다른 검토를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-132">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="fb551-133">첫 번째 열은 텍스트의 감정(0은 무해, 1은 유해)를 나타내고, 두 번째 열은 사용자가 남긴 댓글을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-133">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="fb551-134">열은 탭으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-134">The columns are separated by tabs.</span></span> <span data-ttu-id="fb551-135">데이터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-135">The data looks like the following:</span></span>

| <span data-ttu-id="fb551-136">감정</span><span class="sxs-lookup"><span data-stu-id="fb551-136">Sentiment</span></span> | <span data-ttu-id="fb551-137">SentimentText</span><span class="sxs-lookup"><span data-stu-id="fb551-137">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="fb551-138">1</span><span class="sxs-lookup"><span data-stu-id="fb551-138">1</span></span> | <span data-ttu-id="fb551-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span><span class="sxs-lookup"><span data-stu-id="fb551-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="fb551-140">1</span><span class="sxs-lookup"><span data-stu-id="fb551-140">1</span></span> | <span data-ttu-id="fb551-141">== OK!</span><span class="sxs-lookup"><span data-stu-id="fb551-141">== OK!</span></span> <span data-ttu-id="fb551-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span><span class="sxs-lookup"><span data-stu-id="fb551-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="fb551-143">0</span><span class="sxs-lookup"><span data-stu-id="fb551-143">0</span></span> | <span data-ttu-id="fb551-144">I hope this helps.</span><span class="sxs-lookup"><span data-stu-id="fb551-144">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="fb551-145">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="fb551-145">Choose a scenario</span></span>

![](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="fb551-146">모델을 학습하려면 모델 작성기에서 제공하는 사용 가능한 기계 학습 시나리오 목록에서 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-146">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> 

1. <span data-ttu-id="fb551-147">**솔루션 탐색기**에서 *SentimentRazor* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **Machine Learning**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-147">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="fb551-148">이 샘플에서 감정 분석은 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-148">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="fb551-149">모델 분석기 도구의 *시나리오* 단계에서 **감정 분석** 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-149">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="fb551-150">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fb551-150">Load the data</span></span>

<span data-ttu-id="fb551-151">모델 작성기는 SQL Server 데이터베이스 또는 로컬 파일 `csv` 또는 `tsv` 형식의 두 가지 소스에서 데이터를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-151">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="fb551-152">모델 작성기 도구의 데이터 단계의 데이터 원본 드롭다운에서 **파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-152">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="fb551-153">**파일 선택** 텍스트 상자 옆의 있는 단추를 선택하고 파일 탐색기를 사용하여 *wikipedia-detox-250-line-data.tsv* 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-153">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="fb551-154">**예측할 레이블 또는 열** 드롭다운에서 **감정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-154">Choose **Sentiment** in the **Label or Column to Predict** dropdown</span></span>
1. <span data-ttu-id="fb551-155">**학습** 링크를 선택하여 모델 작성기 도구의 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-155">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="fb551-156">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fb551-156">Train the model</span></span>

<span data-ttu-id="fb551-157">이 자습서에서 가격 예측 모델을 학습하는 데 사용되는 기계 학습 작업은 이진 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-157">The machine learning task used to train the price prediction model in this tutorial is binary classification.</span></span> <span data-ttu-id="fb551-158">모델 학습 프로세스 중에 모델 작성기는 다른 이진 분류 알고리즘 및 설정을 통해 개별 모델을 학습하여 데이터 세트에 가장 적합한 모델을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-158">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="fb551-159">모델을 학습하는 데 필요한 시간은 데이터 양에 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-159">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="fb551-160">모델 작성기는 데이터 소스의 크기에 따라 **학습 시간(초)** 의 기본값을 자동으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-160">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span> 

1. <span data-ttu-id="fb551-161">모델 작성기는 **학습 시간(초)** 값을 10초로 설정하지만 이 값을 30초로 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-161">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="fb551-162">더 긴 시간 동안 학습하면 모델 작성기가 최상의 모델을 찾아 더 많은 알고리즘과 매개 변수의 조합을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-162">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="fb551-163">**학습 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-163">Select **Start Training**.</span></span>

    <span data-ttu-id="fb551-164">학습 프로세스 전체에서 진행률 데이터는 학습 단계의 `Progress` 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-164">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="fb551-165">상태는 학습 프로세스의 완료 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-165">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="fb551-166">가장 높은 정확도는 모델 작성기가 현재까지 찾은 최고 성능 모델의 정확도를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-166">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="fb551-167">더 높은 정확도는 테스트 데이터에서 모델이 더 정확하게 예측된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-167">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="fb551-168">최상의 알고리즘은 모델 작성기가 현재까지 찾은 최고 성능 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-168">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="fb551-169">마지막 알고리즘은 모델 작성기가 가장 최근에 학습하기 위해 사용한 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-169">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="fb551-170">학습이 완료되면 **평가** 링크를 선택하여 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-170">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="fb551-171">모델 평가</span><span class="sxs-lookup"><span data-stu-id="fb551-171">Evaluate the model</span></span>

<span data-ttu-id="fb551-172">학습 단계의 결과는 최상의 성능을 가진 하나의 모델이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-172">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="fb551-173">모델 작성기 도구의 평가 단계인 출력 섹션에는 **최상의 모델** 항목에서 가장 성능이 좋은 모델에서 사용되는 알고리즘과 **최상의 모델 품질(RSquared)** 의 메트릭이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-173">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the **Best Model** entry along with metrics in **Best Model Quality (RSquared)**.</span></span> <span data-ttu-id="fb551-174">또한 상위 5개 모델 및 해당 메트릭을 포함하는 요약 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-174">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="fb551-175">정확도 메트릭에 만족하지 않는 경우 모델 정확도를 개선하기 위한 몇 가지 쉬운 방법은 모델을 학습하거나 더 많은 데이터를 사용하기 위한 시간을 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-175">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="fb551-176">그렇지 않으면 **코드** 링크를 선택하여 모델 작성기 도구의 최종 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-176">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="fb551-177">코드를 추가하여 예측하기</span><span class="sxs-lookup"><span data-stu-id="fb551-177">Add the code to make predictions</span></span>

<span data-ttu-id="fb551-178">학습 프로세스의 결과로 두 개의 프로젝트가 만들어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-178">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="fb551-179">학습된 모델 참조</span><span class="sxs-lookup"><span data-stu-id="fb551-179">Reference the trained model</span></span>

1. <span data-ttu-id="fb551-180">모델 작성기 도구의 *코드* 단계에서 **프로젝트 추가**를 선택하여 자동 생성된 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-180">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="fb551-181">**솔루션 탐색기**에 다음 프로젝트가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-181">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="fb551-182">*SentimentRazorML.ConsoleApp*: 모델 학습 및 예측 코드가 포함된 .NET Core 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-182">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="fb551-183">*SentimentRazorML.Model*: 입력 및 출력 모델 데이터의 스키마를 정의하는 데이터 모델뿐만 아니라 학습 중 가장 성능이 뛰어난 모델의 지속 버전을 포함하는 .NET Standard 클래스 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-183">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

    <span data-ttu-id="fb551-184">이 자습서에서는 *SentimentRazorML.Model* 프로젝트만을 사용합니다. 예측이 콘솔이 아니라 *SentimentRazor* 웹 애플리케이션에서 수행되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-184">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="fb551-185">*SentimentRazorML.ConsoleApp*은 점수 매기기에 사용되지 않지만 나중에 새 데이터를 사용하여 모델을 다시 학습하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-185">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="fb551-186">재학습은 이 자습서에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-186">Retraining is outside the scope of this tutorial though.</span></span>

1. <span data-ttu-id="fb551-187">학습된 모델을 Razor Pages 애플리케이션에서 사용하려면 *SentimentRazorML.Model* 프로젝트에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-187">To use the trained model inside your Razor Pages application, add a reference to the *SentimentRazorML.Model* project.</span></span>

    1. <span data-ttu-id="fb551-188">**SentimentRazor** 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-188">Right-click **SentimentRazor** project.</span></span> 
    1. <span data-ttu-id="fb551-189">**추가 > 참조**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-189">Select **Add > Reference**.</span></span> 
    1. <span data-ttu-id="fb551-190">**프로젝트 > 솔루션** 노드를 선택하고 목록에서 **SentimentRazorML.Model** 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-190">Choose the **Projects > Solution** node and from the list, check the **SentimentRazorML.Model** project.</span></span>
    1. <span data-ttu-id="fb551-191">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-191">Select **OK**.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="fb551-192">PredictionEngine 풀 구성</span><span class="sxs-lookup"><span data-stu-id="fb551-192">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="fb551-193">단일 예측에는 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-193">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="fb551-194">애플리케이션에 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 사용하려면 필요할 때 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-194">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application, you must create it when it's needed.</span></span> <span data-ttu-id="fb551-195">이 경우 가장 좋은 방법은 종속성 주입을 고려하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-195">In that case, a best practice to consider is dependency injection.</span></span>

> [!WARNING]
> <span data-ttu-id="fb551-196">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-196">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="fb551-197">성능과 스레드 안전 향상을 위해 애플리케이션용으로 `PredictionEngine` 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만드는 `PredictionEnginePool` 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-197">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="fb551-198">[ASP.NET Core에서 `PredictionEngine`개체 풀 만들기 및 사용](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/)에 대한 자세한 정보는 다음 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb551-198">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span> 

1. <span data-ttu-id="fb551-199">*Microsoft.Extensions.ML* NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-199">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="fb551-200">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-200">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> 
    1. <span data-ttu-id="fb551-201">패키지 원본으로 "nuget.org"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-201">Choose "nuget.org" as the Package source.</span></span> 
    1. <span data-ttu-id="fb551-202">**찾아보기** 탭을 선택하고 **Microsoft.Extensions.ML**을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-202">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span> 
    1. <span data-ttu-id="fb551-203">목록에서 패키지를 선택하고 **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-203">Select the package in the list, and select the **Install** button.</span></span> 
    1. <span data-ttu-id="fb551-204">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-204">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="fb551-205">나열된 패키지 라이선스 조건에 동의하면 **라이선스 수락** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-205">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> 

1. <span data-ttu-id="fb551-206">*SentimentRazor* 프로젝트에서 *Startup.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-206">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="fb551-207">*Microsoft.Extensions.ML* NuGet 패키지 및 *SentimentRazorML.Model* 프로젝트를 참조하도록 다음 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-207">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L12-L14)]        

1. <span data-ttu-id="fb551-208">학습된 모델 파일의 위치를 저장하는 전역 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-208">Create a global variable to store the location of the trained model file.</span></span>

    [!code-csharp [ModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L20)]

1. <span data-ttu-id="fb551-209">모델 파일은 애플리케이션의 어셈블리 파일과 함께 build 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-209">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="fb551-210">보다 쉽게 액세스할 수 있도록 `Configure` 메서드를 따라 `GetAbsolutePath`라는 도우미 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-210">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    [!code-csharp [GetAbsolutePathMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L66-L73)]

1. <span data-ttu-id="fb551-211">`Startup` 클래스 생성자에서 `GetAbsolutePath` 메서드를 사용하여 `_modelPath`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-211">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    [!code-csharp [InitModelPath](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L25)]

1. <span data-ttu-id="fb551-212">`ConfigureServices` 메서드에서 애플리케이션에 대해 `PredictionEnginePool`을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-212">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    [!code-csharp [InitPredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Startup.cs#L42)]

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="fb551-213">감정 분석 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="fb551-213">Create sentiment analysis handler</span></span>

<span data-ttu-id="fb551-214">예측은 애플리케이션의 기본 페이지에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-214">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="fb551-215">따라서 사용자 입력을 취하고 `PredictionEnginePool`을 사용하여 예측을 반환하는 메서드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-215">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="fb551-216">*Pages* 디렉터리에 있는 *Index.cshtml.cs* 파일을 열고 다음 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-216">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    [!code-csharp [IndexUsings](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L7-L8)]

    <span data-ttu-id="fb551-217">`Startup` 클래스에서 구성된 `PredictionEnginePool`을 사용하려면 해당 클래스를 사용하려는 모델의 생성자에 삽입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-217">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span> 

1. <span data-ttu-id="fb551-218">`IndexModel` 클래스 내부에서 `PredictionEnginePool`을 참조하는 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-218">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    [!code-csharp [PredEnginePool](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L14)]

1. <span data-ttu-id="fb551-219">`IndexModel` 클래스에서 생성자를 만들고 `PredictionEnginePool` 서비스를 여기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-219">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    [!code-csharp [IndexConstructor](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L16-L19)]

1. <span data-ttu-id="fb551-220">`PredictionEnginePool`을 사용하여 웹 페이지에서 받은 사용자 입력으로부터 예측을 수행하는 메서드 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-220">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="fb551-221">`OnGet` 메서드 아래 `OnGetAnalyzeSentiment`라는 새 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-221">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="fb551-222">사용자의 입력이 비어 있거나 null인 경우 `OnGetAnalyzeSentiment` 메서드 내에서 *중립* 감정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-222">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L28)] 
    
    1. <span data-ttu-id="fb551-223">입력이 유효할 경우 `ModelInput`의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-223">Given a valid input, create a new instance of `ModelInput`.</span></span> 

        [!code-csharp [InitInput](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L29)] 

    1. <span data-ttu-id="fb551-224">`PredictionEnginePool`을 사용하여 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-224">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        [!code-csharp [MakePrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L30)] 

    1. <span data-ttu-id="fb551-225">다음 코드를 사용하여 예측된 `bool` 값을 유해 또는 무해로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-225">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        [!code-csharp [ConvertPrediction](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L31)]

    1. <span data-ttu-id="fb551-226">마지막으로 감정을 웹 페이지로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-226">Finally, return the sentiment back to the web page.</span></span>

        [!code-csharp [ReturnSentiment](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml.cs#L32)]

### <a name="configure-the-web-page"></a><span data-ttu-id="fb551-227">웹 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="fb551-227">Configure the web page</span></span>

<span data-ttu-id="fb551-228">`OnGetAnalyzeSentiment`에서 반환하는 결과는 `Index` 웹 페이지에 동적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-228">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="fb551-229">*Pages* 디렉터리에서 *Index. cshtml* 파일을 열고 해당 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-229">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span> 

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="fb551-230">다음으로, *wwwroot\css* 디렉터리에서 *site.css* 페이지 끝에 css 스타일 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-230">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="fb551-231">그런 다음 웹 페이지에서 `OnGetAnalyzeSentiment` 처리기로 입력을 보내는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-231">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="fb551-232">*wwwroot\js* 디렉터리에 있는 *site.js* 파일에서 `OnGetAnalyzeSentiment` 처리기에 사용자 입력을 사용하여 GET HTTP 요청을 하는 `getSentiment`라는 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-232">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="fb551-233">그 아래에 감정이 예측되면 웹 페이지에서 표식의 위치를 동적으로 업데이트하는 `updateMarker`라는 또 다른 함수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-233">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="fb551-234">사용자의 입력을 가져와 `getSentiment` 함수를 사용하여 `OnGetAnalyzeSentiment` 함수에 보내고 `updateMarker` 함수를 사용하여 표식을 업데이트하는 `updateSentiment`라는 이벤트 처리기 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-234">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="fb551-235">마지막으로 이벤트 처리기를 등록하고 `id=Message` 특성을 사용하여 `textarea` 요소에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-235">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="fb551-236">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="fb551-236">Run the application</span></span>

<span data-ttu-id="fb551-237">이제 애플리케이션이 설정되었으므로 브라우저에서 시작해야 하는 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-237">Now that your application is set up, run the application which should launch in your browser.</span></span>

<span data-ttu-id="fb551-238">애플리케이션이 시작되면 *Model Builder is cool!* 을</span><span class="sxs-lookup"><span data-stu-id="fb551-238">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="fb551-239">텍스트 영역에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-239">into the text area.</span></span> <span data-ttu-id="fb551-240">예측된 감정이 *무해*로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-240">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="fb551-241">모델 작성기에서 생성된 프로젝트를 나중에 다른 솔루션 내에서 참조해야 하는 경우 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 디렉터리 내에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-241">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb551-242">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fb551-242">Next steps</span></span>

<span data-ttu-id="fb551-243">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb551-243">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="fb551-244">ASP.NET Core Razor Pages 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fb551-244">Create an ASP.NET Core Razor Pages application</span></span>
> * <span data-ttu-id="fb551-245">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="fb551-245">Prepare and understand the data</span></span>
> * <span data-ttu-id="fb551-246">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="fb551-246">Choose a scenario</span></span>
> * <span data-ttu-id="fb551-247">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fb551-247">Load the data</span></span>
> * <span data-ttu-id="fb551-248">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fb551-248">Train the model</span></span>
> * <span data-ttu-id="fb551-249">모델 평가</span><span class="sxs-lookup"><span data-stu-id="fb551-249">Evaluate the model</span></span>
> * <span data-ttu-id="fb551-250">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fb551-250">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fb551-251">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="fb551-251">Additional Resources</span></span>

<span data-ttu-id="fb551-252">이 자습서에서 언급한 항목에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb551-252">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="fb551-253">모델 작성기 시나리오</span><span class="sxs-lookup"><span data-stu-id="fb551-253">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="fb551-254">이진 분류</span><span class="sxs-lookup"><span data-stu-id="fb551-254">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="fb551-255">이진 분류 모델 메트릭</span><span class="sxs-lookup"><span data-stu-id="fb551-255">Binary Classification Model Metrics</span></span>](../resources/metrics.md#metrics-for-binary-classification)
---
title: 감정 분석 이진 분류 시나리오에서 ML.NET 사용
description: 감정 예측을 통해 적절한 작업을 수행하는 방법을 이해하기 위해 이진 분류 시나리오에서 ML.NET을 사용하는 방법을 살펴봅니다.
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: c5373f63927ff39e7c819cd1fc0bc2bec1843b3e
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58921119"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="515c9-103">자습서: 감정 분석 이진 분류 시나리오에서 ML.NET 사용</span><span class="sxs-lookup"><span data-stu-id="515c9-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

<span data-ttu-id="515c9-104">이 샘플 자습서에서는 Visual Studio 2017에서 C#을 사용하는 .NET Core 콘솔 애플리케이션을 통해 긍정적 또는 부정적 감정을 예측하기 위해 ML.NET을 사용하여 감정 분류자를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-104">This sample tutorial illustrates using ML.NET to create a sentiment classifier to predict either positive or negative sentiment via a .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="515c9-105">기계 학습 환경에서 이 예측 유형을 이진 분류라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-105">In the world of machine learning, this type of prediction is known as binary classification.</span></span>

> [!NOTE]
> <span data-ttu-id="515c9-106">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="515c9-107">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="515c9-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="515c9-108">이 자습서와 관련 샘플에서는 현재 **ML.NET 버전 0.11**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-108">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="515c9-109">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="515c9-109">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="515c9-110">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-110">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="515c9-111">문제 이해</span><span class="sxs-lookup"><span data-stu-id="515c9-111">Understand the problem</span></span>
> * <span data-ttu-id="515c9-112">적절한 기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="515c9-112">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="515c9-113">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="515c9-113">Prepare your data</span></span>
> * <span data-ttu-id="515c9-114">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="515c9-114">Transform the data</span></span>
> * <span data-ttu-id="515c9-115">모델 학습</span><span class="sxs-lookup"><span data-stu-id="515c9-115">Train the model</span></span>
> * <span data-ttu-id="515c9-116">모델 평가</span><span class="sxs-lookup"><span data-stu-id="515c9-116">Evaluate the model</span></span>
> * <span data-ttu-id="515c9-117">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="515c9-117">Predict with the trained model</span></span>
> * <span data-ttu-id="515c9-118">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="515c9-118">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="515c9-119">감정 분석 샘플 개요</span><span class="sxs-lookup"><span data-stu-id="515c9-119">Sentiment analysis sample overview</span></span>

<span data-ttu-id="515c9-120">샘플은 ML.NET을 사용하여 감정을 긍정적 또는 부정적으로 분류하고 예측하는 모델을 학습시키는 콘솔 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-120">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="515c9-121">Yelp 감정 데이터 세트는 UCI(University of California, Irvine)에서 제공되고 학습 데이터 세트와 테스트 데이터 세트로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-121">The Yelp sentiment dataset is from University of California, Irvine (UCI), which is split into a train dataset and a test dataset.</span></span> <span data-ttu-id="515c9-122">샘플은 품질 분석을 위해 테스트 데이터 세트를 사용하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-122">The sample evaluates the model with the test dataset for quality analysis.</span></span> 

<span data-ttu-id="515c9-123">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-123">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="515c9-124">전제 조건</span><span class="sxs-lookup"><span data-stu-id="515c9-124">Prerequisites</span></span>

* <span data-ttu-id="515c9-125">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="515c9-125">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="515c9-126">UCI Sentiment Labeled Sentences 데이터 세트 zip 파일</span><span class="sxs-lookup"><span data-stu-id="515c9-126">The UCI Sentiment Labeled Sentences dataset zip file</span></span>](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a><span data-ttu-id="515c9-127">기계 학습 워크플로</span><span class="sxs-lookup"><span data-stu-id="515c9-127">Machine learning workflow</span></span>

<span data-ttu-id="515c9-128">이 자습서는 프로세스가 체계적으로 이동할 수 있도록 하는 기계 학습 워크플로를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="515c9-129">워크플로 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-129">The workflow phases are as follows:</span></span>

1. **<span data-ttu-id="515c9-130">문제 이해</span><span class="sxs-lookup"><span data-stu-id="515c9-130">Understand the problem</span></span>**
2. **<span data-ttu-id="515c9-131">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="515c9-131">Prepare your data</span></span>**
   * **<span data-ttu-id="515c9-132">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="515c9-132">Load the data</span></span>**
   * **<span data-ttu-id="515c9-133">기능 추출(데이터 변환)</span><span class="sxs-lookup"><span data-stu-id="515c9-133">Extract features (Transform your data)</span></span>**
3. **<span data-ttu-id="515c9-134">빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="515c9-134">Build and train</span></span>** 
   * **<span data-ttu-id="515c9-135">모델 학습</span><span class="sxs-lookup"><span data-stu-id="515c9-135">Train the model</span></span>**
   * **<span data-ttu-id="515c9-136">모델 평가</span><span class="sxs-lookup"><span data-stu-id="515c9-136">Evaluate the model</span></span>**
4. **<span data-ttu-id="515c9-137">모델 배포</span><span class="sxs-lookup"><span data-stu-id="515c9-137">Deploy Model</span></span>**
   * **<span data-ttu-id="515c9-138">예측 모델 사용</span><span class="sxs-lookup"><span data-stu-id="515c9-138">Use the Model to predict</span></span>**

### <a name="understand-the-problem"></a><span data-ttu-id="515c9-139">문제 이해</span><span class="sxs-lookup"><span data-stu-id="515c9-139">Understand the problem</span></span>

<span data-ttu-id="515c9-140">먼저 문제를 이해해야 하므로 모델 빌드 및 학습을 지원할 수 있는 부분으로 문제를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="515c9-141">문제를 구분하면 결과를 예측하고 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-141">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="515c9-142">이 자습서의 문제는 들어오는 웹 사이트 댓글 감정을 이해하여 적절한 작업을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-142">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="515c9-143">모델 학습에 사용할 데이터의 감정 텍스트와 감정 값 및 평가 후 조작에 사용할 수 있는 예측 감정 값으로 문제를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-143">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="515c9-144">그런 다음, 기계 학습 작업 선택에 도움이 되는 감정을 **확인**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-144">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="515c9-145">적절한 기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="515c9-145">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="515c9-146">이 문제에서 다음 사실을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-146">With this problem, you know the following facts:</span></span>

<span data-ttu-id="515c9-147">학습 데이터: 웹 사이트 댓글은 긍정적(1) 또는 부정적(0)(**감정**)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-147">Training data: website comments can be positive (1) or negative (0) (**sentiment**).</span></span>

<span data-ttu-id="515c9-148">다음 예제와 같이 새로운 웹 사이트 댓글의 **감정**을 긍정적 또는 부정적으로 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-148">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="515c9-149">종업원들이 매우 마음에 듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-149">I love the wait staff here.</span></span> <span data-ttu-id="515c9-150">정말 최고입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-150">They rock.</span></span>
* <span data-ttu-id="515c9-151">여기 수프는 최악입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-151">This place has the worst soup.</span></span>

<span data-ttu-id="515c9-152">이 시나리오에서는 분류 기계 학습 알고리즘이 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-152">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-algorithm"></a><span data-ttu-id="515c9-153">분류 알고리즘 정보</span><span class="sxs-lookup"><span data-stu-id="515c9-153">About the classification algorithm</span></span>

<span data-ttu-id="515c9-154">분류는 데이터를 사용하여 데이터 항목 또는 행의 범주, 형식 또는 클래스를 **확인**하는 기계 학습 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-154">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="515c9-155">예를 들어 분류를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-155">For example, you can use classification to:</span></span>

* <span data-ttu-id="515c9-156">감정을 긍정적 또는 부정적으로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-156">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="515c9-157">전자 메일을 스팸, 정크 또는 정상으로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-157">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="515c9-158">환자의 실험실 샘플이 종양성인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-158">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="515c9-159">영업 캠페인에 응답하는 고객의 성향을 기준으로 고객을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-159">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="515c9-160">일반적으로 분류 알고리즘은 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-160">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="515c9-161">이진: A 또는 B.</span><span class="sxs-lookup"><span data-stu-id="515c9-161">Binary: either A or B.</span></span>
* <span data-ttu-id="515c9-162">다중 클래스: 단일 모델을 사용하여 예측할 수 있는 여러 범주.</span><span class="sxs-lookup"><span data-stu-id="515c9-162">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="515c9-163">웹 사이트 댓글은 긍정적 또는 부정적으로 분류해야 하므로 이진 분류 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-163">Because the website comments need to be classified as either positive or negative, you use the Binary Classification algorithm.</span></span> 

## <a name="create-a-console-application"></a><span data-ttu-id="515c9-164">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="515c9-164">Create a console application</span></span>

1. <span data-ttu-id="515c9-165">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-165">Open Visual Studio 2017.</span></span> <span data-ttu-id="515c9-166">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-166">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="515c9-167">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-167">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="515c9-168">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-168">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="515c9-169">**이름** 텍스트 상자에 “SentimentAnalysis”를 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-169">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="515c9-170">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-170">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="515c9-171">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-171">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="515c9-172">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-172">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="515c9-173">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="515c9-174">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="515c9-175">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="515c9-176">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-176">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="515c9-177">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="515c9-177">Prepare your data</span></span>

1. <span data-ttu-id="515c9-178">[UCI Sentiment Labeled Sentences 데이터 세트 zip 파일(다음 참고의 인용 참조)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)을 다운로드하여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-178">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="515c9-179">만든 *Data* 디렉터리에 `yelp_labelled.txt` 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-179">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

> [!NOTE]
> <span data-ttu-id="515c9-180">이 자습서에서 사용하는 데이터 세트는 ‘From Group to Individual Labels using Deep Features’(Kotzias</span><span class="sxs-lookup"><span data-stu-id="515c9-180">The datasets this tutorial uses are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="515c9-181">외,</span><span class="sxs-lookup"><span data-stu-id="515c9-181">al,.</span></span> <span data-ttu-id="515c9-182">KDD 2015)에서 제공되고 UCI Machine Learning Repository(Dua, D. 및 Karra Taniskidou, E. (2017))에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="515c9-183">UCI Machine Learning Repository[http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="515c9-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="515c9-184">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="515c9-184">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

3. <span data-ttu-id="515c9-185">솔루션 탐색기에서 `yelp_labeled.txt` 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-185">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="515c9-186">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="515c9-187">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="515c9-187">Create classes and define paths</span></span>

<span data-ttu-id="515c9-188">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="515c9-189">최근에 다운로드한 데이터 세트 파일 경로 및 저장된 모델 파일 경로를 포함할 두 개의 전역 필드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-189">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* `_dataPath` <span data-ttu-id="515c9-190">에는 모델을 학습시키는 데 사용되는 데이터 세트의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-190">has the path to the dataset used to train the model.</span></span>
* `_modelPath` <span data-ttu-id="515c9-191">에는 학습된 모델이 저장되는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-191">has the path where the trained model is saved.</span></span>

<span data-ttu-id="515c9-192">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-192">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="515c9-193">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-193">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="515c9-194">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-194">Add a new class to your project:</span></span>

1. <span data-ttu-id="515c9-195">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-195">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="515c9-196">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-196">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="515c9-197">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-197">Then, select the **Add** button.</span></span>

    <span data-ttu-id="515c9-198">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-198">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="515c9-199">다음 `using` 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-199">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="515c9-200">기존 클래스 정의를 제거하고 두 개의 클래스 `SentimentData` 및 `SentimentPrediction`가 있는 다음 코드를 *SentimentData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-200">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="515c9-201">입력 데이터 세트 클래스인 `SentimentData`에는 댓글에 대한 `string`(`SentimentText`) 및 긍정적/부정적 감정 값을 나타내는 `bool`(`Sentiment`)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-201">The input dataset class, `SentimentData`, has a `string` for the comment (`SentimentText`) and a `bool` (`Sentiment`) that has a value for sentiment of either positive or negative.</span></span> <span data-ttu-id="515c9-202">두 필드에 모두 <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> 특성이 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-202">Both fields have <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> attributes attached to them.</span></span> <span data-ttu-id="515c9-203">이 특성은 데이터 파일의 각 필드 순서를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-203">This attribute describes the order of each field in the data file.</span></span>  <span data-ttu-id="515c9-204">또한 `Sentiment` 속성에는 필드를 `Label` 필드로 지정하는 <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-204">In addition, the `Sentiment` property has a <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> to designate it as the `Label` field.</span></span> `SentimentPrediction` <span data-ttu-id="515c9-205">은(는) 모델이 학습된 후 예측에 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-205">is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="515c9-206">여기에는 단일 부울(`Sentiment`)과 `PredictedLabel` `ColumnName` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-206">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="515c9-207">`Label`은 세트를 만들고 학습시키는 데 사용되며 분할된 테스트 데이터 세트와 함께 모델을 평가하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-207">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="515c9-208">`PredictedLabel`은 예측 및 평가 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-208">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="515c9-209">평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-209">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="515c9-210">ML .NET를 사용하여 모델을 작성하는 경우 먼저 <xref:Microsoft.ML.MLContext>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-210">When building a model with ML.NET you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> `MLContext` <span data-ttu-id="515c9-211">은(는) Entity Framework에서 `DbContext`를 사용하는 것과 비슷한 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-211">is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="515c9-212">환경은 예외 추적 및 로깅에 사용할 수 있는 ML 작업의 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-212">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="515c9-213">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="515c9-213">Initialize variables in Main</span></span>

<span data-ttu-id="515c9-214">`mlContext`라는 변수를 만들고 `MLContext`의 새 인스턴스로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-214">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="515c9-215">`Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-215">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

<span data-ttu-id="515c9-216">`Main` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

<span data-ttu-id="515c9-217">`LoadData` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-217">The `LoadData` method executes the following tasks:</span></span>

* <span data-ttu-id="515c9-218">데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-218">Loads the data.</span></span>
* <span data-ttu-id="515c9-219">로드된 데이터 세트를 학습 및 테스트 세트로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-219">Splits the loaded dataset into train and test datasets.</span></span>
* <span data-ttu-id="515c9-220">분할된 학습 및 테스트 데이터 세트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-220">Returns the split train and test datasets.</span></span>

<span data-ttu-id="515c9-221">다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `LoadData` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-221">Create the `LoadData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static TrainCatalogBase.TrainTestData LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a><span data-ttu-id="515c9-222">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="515c9-222">Load the data</span></span>

<span data-ttu-id="515c9-223">이전에 만든 `SentimentData` 데이터 모델 유형이 데이터 세트 스키마와 일치하므로 [LoadFromTextFile 메서드](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)에 대해 `MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 초기화, 매핑 및 데이터 세트 로드를 하나의 코드 줄로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-223">Since your previously created `SentimentData` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="515c9-224"><xref:Microsoft.Data.DataView.IDataView>가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-224">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> 

 <span data-ttu-id="515c9-225">`Transforms`의 입력 및 출력으로 사용되는 `DataView`는 `LINQ`의 `IEnumerable`과 비슷한 기본적인 데이터 파이프라인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-225">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="515c9-226">ML.NET에서 데이터는 SQL 뷰와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-226">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="515c9-227">지연 계산되고, 스키마화되며, 형식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-227">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="515c9-228">개체가 파이프라인의 첫 번째 부분이며 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-228">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="515c9-229">이 자습서에서 개체는 댓글과 해당하는 악의적 또는 비악의적 감정을 포함하는 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-229">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="515c9-230">이 데이터 세트는 모델을 만들고 학습시키는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-230">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="515c9-231">다음 코드를 `LoadData` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-231">Add the following code as the first line of the `LoadData` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="515c9-232">데이터 세트를 모델 학습 및 테스트용으로 분할</span><span class="sxs-lookup"><span data-stu-id="515c9-232">Split the dataset for model training and testing</span></span>

<span data-ttu-id="515c9-233">다음으로, 모델을 학습시키기 위한 학습 데이터 세트와 모델을 평가하기 위한 테스트 데이터 세트가 둘 다 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-233">Next, you need both a training dataset to train the model and a test dataset to evaluate the model.</span></span> <span data-ttu-id="515c9-234"><xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A>를 래핑하는 `MLContext.BinaryClassification.TrainTestSplit`를 사용하여 로드된 데이터 세트를 학습 및 테스트 데이터 세트로 분할하고 <xref:Microsoft.ML.TrainCatalogBase.TrainTestData> 내부에서 분할된 데이터 세트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-234">Use the `MLContext.BinaryClassification.TrainTestSplit` which wraps <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> to split the loaded dataset into train and test datasets and return them inside of a <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span></span> <span data-ttu-id="515c9-235">`testFraction` 매개 변수로 테스트 세트의 일부 데이터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-235">You can specify the fraction of data for the test set with the `testFraction`parameter.</span></span> <span data-ttu-id="515c9-236">기본값은 10%이지만, 이 경우에는 20%를 사용하여 평가에 더 많은 데이터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-236">The default is 10% but you use 20% in this case to use more data for the evaluation.</span></span>  

<span data-ttu-id="515c9-237">로드된 데이터를 필요한 데이터 세트로 분할하려면 `LoadData` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-237">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData` method:</span></span>

[!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

<span data-ttu-id="515c9-238">`splitDataView` 메서드의 끝에 `LoadData`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-238">Return the `splitDataView` at the end of the `LoadData` method:</span></span>

[!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="515c9-239">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="515c9-239">Build and train the model</span></span>

<span data-ttu-id="515c9-240">`BuildAndTrainModel` 메서드에 다음 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-240">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="515c9-241">`BuildAndTrainModel` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-241">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="515c9-242">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-242">Extracts and transforms the data.</span></span>
* <span data-ttu-id="515c9-243">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-243">Trains the model.</span></span>
* <span data-ttu-id="515c9-244">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-244">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="515c9-245">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-245">Returns the model.</span></span>

<span data-ttu-id="515c9-246">다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `BuildAndTrainModel` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-246">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

<span data-ttu-id="515c9-247">두 개의 매개 변수가 Train 메서드에 전달됩니다. 하나는 컨텍스트(`mlContext`)를 나타내는 `MLContext`이고, 다른 하나는 학습 데이터 세트(`splitTrainSet`)를 나타내는 `IDataView`입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-247">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and an `IDataView`for the training dataset (`splitTrainSet`).</span></span> 

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="515c9-248">데이터 추출 및 변환</span><span class="sxs-lookup"><span data-stu-id="515c9-248">Extract and transform the data</span></span>

<span data-ttu-id="515c9-249">데이터 전처리 및 정리는 데이터 세트가 기계 학습에 효과적으로 사용되기 전에 수행되는 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-249">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="515c9-250">원시 데이터는 종종 정리되지 않고 불안정하며 값이 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-250">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="515c9-251">이러한 모델링 작업 없이 데이터를 사용하면 잘못된 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-251">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="515c9-252">ML.NET의 변환 파이프라인은 학습 또는 테스트 전에 데이터에 적용되는 사용자 지정 변환 세트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-252">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="515c9-253">변환의 기본 목적은 데이터 [기능화](../resources/glossary.md#feature-engineering)입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-253">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="515c9-254">기계 학습 알고리즘은 [기능화된](../resources/glossary.md#feature) 데이터를 인식하므로 다음 단계는 텍스트 데이터를 ML 알고리즘이 인식하는 형식으로 변환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-254">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="515c9-255">해당 형식은 [숫자 벡터](../resources/glossary.md#numerical-feature-vector)입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-255">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="515c9-256">다음으로, 텍스트(`SentimentText`) 열을 기계 학습 알고리즘에서 사용되는 `Features`라는 숫자 벡터로 기능화하는 `mlContext.Transforms.Text.FeaturizeText`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-256">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="515c9-257">이는 실제로 파이프라인이 될 <xref:Microsoft.ML.Data.EstimatorChain%601>을 반환하는 래퍼 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-257">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="515c9-258">이 학습자를 `EstimatorChain`에 추가할 때 `pipeline`으로 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-258">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="515c9-259">아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-259">Add this as the next line of code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> <span data-ttu-id="515c9-260">ML.NET 버전 0.10은 변환 매개 변수의 순서를 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-260">ML.NET Version 0.10 changed the order of the Transform parameters.</span></span> <span data-ttu-id="515c9-261">이렇게 하면 애플리케이션을 실행하고 모델을 빌드할 때까지 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-261">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="515c9-262">이전 코드 조각에 설명된 것처럼 변환에 매개 변수 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-262">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="515c9-263">이것이 전처리/기능화 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-263">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="515c9-264">ML.NET에서 사용 가능한 추가 구성 요소를 사용하면 모델에서 더 나은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-264">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="515c9-265">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="515c9-265">Choose a learning algorithm</span></span>

<span data-ttu-id="515c9-266">학습자를 추가하려면 <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> 개체를 반환하는 `mlContext.BinaryClassification.Trainers.FastTree` 래퍼 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-266">To add the trainer, call the `mlContext.BinaryClassification.Trainers.FastTree` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="515c9-267">이 개체는 이 파이프라인에서 사용할 의사 결정 트리 학습자입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-267">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="515c9-268">`FastTreeBinaryClassificationTrainer`는 `pipeline`에 추가되며, 기록 데이터에서 학습할 기능화된 `SentimentText`(`Features`) 및 `Label` 입력 매개 변수를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-268">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="515c9-269">`BuildAndTrainModel` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-269">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="515c9-270">모델 학습</span><span class="sxs-lookup"><span data-stu-id="515c9-270">Train the model</span></span>

<span data-ttu-id="515c9-271">로드되고 변환된 데이터 세트를 기반으로 <xref:Microsoft.ML.Data.TransformerChain%601> 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-271">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="515c9-272">추정기가 정의된 후, 이미 로드된 학습 데이터를 제공하는 동시에 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> 메서드를 사용하여 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-272">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> method while providing the already loaded training data.</span></span> <span data-ttu-id="515c9-273">그러면 예측에 사용할 모델이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-273">This returns a model to use for predictions.</span></span> `pipeline.Fit()` <span data-ttu-id="515c9-274">은(는) 파이프라인을 학습시키고, 전달된 `DataView`에 따라 `Transformer`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-274">trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="515c9-275">`.Fit()` 메서드가 실행될 때까지 실험이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-275">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="515c9-276">`BuildAndTrainModel` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-276">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="515c9-277">평가에 사용하기 위해 학습된 모델 저장 및 반환</span><span class="sxs-lookup"><span data-stu-id="515c9-277">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="515c9-278">이 시점에는 기존 또는 새 .NET 애플리케이션에 통합할 수 있는 <xref:Microsoft.ML.Data.TransformerChain%601> 형식의 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-278">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="515c9-279">`BuildAndTrainModel` 메서드의 끝에 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-279">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="515c9-280">모델 평가</span><span class="sxs-lookup"><span data-stu-id="515c9-280">Evaluate the model</span></span>

<span data-ttu-id="515c9-281">이제 모델을 만들고 학습시켰으므로 품질 보증 및 유효성 검사를 위해 다른 데이터 세트를 사용하여 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-281">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="515c9-282">`Evaluate` 메서드에서는 `BuildAndTrainModel`에서 만들어진 모델을 전달하여 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-282">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="515c9-283">다음 코드와 같이 `BuildAndTrainModel` 바로 뒤에 `Evaluate` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-283">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

<span data-ttu-id="515c9-284">`Evaluate` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-284">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="515c9-285">테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-285">Loads the test dataset.</span></span>
* <span data-ttu-id="515c9-286">binaryclassification 평가기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-286">Creates the binaryclassification evaluator.</span></span>
* <span data-ttu-id="515c9-287">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-287">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="515c9-288">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-288">Displays the metrics.</span></span>

<span data-ttu-id="515c9-289">다음 코드를 사용하여 `Train` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-289">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

<span data-ttu-id="515c9-290">다음으로, 기계 학습 `model` 매개 변수(변환기)와 `splitTestSet` 매개 변수를 사용하여 기능을 입력하고 예측을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-290">Next, you'll use the machine learning `model` parameter (a transformer) and the `splitTestSet` parameter to input the features and return predictions.</span></span> <span data-ttu-id="515c9-291">`Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-291">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

<span data-ttu-id="515c9-292">`mlContext.BinaryClassification.Evaluate` 메서드는 지정된 데이터 세트를 사용하여 `PredictionModel`에 대한 품질 메트릭을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-292">The `mlContext.BinaryClassification.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="515c9-293">이진 분류 평가자가 계산한 전체 메트릭이 포함된 <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-293">It returns a <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> object that contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="515c9-294">모델의 품질을 확인하기 위해 이러한 메트릭을 표시하려면 먼저 메트릭을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-294">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="515c9-295">`Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-295">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="515c9-296">모델 유효성 검사를 위해 메트릭 표시</span><span class="sxs-lookup"><span data-stu-id="515c9-296">Displaying the metrics for model validation</span></span>

<span data-ttu-id="515c9-297">다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-297">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

<span data-ttu-id="515c9-298">반환하기 전에 모델을 .zip 파일로 저장하려면 `SaveModelAsFile` 메서드를 호출하는 아래 코드를 `Evaluate`에 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-298">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="515c9-299">모델을 .zip 파일로 저장</span><span class="sxs-lookup"><span data-stu-id="515c9-299">Save the model as a.zip file</span></span>

<span data-ttu-id="515c9-300">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `SaveModelAsFile` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-300">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="515c9-301">`SaveModelAsFile` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-301">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="515c9-302">모델을 .zip 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-302">Saves the model as a .zip file.</span></span>

<span data-ttu-id="515c9-303">다음으로, 다른 애플리케이션에서 다시 사용하고 이용할 수 있도록 모델을 저장하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-303">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="515c9-304">`ITransformer`에는 `_modelPath` 전역 필드를 사용하는 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 메서드와 <xref:System.IO.Stream>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-304">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="515c9-305">이 파일을 zip 파일로 저장하기 위해 `SaveTo` 메서드를 호출하기 직전에 `FileStream`을 만들겠습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-305">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="515c9-306">`SaveModelAsFile` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-306">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

<span data-ttu-id="515c9-307">다음 코드를 사용해서 `_modelPath`가 포함된 콘솔 메시지를 작성하여 파일이 작성된 위치를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-307">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="515c9-308">저장된 모델을 사용하여 테스트 데이터 결과 예측</span><span class="sxs-lookup"><span data-stu-id="515c9-308">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="515c9-309">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `UseModelWithSingleItem` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-309">Create the `UseModelWithSingleItem` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="515c9-310">`UseModelWithSingleItem` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-310">The `UseModelWithSingleItem` method executes the following tasks:</span></span>

* <span data-ttu-id="515c9-311">테스트 데이터의 단일 댓글을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-311">Creates a single comment of test data.</span></span>
* <span data-ttu-id="515c9-312">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-312">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="515c9-313">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-313">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="515c9-314">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-314">Displays the predicted results.</span></span>

<span data-ttu-id="515c9-315">다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-315">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

<span data-ttu-id="515c9-316">`model`은 여러 데이터 행에서 작동하는 `transformer`이지만, 일반적인 프로덕션 시나리오에서는 개별 예제에 대한 예측이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-316">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="515c9-317"><xref:Microsoft.ML.PredictionEngine%602>은 `CreatePredictionEngine` 메서드에서 반환되는 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-317">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="515c9-318">다음 코드를 추가하여 `PredictionEngine`을 `Predict` 메서드의 첫째 줄로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-318">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
<span data-ttu-id="515c9-319">`SentimentData` 인스턴스를 만들어 댓글을 추가하여 `Predict` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-319">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 <span data-ttu-id="515c9-320">해당 메서드를 사용하여 댓글 데이터의 단일 인스턴스에서 긍정적 또는 부정적 감정을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-320">You can use that to predict the positive or negative sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="515c9-321">예측을 가져오려면 데이터에 대해 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-321">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="515c9-322">입력 데이터는 문자열이고 모델은 기능화를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-322">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="515c9-323">파이프라인은 학습 및 예측 중에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-323">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="515c9-324">특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-324">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a><span data-ttu-id="515c9-325">모델 사용: 예측</span><span class="sxs-lookup"><span data-stu-id="515c9-325">Use the model: prediction</span></span>

<span data-ttu-id="515c9-326">결과를 공유하고 이에 따라 작업을 수행하기 위해 `SentimentText` 및 해당 감정 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-326">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="515c9-327">이것을 반환된 데이터를 운영 정책의 일부로 사용하는 연산화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-327">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="515c9-328">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과 표시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-328">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="515c9-329">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="515c9-329">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="515c9-330">다음 코드를 사용하여 `SaveModelAsFile` 메서드 바로 앞에 `UseLoadedModelWithBatchItems` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-330">Create the `UseLoadedModelWithBatchItems` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

<span data-ttu-id="515c9-331">`UseLoadedModelWithBatchItems` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-331">The `UseLoadedModelWithBatchItems` method executes the following tasks:</span></span>

* <span data-ttu-id="515c9-332">일괄 처리 테스트 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-332">Creates batch test data.</span></span>
* <span data-ttu-id="515c9-333">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-333">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="515c9-334">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-334">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="515c9-335">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-335">Displays the predicted results.</span></span>

<span data-ttu-id="515c9-336">다음 코드를 사용하여 `UseModelWithSingleItem` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-336">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

<span data-ttu-id="515c9-337">몇몇 댓글을 추가하여 `UseLoadedModelWithBatchItems` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-337">Add some comments to test the trained model's predictions in the `UseLoadedModelWithBatchItems` method:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

<span data-ttu-id="515c9-338">모델 로드</span><span class="sxs-lookup"><span data-stu-id="515c9-338">Load the model</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

<span data-ttu-id="515c9-339">이제 모델이 있으므로 해당 모델을 통해 <xref:Microsoft.ML.ITransformer.Transform%2A> 메서드를 사용하여 댓글 데이터의 악의적 또는 비악의적 감정을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-339">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="515c9-340">예측을 가져오려면 새 데이터에서 `Predict`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-340">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="515c9-341">입력 데이터는 문자열이고 모델은 기능화를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-341">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="515c9-342">파이프라인은 학습 및 예측 중에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-342">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="515c9-343">특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-343">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="515c9-344">예측을 위해 `UseLoadedModelWithBatchItems` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-344">Add the following code to the `UseLoadedModelWithBatchItems` method for the predictions:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a><span data-ttu-id="515c9-345">예측에 로드된 모델 사용</span><span class="sxs-lookup"><span data-stu-id="515c9-345">Use the loaded model for prediction</span></span>

<span data-ttu-id="515c9-346">결과를 공유하고 이에 따라 작업을 수행하기 위해 `SentimentText` 및 해당 감정 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-346">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="515c9-347">이것을 반환된 데이터를 운영 정책의 일부로 사용하는 연산화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-347">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="515c9-348">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과에 대한 헤더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-348">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="515c9-349">예측 결과를 표시하기 전에 감정과 예측을 결합하여 예측된 감정이 있는 원래 주석을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-349">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="515c9-350">다음 코드는 <xref:System.Linq.Enumerable.Zip%2A> 메서드를 사용하여 작업이 수행되도록 하므로, 다음으로 해당 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-350">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="515c9-351">이제 `SentimentText` 및 `Sentiment`를 클래스로 결합했으므로 <xref:System.Console.WriteLine?displayProperty=nameWithType> 메서드를 사용하여 결과를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-351">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

<span data-ttu-id="515c9-352">유추된 튜플 요소 이름은 C# 7.1의 새로운 기능이고 프로젝트의 기본 언어 버전은 C# 7.0이므로 언어 버전을 C# 7.1 이상으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-352">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="515c9-353">이 작업을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-353">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="515c9-354">**빌드** 탭을 선택하고 **고급** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-354">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="515c9-355">드롭다운에서 **C# 7.1**(또는 이상 버전)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-355">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="515c9-356">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-356">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="515c9-357">결과</span><span class="sxs-lookup"><span data-stu-id="515c9-357">Results</span></span>

<span data-ttu-id="515c9-358">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-358">Your results should be similar to the following.</span></span> <span data-ttu-id="515c9-359">파이프라인이 처리할 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-359">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="515c9-360">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-360">You may see warnings, or processing messages.</span></span> <span data-ttu-id="515c9-361">이해하기 쉽도록 이러한 결과는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-361">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="515c9-362">지금까지</span><span class="sxs-lookup"><span data-stu-id="515c9-362">Congratulations!</span></span> <span data-ttu-id="515c9-363">이제 메시지 감정을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-363">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> 

<span data-ttu-id="515c9-364">성공한 모델 빌드하는 것은 반복적인 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-364">Building successful models is an iterative process.</span></span> <span data-ttu-id="515c9-365">자습서에서는 작은 데이터 세트를 사용하여 빠른 모델 학습을 제공하므로 이 모델은 초기 품질이 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-365">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="515c9-366">모델 품질에 만족하지 않는 경우 더 큰 학습 데이터 세트를 제공하거나 각 알고리즘에 대한 다양한 하이퍼 매개 변수와 함께 다양한 학습 알고리즘을 선택하여 모델 품질을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-366">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span>

<span data-ttu-id="515c9-367">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-367">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="515c9-368">다음 단계</span><span class="sxs-lookup"><span data-stu-id="515c9-368">Next steps</span></span>

<span data-ttu-id="515c9-369">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="515c9-369">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="515c9-370">문제 이해</span><span class="sxs-lookup"><span data-stu-id="515c9-370">Understand the problem</span></span>
> * <span data-ttu-id="515c9-371">적절한 기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="515c9-371">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="515c9-372">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="515c9-372">Prepare your data</span></span>
> * <span data-ttu-id="515c9-373">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="515c9-373">Transform the data</span></span>
> * <span data-ttu-id="515c9-374">모델 학습</span><span class="sxs-lookup"><span data-stu-id="515c9-374">Train the model</span></span>
> * <span data-ttu-id="515c9-375">모델 평가</span><span class="sxs-lookup"><span data-stu-id="515c9-375">Evaluate the model</span></span>
> * <span data-ttu-id="515c9-376">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="515c9-376">Predict with the trained model</span></span>
> * <span data-ttu-id="515c9-377">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="515c9-377">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="515c9-378">다음 자습서로 이동하여 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="515c9-378">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="515c9-379">문제 분류</span><span class="sxs-lookup"><span data-stu-id="515c9-379">Issue Classification</span></span>](github-issue-classification.md)

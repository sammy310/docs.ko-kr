---
title: GitHub 문제 다중 클래스 분류 시나리오에서 ML.NET 사용
description: 다중 클래스 분류 시나리오에서 ML.NET을 사용하여 GitHub 문제를 분류하여 지정된 영역에 할당하는 방법을 알아봅니다.
ms.date: 02/20/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4f6a95fbd470c688c977b406d1813d6a453e8a79
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471482"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="a5b36-103">자습서: 다중 클래스 분류 시나리오에서 ML.NET을 사용하여 GitHub 문제 분류</span><span class="sxs-lookup"><span data-stu-id="a5b36-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="a5b36-104">이 샘플 자습서에서는 ML.NET을 사용하여 Visual Studio 2017에서 C#을 사용하는 .NET Core 콘솔 애플리케이션을 통해 GitHub 문제 분류자를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="a5b36-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="a5b36-106">문제 이해</span><span class="sxs-lookup"><span data-stu-id="a5b36-106">Understand the problem</span></span>
> * <span data-ttu-id="a5b36-107">적절한 기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="a5b36-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="a5b36-108">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="a5b36-108">Prepare your data</span></span>
> * <span data-ttu-id="a5b36-109">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="a5b36-109">Transform the data</span></span>
> * <span data-ttu-id="a5b36-110">모델 학습</span><span class="sxs-lookup"><span data-stu-id="a5b36-110">Train the model</span></span>
> * <span data-ttu-id="a5b36-111">모델 평가</span><span class="sxs-lookup"><span data-stu-id="a5b36-111">Evaluate the model</span></span>
> * <span data-ttu-id="a5b36-112">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="a5b36-112">Predict with the trained model</span></span>
> * <span data-ttu-id="a5b36-113">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="a5b36-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="a5b36-114">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="a5b36-115">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5b36-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="a5b36-116">이 자습서와 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-116">This tutorial and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="a5b36-117">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5b36-117">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="a5b36-118">GitHub 문제 샘플 개요</span><span class="sxs-lookup"><span data-stu-id="a5b36-118">GitHub issue sample overview</span></span>

<span data-ttu-id="a5b36-119">샘플은 ML.NET을 사용하여 GitHub 문제에 대한 영역 레이블을 분류하고 예측하는 모델을 학습시키는 콘솔 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-119">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="a5b36-120">또한 품질 분석을 위해 두 번째 데이터 세트를 사용하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-120">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="a5b36-121">문제 데이터 세트는 dotnet/corefx GitHub 리포지토리에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-121">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="a5b36-122">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-122">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5b36-123">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a5b36-123">Prerequisites</span></span>

* <span data-ttu-id="a5b36-124">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="a5b36-124">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="a5b36-125">[Github에서 탭 분리 파일(issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv)을 발행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-125">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="a5b36-126">[Github에서 테스트 탭 분리 파일(issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv)을 발행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-126">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="a5b36-127">기계 학습 워크플로</span><span class="sxs-lookup"><span data-stu-id="a5b36-127">Machine learning workflow</span></span>

<span data-ttu-id="a5b36-128">이 자습서는 프로세스가 체계적으로 이동할 수 있도록 하는 기계 학습 워크플로를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="a5b36-129">워크플로 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="a5b36-130">**문제 이해**</span><span class="sxs-lookup"><span data-stu-id="a5b36-130">**Understand the problem**</span></span>
2. <span data-ttu-id="a5b36-131">**데이터 준비**</span><span class="sxs-lookup"><span data-stu-id="a5b36-131">**Prepare your data**</span></span>
   * <span data-ttu-id="a5b36-132">**데이터 로드**</span><span class="sxs-lookup"><span data-stu-id="a5b36-132">**Load the data**</span></span>
   * <span data-ttu-id="a5b36-133">**기능 추출(데이터 변환)**</span><span class="sxs-lookup"><span data-stu-id="a5b36-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="a5b36-134">**빌드 및 학습**</span><span class="sxs-lookup"><span data-stu-id="a5b36-134">**Build and train**</span></span> 
   * <span data-ttu-id="a5b36-135">**모델 학습**</span><span class="sxs-lookup"><span data-stu-id="a5b36-135">**Train the model**</span></span>
   * <span data-ttu-id="a5b36-136">**모델 평가**</span><span class="sxs-lookup"><span data-stu-id="a5b36-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="a5b36-137">**모델 배포**</span><span class="sxs-lookup"><span data-stu-id="a5b36-137">**Deploy Model**</span></span>
   * <span data-ttu-id="a5b36-138">**예측 모델 사용**</span><span class="sxs-lookup"><span data-stu-id="a5b36-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="a5b36-139">문제 이해</span><span class="sxs-lookup"><span data-stu-id="a5b36-139">Understand the problem</span></span>

<span data-ttu-id="a5b36-140">먼저 문제를 이해해야 하므로 모델 빌드 및 학습을 지원할 수 있는 부분으로 문제를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="a5b36-141">문제를 구분하면 결과를 예측하고 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-141">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="a5b36-142">이 자습서의 문제점은 들어오는 GitHub 문제가 속해 있는 영역을 이해하여 우선순위 지정 및 스케줄링을 위해 올바르게 레이블을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-142">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="a5b36-143">문제를 다음과 같은 파트로 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-143">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="a5b36-144">문제 제목 텍스트</span><span class="sxs-lookup"><span data-stu-id="a5b36-144">the issue title text</span></span>
* <span data-ttu-id="a5b36-145">문제 설명 텍스트</span><span class="sxs-lookup"><span data-stu-id="a5b36-145">the issue description text</span></span>
* <span data-ttu-id="a5b36-146">모델 학습 데이터에 대한 영역 값</span><span class="sxs-lookup"><span data-stu-id="a5b36-146">an area value for the model training data</span></span>
* <span data-ttu-id="a5b36-147">평가한 다음, 작동 가능하게 사용할 수 있는 예측된 영역 값</span><span class="sxs-lookup"><span data-stu-id="a5b36-147">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="a5b36-148">그런 다음, 기계 학습 작업 선택에 도움이 되는 영역을 **확인**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-148">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="a5b36-149">적절한 기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="a5b36-149">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="a5b36-150">이 문제에서 다음 사실을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-150">With this problem, you know the following facts:</span></span>

<span data-ttu-id="a5b36-151">학습 데이터:</span><span class="sxs-lookup"><span data-stu-id="a5b36-151">Training data:</span></span>

<span data-ttu-id="a5b36-152">다음 예제와 같이 GitHub 문제는 여러 영역(**Area**)에 레이블을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-152">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="a5b36-153">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="a5b36-153">area-System.Numerics</span></span>
* <span data-ttu-id="a5b36-154">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="a5b36-154">area-System.Xml</span></span>
* <span data-ttu-id="a5b36-155">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="a5b36-155">area-Infrastructure</span></span>
* <span data-ttu-id="a5b36-156">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="a5b36-156">area-System.Linq</span></span>
* <span data-ttu-id="a5b36-157">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="a5b36-157">area-System.IO</span></span>

<span data-ttu-id="a5b36-158">다음 예제와 같이 새 GitHub 문제의 **영역**을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-158">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="a5b36-159">Contract.Assert 대 Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="a5b36-159">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="a5b36-160">System.Xml에서 읽기 전용으로 필드 만들기</span><span class="sxs-lookup"><span data-stu-id="a5b36-160">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="a5b36-161">이 시나리오에서는 분류 기계 학습 알고리즘이 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-161">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="a5b36-162">분류 학습 알고리즘 정보</span><span class="sxs-lookup"><span data-stu-id="a5b36-162">About the classification learning algorithm</span></span>

<span data-ttu-id="a5b36-163">분류는 데이터를 사용하여 데이터 항목 또는 행의 범주, 형식 또는 클래스를 **확인**하는 기계 학습 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-163">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="a5b36-164">예를 들어 분류를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-164">For example, you can use classification to:</span></span>

* <span data-ttu-id="a5b36-165">감정을 긍정적 또는 부정적으로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-165">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="a5b36-166">전자 메일을 스팸, 정크 또는 정상으로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-166">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="a5b36-167">환자의 실험실 샘플이 종양성인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-167">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="a5b36-168">영업 캠페인에 응답하는 고객의 성향을 기준으로 고객을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-168">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="a5b36-169">일반적으로 분류 학습 알고리즘 사용 사례는 다음과 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-169">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="a5b36-170">이진: A 또는 B.</span><span class="sxs-lookup"><span data-stu-id="a5b36-170">Binary: either A or B.</span></span>
* <span data-ttu-id="a5b36-171">다중 클래스: 단일 모델을 사용하여 예측할 수 있는 여러 범주.</span><span class="sxs-lookup"><span data-stu-id="a5b36-171">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="a5b36-172">이러한 유형의 문제에는 다중 클래스 분류 학습 알고리즘을 사용합니다. 문제 범주 예측이 단 2개(이진)가 아닌 여러 범주(다중 클래스) 중 하나일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-172">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="a5b36-173">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="a5b36-173">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="a5b36-174">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a5b36-174">Create a project</span></span>

1. <span data-ttu-id="a5b36-175">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-175">Open Visual Studio 2017.</span></span> <span data-ttu-id="a5b36-176">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-176">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="a5b36-177">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-177">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="a5b36-178">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-178">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="a5b36-179">**이름** 텍스트 상자에 "GitHubIssueClassification"을 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-179">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="a5b36-180">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-180">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="a5b36-181">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-181">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="a5b36-182">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-182">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="a5b36-183">프로젝트에서 *Models* 디렉터리를 만들어 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-183">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="a5b36-184">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-184">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="a5b36-185">"Models"를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-185">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="a5b36-186">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-186">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a5b36-187">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-187">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a5b36-188">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-188">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a5b36-189">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-189">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="a5b36-190">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="a5b36-190">Prepare your data</span></span>

1. <span data-ttu-id="a5b36-191">[issues-train.csv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) 및 [issues-test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) 데이터 세트를 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-191">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="a5b36-192">첫 번째 데이터 세트는 기계 학습 모델을 교육하고 두 번째 데이터 세트는 모델이 얼마나 정확한지 평가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-192">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="a5b36-193">솔루션 탐색기에서 각 \*.tsv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-193">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="a5b36-194">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-194">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="a5b36-195">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="a5b36-195">Create classes and define paths</span></span>

<span data-ttu-id="a5b36-196">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-196">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="a5b36-197">최근에 다운로드한 파일의 경로와 `MLContext`,`DataView`, `PredictionEngine` 및 `TextLoader`의 글로벌 변수가 포함될 세 개의 글로벌 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-197">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="a5b36-198">`_trainDataPath`에는 모델을 학습시키는 데 사용되는 데이터 세트의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-198">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="a5b36-199">`_testDataPath`에는 모델을 평가하는 데 사용되는 데이터 세트의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-199">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="a5b36-200">`_modelPath`에는 학습된 모델이 저장되는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-200">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="a5b36-201">`_mlContext`는 처리 컨텍스트를 제공하는 <xref:Microsoft.ML.MLContext>입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-201">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="a5b36-202">`_trainingDataView`는 학습 데이터 세트를 처리하는 데 사용되는 <xref:Microsoft.Data.DataView.IDataView>입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-202">`_trainingDataView` is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="a5b36-203">`_predEngine`은 단일 예측에 사용되는 <xref:Microsoft.ML.PredictionEngine%602>입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-203">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="a5b36-204">`_reader`는 데이터 세트를 로드하고 변환하는 데 사용되는 <xref:Microsoft.ML.Data.TextLoader>입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-204">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="a5b36-205">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로와 다른 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-205">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="a5b36-206">입력 데이터 및 예측에 대한 일부 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-206">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="a5b36-207">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-207">Add a new class to your project:</span></span>

1. <span data-ttu-id="a5b36-208">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-208">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="a5b36-209">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *GitHubIssueData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-209">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="a5b36-210">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-210">Then, select the **Add** button.</span></span>

    <span data-ttu-id="a5b36-211">*GitHubIssueData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-211">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a5b36-212">다음 `using` 문을 *GitHubIssueData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-212">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="a5b36-213">기존 클래스 정의를 제거하고 두 개의 클래스 `GitHubIssue` 및 `IssuePrediction`이 있는 다음 코드를 *GitHubIssueData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-213">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="a5b36-214">`GitHubIssue`는 다음 입력 데이터 세트 클래스이며 다음 <xref:System.String> 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-214">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="a5b36-215">`ID`에 GitHub 문제 ID에 대한 값 포함</span><span class="sxs-lookup"><span data-stu-id="a5b36-215">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="a5b36-216">`Area`에 `Area` 레이블에 대한 값 포함</span><span class="sxs-lookup"><span data-stu-id="a5b36-216">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="a5b36-217">`Title`에 GitHub 문제 제목 포함</span><span class="sxs-lookup"><span data-stu-id="a5b36-217">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="a5b36-218">`Description`에 GitHub 문제 설명 포함</span><span class="sxs-lookup"><span data-stu-id="a5b36-218">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="a5b36-219">`IssuePrediction`은 모델이 학습된 후 예측에 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-219">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="a5b36-220">여기에는 단일 `string`(`Area`) 및 `PredictedLabel` `ColumnName` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-220">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="a5b36-221">`Label`은 세트를 만들고 학습시키는 데 사용되며 두 번째 데이터 세트와 함께 모델을 평가하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-221">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="a5b36-222">`PredictedLabel`은 예측 및 평가 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-222">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="a5b36-223">평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-223">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="a5b36-224">ML.NET를 사용하여 모델을 빌드하는 경우 먼저 <xref:Microsoft.ML.MLContext>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-224">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="a5b36-225">`MLContext`는 Entity Framework에서 `DbContext`를 사용하는 것과 비슷한 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-225">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="a5b36-226">환경은 예외 추적 및 로깅에 사용할 수 있는 ML 작업의 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-226">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="a5b36-227">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="a5b36-227">Initialize variables in Main</span></span>

<span data-ttu-id="a5b36-228">여러 학습에서 반복 가능한/결정적 결과를 얻기 위해 임의의 시드(`seed: 0`)가 있는 `MLContext`의 새 인스턴스로 `_mlContext` 글로벌 변수를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-228">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="a5b36-229">`Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-229">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="a5b36-230">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="a5b36-230">Load the data</span></span>

<span data-ttu-id="a5b36-231">그런 다음, `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> 글로벌 변수 초기화하고 `_trainDataPath` 매개 변수를 사용하여 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-231">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="a5b36-232">[`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer)의 입력 및 출력으로 사용되는 `DataView`는 `LINQ`에서 `IEnumerable`과 비슷한 기본적인 데이터 파이프라인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-232">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="a5b36-233">ML.NET에서 데이터는 `SQL view`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-233">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="a5b36-234">지연 계산되고, 스키마화되며, 형식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-234">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="a5b36-235">개체가 파이프라인의 첫 번째 부분이며 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-235">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="a5b36-236">이 자습서에서는 문제 제목, 설명 및 해당 영역 GitHub 레이블이 있는 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-236">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="a5b36-237">`DataView`는 모델을 만들고 학습시키는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-237">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="a5b36-238">이전에 만든 `GitHubIssue` 데이터 모델 유형이 데이터 세트 스키마와 일치하므로 초기화, 매핑 및 데이터 세트 로드를 하나의 코드 줄로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-238">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="a5b36-239">줄의 첫 번재 부분(`CreateTextLoader<GitHubIssue>(hasHeader: true)`)에서는 `GitHubIssue` 데이터 모델 형식의 데이터 세트 스키마를 추론하고 데이터 세트 헤더를 사용하여 <xref:Microsoft.ML.Data.TextLoader>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-239">The first part of the line (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferring the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="a5b36-240">이전에 `GitHubIssue` 클래스를 만들 때 데이터 스키마를 정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-240">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="a5b36-241">스키마의 경우:</span><span class="sxs-lookup"><span data-stu-id="a5b36-241">For your schema:</span></span>

* <span data-ttu-id="a5b36-242">첫 번째 열 `ID`(GitHub 문제 ID)</span><span class="sxs-lookup"><span data-stu-id="a5b36-242">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="a5b36-243">두 번째 열 `Area`(학습 예측)</span><span class="sxs-lookup"><span data-stu-id="a5b36-243">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="a5b36-244">세 번째 열 `Title`(GitHub 문제 제목)은 `Area`를 예측하는 데 사용되는 첫 번째 [기능](../resources/glossary.md##feature)입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-244">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="a5b36-245">네 번째 열 `Description`은 `Area`를 예측하는 데 사용되는 두 번째 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-245">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="a5b36-246">줄의 두 번째 부분(`.Read(_trainDataPath)`)에서는 `_trainDataPath`를 통해 `IDataView`(`_trainingDataView`) 글로벌 변수에 학습 텍스트 파일을 로드하는 데 <xref:Microsoft.ML.Data.TextLoader.Read%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-246">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="a5b36-247">`_trainingDataView` 글로벌 변수를 파이프라인에 사용하기 위해 초기화 및 로드하려면 `mlContext` 초기화 후에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-247">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="a5b36-248">`Main` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-248">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="a5b36-249">`ProcessData` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-249">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="a5b36-250">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-250">Extracts and transforms the data.</span></span>
* <span data-ttu-id="a5b36-251">처리 파이프라인을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-251">Returns the processing pipeline.</span></span>

<span data-ttu-id="a5b36-252">다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `ProcessData` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-252">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="a5b36-253">기능 추출 및 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="a5b36-253">Extract Features and transform the data</span></span>

<span data-ttu-id="a5b36-254">데이터 전처리 및 정리는 데이터 세트가 기계 학습에 효과적으로 사용되기 전에 수행되는 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-254">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="a5b36-255">원시 데이터는 종종 정리되지 않고 불안정하며 값이 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-255">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="a5b36-256">이러한 모델링 작업 없이 데이터를 사용하면 잘못된 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-256">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="a5b36-257">ML.NET의 변환 파이프라인은 학습 또는 테스트 전에 데이터에 적용되는 사용자 지정 `transforms` 세트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-257">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="a5b36-258">변환의 기본 목적은 데이터 [기능화](../resources/glossary.md#feature-engineering)입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-258">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="a5b36-259">기계 학습 알고리즘은 [기능화된](../resources/glossary.md#feature) 데이터를 인식하므로 다음 단계는 텍스트 데이터를 ML 알고리즘이 인식하는 형식으로 변환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-259">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="a5b36-260">해당 형식은 [숫자 벡터](../resources/glossary.md#numerical-feature-vector)입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-260">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="a5b36-261">다음 단계에서는 `GitHubIssue` 클래스에 정의된 이름으로 해당 열을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-261">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="a5b36-262">모델을 학습하고 평가할 때 기본적으로 **Label** 열의 값이 예측할 올바른 값으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-262">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="a5b36-263">`GitHubIssue`에 대한 Area GitHub 레이블을 예측하려면 `Area` 열을 **Label** 열로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-263">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="a5b36-264">이렇게 하려면 <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> 변환 클래스의 래퍼인 `MLContext.Transforms.Conversion.MapValueToKey`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-264">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="a5b36-265">`MapValueToKey`는 실제로 파이프라인이 될 <xref:Microsoft.ML.Data.EstimatorChain%601>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-265">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="a5b36-266">이 학습자를 `EstimatorChain`에 추가할 때 `pipeline`으로 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-266">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="a5b36-267">다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-267">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="a5b36-268">기능화는 각 열의 다른 값에 서로 다른 숫자 키 값을 할당하고 기계 학습 알고리즘에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-268">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="a5b36-269">다음으로, 텍스트(`Title` 및 `Description`) 열을 `TitleFeaturized` 및 `DescriptionFeaturized` 각각에서 숫자 벡터로 기능화하는 `mlContext.Transforms.Text.FeaturizeText`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-269">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="a5b36-270">다음 코드를 사용하여 두 열에 대한 기능화(featurization)를 파이프라인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-270">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="a5b36-271">ML.NET 버전 0.10은 변환 매개 변수의 순서를 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-271">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="a5b36-272">이렇게 하면 빌드할 때까지 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-272">This will not error out until you build.</span></span> <span data-ttu-id="a5b36-273">이전 코드 조각에 설명된 것처럼 변환에 매개 변수 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-273">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="a5b36-274">데이터 준비의 마지막 단계에서는 `Concatenate` 변환 클래스를 사용하여 모든 기능 열을 **Features** 열에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-274">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="a5b36-275">기본적으로, 학습 알고리즘은 **Features** 열의 기능만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-275">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="a5b36-276">다음 코드를 사용하여 이 변환을 파이프라인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-276">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="a5b36-277">다음으로, <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A>를 추가하여 DataView를 캐시합니다. 따라서 해당 캐시를 사용하여 데이터를 여러 번 반복하면 다음 코드를 사용하는 것처럼 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-277">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="a5b36-278">작거나 중간 규모의 데이터 세트에서는 AppendCacheCheckpoint를 사용하여 학습 시간을 단축하세요.</span><span class="sxs-lookup"><span data-stu-id="a5b36-278">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="a5b36-279">규모가 매우 큰 데이터 세트를 다룰 때는 사용하지 마세요(AppendCacheCheckpoint()를 제거).</span><span class="sxs-lookup"><span data-stu-id="a5b36-279">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="a5b36-280">`ProcessData` 메서드의 끝에 파이프라인을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-280">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="a5b36-281">이 단계는 전처리/기능화를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-281">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="a5b36-282">ML.NET에서 사용 가능한 추가 구성 요소를 사용하면 모델에서 더 나은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-282">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="a5b36-283">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="a5b36-283">Build and train the model</span></span>

<span data-ttu-id="a5b36-284">`BuildAndTrainModel` 메서드에 다음 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-284">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="a5b36-285">`BuildAndTrainModel` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-285">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="a5b36-286">학습 알고리즘 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-286">Creates the training algorithm class.</span></span>
* <span data-ttu-id="a5b36-287">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-287">Trains the model.</span></span>
* <span data-ttu-id="a5b36-288">학습 데이터를 기반으로 영역을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-288">Predicts area based on training data.</span></span>
* <span data-ttu-id="a5b36-289">모델을 `.zip` 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-289">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="a5b36-290">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-290">Returns the model.</span></span>

<span data-ttu-id="a5b36-291">다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `BuildAndTrainModel` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-291">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<KeyToValueMappingTransformer> BuildAndTrainModel(IDataView trainingDataView, EstimatorChain<ITransformer> pipeline)
{

}
```

<span data-ttu-id="a5b36-292">BuildAndTrainModel 메서드에는 학습 데이터 세트(`trainingDataView`)에 대한 `IDataView` 및 ProcessData(`pipeline`)에서 만든 처리 파이프라인에 대한 <xref:Microsoft.ML.Data.EstimatorChain%601>이라는 두 개의 매개 변수가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-292">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="a5b36-293">다음 코드를 `BuildAndTrainModel` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-293">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="a5b36-294">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="a5b36-294">Choose a learning algorithm</span></span>

<span data-ttu-id="a5b36-295">학습 알고리즘을 추가하려면 <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> 개체를 반환하는 `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` 래퍼 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-295">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="a5b36-296">`SdcaMultiClassTrainer`는 `pipeline`에 추가되고 기록 데이터에서 학습할 기능화된 `Title`, `Description`(`Features`) 및 `Label` 입력 매개 변수를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-296">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="a5b36-297">또한 레이블을 원래 읽기 가능한 상태로 반환하려면 값에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-297">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="a5b36-298">다음 코드를 사용하여 해당 작업 모두를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-298">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="a5b36-299">모델 학습</span><span class="sxs-lookup"><span data-stu-id="a5b36-299">Train the model</span></span>

<span data-ttu-id="a5b36-300">로드되고 변환된 데이터 세트를 기반으로 <xref:Microsoft.ML.Data.TransformerChain%601> 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-300">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="a5b36-301">추정기가 정의된 후, 이미 로드된 학습 데이터를 제공하는 동시에 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>을 사용하여 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-301">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="a5b36-302">이 메서드는 예측에 사용할 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-302">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="a5b36-303">`trainingPipeline.Fit()`은 파이프라인을 학습시키고, 전달된 `DataView`에 따라 `Transformer`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-303">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="a5b36-304">`.Fit()` 메서드가 실행될 때까지 실험이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-304">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="a5b36-305">`BuildAndTrainModel` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-305">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="a5b36-306">`model`은 여러 데이터 행에서 작동하는 `transformer`이지만, 개별 예제에 대한 예측은 일반적인 프로덕션 시나리오에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-306">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="a5b36-307"><xref:Microsoft.ML.PredictionEngine%602>은 `CreatePredictionEngine` 메서드에서 반환되는 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="a5b36-308">다음 코드를 추가하여 `PredictionEngine`을 `BuildAndTrainModel` 메서드의 다음 줄로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-308">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="a5b36-309">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="a5b36-309">Predict with the trained model</span></span>

<span data-ttu-id="a5b36-310">`GitHubIssue`의 인스턴스를 만들어 GitHub 문제를 추가하여 `Predict` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-310">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="a5b36-311">문제 데이터의 단일 인스턴스에 대한 `Area` 레이블을 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-311">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="a5b36-312">예측을 가져오려면 데이터에 대해 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-312">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="a5b36-313">입력 데이터는 문자열이고 모델에는 기능화가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-313">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="a5b36-314">파이프라인은 학습 및 예측 중에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-314">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="a5b36-315">특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-315">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="a5b36-316">모델 사용: 예측 결과</span><span class="sxs-lookup"><span data-stu-id="a5b36-316">Using the model: prediction results</span></span>

<span data-ttu-id="a5b36-317">결과를 공유하고 이에 따라 작업을 수행하기 위해 `GitHubIssue` 및 해당 `Area` 레이블 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-317">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="a5b36-318">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과 표시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="a5b36-319">평가에 사용하기 위해 학습된 모델 반환</span><span class="sxs-lookup"><span data-stu-id="a5b36-319">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="a5b36-320">`BuildAndTrainModel` 메서드의 끝에 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-320">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="a5b36-321">모델 평가</span><span class="sxs-lookup"><span data-stu-id="a5b36-321">Evaluate the model</span></span>

<span data-ttu-id="a5b36-322">이제 모델을 만들고 학습시켰으므로 품질 보증 및 유효성 검사를 위해 다른 데이터 세트를 사용하여 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-322">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="a5b36-323">`Evaluate` 메서드에서는 `BuildAndTrainModel`에서 만들어진 모델을 전달하여 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-323">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="a5b36-324">다음 코드와 같이 `BuildAndTrainModel` 바로 뒤에 `Evaluate` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-324">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="a5b36-325">`Evaluate` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-325">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="a5b36-326">테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-326">Loads the test dataset.</span></span>
* <span data-ttu-id="a5b36-327">다중 클래스 평가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-327">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="a5b36-328">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-328">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="a5b36-329">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-329">Displays the metrics.</span></span>

<span data-ttu-id="a5b36-330">다음 코드를 사용하여 `BuildAndTrainModel` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-330">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="a5b36-331">이전에 학습 데이터 세트를 사용했을 때처럼 초기화, 매핑 및 테스트 데이터 세트 로드를 하나의 코드 행에 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-331">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="a5b36-332">이 데이터 세트를 품질 검사로 사용하여 모델을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-332">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="a5b36-333">`Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-333">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="a5b36-334">`MulticlassClassificationContext.Evaluate`는 지정된 데이터 세트를 사용하여 모델의 품질 메트릭을 계산하는 <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> 메서드의 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-334">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="a5b36-335">다중 클래스 분류 평가자가 계산한 전체 메트릭을 포함하는 <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-335">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="a5b36-336">모델의 품질을 확인하기 위해 메트릭을 표시하려면 먼저 해당 메트릭을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-336">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="a5b36-337">기계 학습 `_trainedModel` 글로벌 변수(변환기)의 `Transform` 메서드를 사용하여 기능을 입력하고 예측을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-337">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="a5b36-338">`Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-338">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="a5b36-339">다중 클래스 분류에 대한 다음 메트릭이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-339">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="a5b36-340">마이크로 정확도 - 모든 샘플 클래스 쌍은 정확도 메트릭에 동일하게 기여합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-340">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="a5b36-341">마이크로 정확도를 가능한 한 1에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-341">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="a5b36-342">매크로 정확도 - 모든 클래스 정확도 메트릭에 동일하게 기여합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-342">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="a5b36-343">소수 클래스는 큰 클래스와 같은 가중치를 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-343">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="a5b36-344">매크로 정확도를 가능한 한 1에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-344">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="a5b36-345">로그 손실 - [로그 손실](../resources/glossary.md#log-loss)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5b36-345">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="a5b36-346">로그 손실을 가능한 한 0에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-346">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="a5b36-347">로그 손실 감소 - [-inf, 100]의 범위입니다. 여기서 100은 완벽한 예측이고 0은 평균 예측을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-347">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="a5b36-348">로그 손실 감소를 가능한 한 0에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-348">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="a5b36-349">모델 유효성 검사를 위해 메트릭 표시</span><span class="sxs-lookup"><span data-stu-id="a5b36-349">Displaying the metrics for model validation</span></span>

<span data-ttu-id="a5b36-350">다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-350">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="a5b36-351">학습되고 평가된 모델 저장</span><span class="sxs-lookup"><span data-stu-id="a5b36-351">Save the trained and evaluated model</span></span>

<span data-ttu-id="a5b36-352">이 시점에는 기존 또는 새 .NET 애플리케이션에 통합할 수 있는 <xref:Microsoft.ML.Data.TransformerChain%601> 형식의 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-352">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="a5b36-353">학습된 모델을 .zip 파일로 저장하려면 다음 코드를 추가하여 `SaveModelAsFile` 메서드를 `BuildAndTrainModel`에 다음 줄로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-353">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="a5b36-354">모델을 .zip 파일로 저장</span><span class="sxs-lookup"><span data-stu-id="a5b36-354">Save the model as a .zip file</span></span>

<span data-ttu-id="a5b36-355">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `SaveModelAsFile` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-355">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="a5b36-356">`SaveModelAsFile` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-356">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="a5b36-357">모델을 .zip 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-357">Saves the model as a .zip file.</span></span>

<span data-ttu-id="a5b36-358">다음으로, 다른 애플리케이션에서 다시 사용하고 이용할 수 있도록 모델을 저장하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-358">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="a5b36-359">`ITransformer`에는 `_modelPath` 전역 필드를 사용하는 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 메서드와 <xref:System.IO.Stream>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-359">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="a5b36-360">이 모델을 zip 파일로 저장하기 위해 `SaveTo` 메서드를 호출하기 직전에 `FileStream`을 만들겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-360">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="a5b36-361">`SaveModelAsFile` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-361">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="a5b36-362">다음 코드를 사용해서 `_modelPath`가 포함된 콘솔 메시지를 작성하여 파일이 작성된 위치를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-362">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="a5b36-363">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="a5b36-363">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="a5b36-364">다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-364">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="a5b36-365">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 (또한 `SaveModelAsFile` 메서드 바로 앞에) `PredictIssue` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-365">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="a5b36-366">`PredictIssue` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-366">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="a5b36-367">테스트 데이터의 단일 문제를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-367">Creates a single issue of test data.</span></span>
* <span data-ttu-id="a5b36-368">테스트 데이터를 기반으로 영역을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-368">Predicts Area based on test data.</span></span>
* <span data-ttu-id="a5b36-369">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-369">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="a5b36-370">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-370">Displays the predicted results.</span></span>

<span data-ttu-id="a5b36-371">먼저 다음 코드를 사용하여 이전에 저장한 모델을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-371">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="a5b36-372">`GitHubIssue`의 인스턴스를 만들어 GitHub 문제를 추가하여 `Predict` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-372">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="a5b36-373">이제 모델을 설정했으므로 GitHub 문제 데이터의 단일 인스턴스에 대한 Area GitHub 레이블을 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-373">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="a5b36-374">예측을 가져오려면 데이터에 대해 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-374">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="a5b36-375">입력 데이터는 문자열이고 모델에는 기능화가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-375">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="a5b36-376">파이프라인은 학습 및 예측 중에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-376">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="a5b36-377">특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-377">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="a5b36-378">예측을 위해 `PredictIssue` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-378">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="a5b36-379">예측에 로드된 모델 사용</span><span class="sxs-lookup"><span data-stu-id="a5b36-379">Using the loaded model for prediction</span></span>

<span data-ttu-id="a5b36-380">문제를 분류하고 이에 따라 조치를 취하기 위해 `Area`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-380">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="a5b36-381">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과 표시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-381">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="a5b36-382">결과</span><span class="sxs-lookup"><span data-stu-id="a5b36-382">Results</span></span>

<span data-ttu-id="a5b36-383">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-383">Your results should be similar to the following.</span></span> <span data-ttu-id="a5b36-384">파이프라인이 처리할 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-384">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="a5b36-385">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-385">You may see warnings, or processing messages.</span></span> <span data-ttu-id="a5b36-386">이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-386">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="a5b36-387">지금까지</span><span class="sxs-lookup"><span data-stu-id="a5b36-387">Congratulations!</span></span> <span data-ttu-id="a5b36-388">이제 GitHub 문제의 영역 레이블을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-388">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="a5b36-389">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-389">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5b36-390">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a5b36-390">Next steps</span></span>

<span data-ttu-id="a5b36-391">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b36-391">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="a5b36-392">문제 이해</span><span class="sxs-lookup"><span data-stu-id="a5b36-392">Understand the problem</span></span>
> * <span data-ttu-id="a5b36-393">적절한 기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="a5b36-393">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="a5b36-394">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="a5b36-394">Prepare your data</span></span>
> * <span data-ttu-id="a5b36-395">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="a5b36-395">Transform the data</span></span>
> * <span data-ttu-id="a5b36-396">모델 학습</span><span class="sxs-lookup"><span data-stu-id="a5b36-396">Train the model</span></span>
> * <span data-ttu-id="a5b36-397">모델 평가</span><span class="sxs-lookup"><span data-stu-id="a5b36-397">Evaluate the model</span></span>
> * <span data-ttu-id="a5b36-398">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="a5b36-398">Predict with the trained model</span></span>
> * <span data-ttu-id="a5b36-399">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="a5b36-399">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="a5b36-400">다음 자습서로 이동하여 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="a5b36-400">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a5b36-401">택시 요금 예측기</span><span class="sxs-lookup"><span data-stu-id="a5b36-401">Taxi Fare Predictor</span></span>](taxi-fare.md)

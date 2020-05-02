---
title: '자습서: 지원 문제 분류 - 다중 클래스 분류'
description: 다중 클래스 분류 시나리오에서 ML.NET을 사용하여 GitHub 문제를 분류하여 지정된 영역에 할당하는 방법을 알아봅니다.
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: f158b8dce81e00f652496cad4ec9217c516b3e9d
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739714"
---
# <a name="tutorial-categorize-support-issues-using-multiclass-classification-with-mlnet"></a><span data-ttu-id="af2a1-103">자습서: ML .NET에서 다중 클래스 분류를 사용하여 지원 문제 분류</span><span class="sxs-lookup"><span data-stu-id="af2a1-103">Tutorial: Categorize support issues using multiclass classification with ML.NET</span></span>

<span data-ttu-id="af2a1-104">이 샘플 자습서에서는 ML.NET을 사용하여 Visual Studio에서 C#을 사용하는 .NET Core 콘솔 애플리케이션을 통해 GitHub 문제를 분류하고 영역 레이블을 예측하는 모델을 학습하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier to train a model that classifies and predicts the Area label for a GitHub issue via a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="af2a1-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="af2a1-106">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="af2a1-106">Prepare your data</span></span>
> * <span data-ttu-id="af2a1-107">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="af2a1-107">Transform the data</span></span>
> * <span data-ttu-id="af2a1-108">모델 학습</span><span class="sxs-lookup"><span data-stu-id="af2a1-108">Train the model</span></span>
> * <span data-ttu-id="af2a1-109">모델 평가</span><span class="sxs-lookup"><span data-stu-id="af2a1-109">Evaluate the model</span></span>
> * <span data-ttu-id="af2a1-110">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="af2a1-110">Predict with the trained model</span></span>
> * <span data-ttu-id="af2a1-111">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="af2a1-111">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="af2a1-112">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-112">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af2a1-113">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="af2a1-113">Prerequisites</span></span>

* <span data-ttu-id="af2a1-114">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상 또는 Visual Studio 2017 버전 15.6 이상.</span><span class="sxs-lookup"><span data-stu-id="af2a1-114">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
* <span data-ttu-id="af2a1-115">[GitHub에서 탭 분리 파일(issues_train.tsv)을 발행](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv)합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-115">The [GitHub issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="af2a1-116">[GitHub에서 테스트 탭 분리 파일(issues_test.tsv)을 발행](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv)합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-116">The [GitHub issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="af2a1-117">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="af2a1-117">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="af2a1-118">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="af2a1-118">Create a project</span></span>

1. <span data-ttu-id="af2a1-119">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-119">Open Visual Studio 2017.</span></span> <span data-ttu-id="af2a1-120">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-120">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="af2a1-121">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-121">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="af2a1-122">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-122">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="af2a1-123">**이름** 텍스트 상자에 "GitHubIssueClassification"을 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-123">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="af2a1-124">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-124">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="af2a1-125">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="af2a1-126">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-126">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="af2a1-127">프로젝트에서 *Models* 디렉터리를 만들어 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-127">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="af2a1-128">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-128">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="af2a1-129">"Models"를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-129">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="af2a1-130">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-130">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="af2a1-131">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-131">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="af2a1-132">"nuget.org"를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고 **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-132">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="af2a1-133">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-133">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="af2a1-134">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="af2a1-134">Prepare your data</span></span>

1. <span data-ttu-id="af2a1-135">[issues-train.csv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) 및 [issues-test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) 데이터 세트를 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-135">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="af2a1-136">첫 번째 데이터 세트는 기계 학습 모델을 교육하고 두 번째 데이터 세트는 모델이 얼마나 정확한지 평가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-136">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="af2a1-137">솔루션 탐색기에서 각 \*.tsv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-137">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="af2a1-138">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="af2a1-139">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="af2a1-139">Create classes and define paths</span></span>

<span data-ttu-id="af2a1-140">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddUsings)]

<span data-ttu-id="af2a1-141">최근에 다운로드한 파일의 경로와 `MLContext`,`DataView` 및 `PredictionEngine`의 글로벌 변수가 포함될 세 개의 글로벌 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-141">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, and `PredictionEngine`:</span></span>

* <span data-ttu-id="af2a1-142">`_trainDataPath`에는 모델을 학습시키는 데 사용되는 데이터 세트의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-142">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="af2a1-143">`_testDataPath`에는 모델을 평가하는 데 사용되는 데이터 세트의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-143">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="af2a1-144">`_modelPath`에는 학습된 모델이 저장되는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-144">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="af2a1-145">`_mlContext`는 처리 컨텍스트를 제공하는 <xref:Microsoft.ML.MLContext>입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-145">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="af2a1-146">`_trainingDataView`는 학습 데이터 세트를 처리하는 데 사용되는 <xref:Microsoft.ML.IDataView>입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-146">`_trainingDataView` is the <xref:Microsoft.ML.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="af2a1-147">`_predEngine`은 단일 예측에 사용되는 <xref:Microsoft.ML.PredictionEngine%602>입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-147">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>

<span data-ttu-id="af2a1-148">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로와 다른 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-148">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="af2a1-149">입력 데이터 및 예측에 대한 일부 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-149">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="af2a1-150">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-150">Add a new class to your project:</span></span>

1. <span data-ttu-id="af2a1-151">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-151">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="af2a1-152">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *GitHubIssueData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-152">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="af2a1-153">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-153">Then, select the **Add** button.</span></span>

    <span data-ttu-id="af2a1-154">*GitHubIssueData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-154">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="af2a1-155">다음 `using` 문을 *GitHubIssueData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-155">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="af2a1-156">기존 클래스 정의를 제거하고 두 개의 클래스 `GitHubIssue` 및 `IssuePrediction`이 있는 다음 코드를 *GitHubIssueData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-156">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="af2a1-157">`label`은 예측할 열입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-157">The `label` is the column you want to predict.</span></span> <span data-ttu-id="af2a1-158">식별된 `Features`는 레이블 예측을 위해 모델에 제공하는 입력입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-158">The identified `Features` are the inputs you give the model to predict the Label.</span></span>

<span data-ttu-id="af2a1-159">[LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute)를 사용하여 데이터 세트에서 원본 열의 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-159">Use the [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="af2a1-160">`GitHubIssue`는 다음 입력 데이터 세트 클래스이며 다음 <xref:System.String> 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-160">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="af2a1-161">첫 번째 열 `ID`(GitHub 문제 ID)</span><span class="sxs-lookup"><span data-stu-id="af2a1-161">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="af2a1-162">두 번째 열 `Area`(학습 예측)</span><span class="sxs-lookup"><span data-stu-id="af2a1-162">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="af2a1-163">세 번째 열 `Title`(GitHub 문제 제목)은 `Area` 예측에 사용되는 첫 번째 `feature`입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-163">the third column `Title` (GitHub issue title) is the first `feature` used for predicting the `Area`</span></span>
* <span data-ttu-id="af2a1-164">네 번째 열 `Description`은 `Area` 예측에 사용되는 두 번째 `feature`입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-164">the fourth column  `Description` is the second `feature` used for predicting the `Area`</span></span>

<span data-ttu-id="af2a1-165">`IssuePrediction`은 모델이 학습된 후 예측에 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-165">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="af2a1-166">여기에는 단일 `string`(`Area`) 및 `PredictedLabel` `ColumnName` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-166">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span>  <span data-ttu-id="af2a1-167">`PredictedLabel`은 예측 및 평가 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-167">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="af2a1-168">평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-168">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="af2a1-169">모든 ML.NET 작업은 [MLContext 클래스](xref:Microsoft.ML.MLContext)에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-169">All ML.NET operations start in the [MLContext](xref:Microsoft.ML.MLContext) class.</span></span> <span data-ttu-id="af2a1-170">`mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-170">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="af2a1-171">개념적으로 `Entity Framework`의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-171">It's similar, conceptually, to `DBContext` in `Entity Framework`.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="af2a1-172">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="af2a1-172">Initialize variables in Main</span></span>

<span data-ttu-id="af2a1-173">여러 학습에서 반복 가능한/결정적 결과를 얻기 위해 임의의 시드(`seed: 0`)가 있는 `MLContext`의 새 인스턴스로 `_mlContext` 글로벌 변수를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-173">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="af2a1-174">`Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-174">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="af2a1-175">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="af2a1-175">Load the data</span></span>

<span data-ttu-id="af2a1-176">ML.NET은 숫자 또는 텍스트 테이블 형식 데이터를 설명하는 효율적인 방법으로 [IDataView 클래스](xref:Microsoft.ML.IDataView)를 유연하게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-176">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="af2a1-177">`IDataView`는 텍스트 파일을 또는 실시간으로 로드할 수 있습니다(예: SQL 데이터베이스 또는 로그 파일).</span><span class="sxs-lookup"><span data-stu-id="af2a1-177">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span>

<span data-ttu-id="af2a1-178">`_trainingDataView` 글로벌 변수를 파이프라인에 사용하기 위해 초기화 및 로드하려면 `mlContext` 초기화 후에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-178">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTrainData)]

<span data-ttu-id="af2a1-179">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)은 데이터 스키마를 정의하고 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-179">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="af2a1-180">데이터 경로 변수를 가져와서 `IDataView`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-180">It takes in the data path variables and returns an `IDataView`.</span></span>

<span data-ttu-id="af2a1-181">`Main` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-181">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallProcessData)]

<span data-ttu-id="af2a1-182">`ProcessData` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-182">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="af2a1-183">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-183">Extracts and transforms the data.</span></span>
* <span data-ttu-id="af2a1-184">처리 파이프라인을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-184">Returns the processing pipeline.</span></span>

<span data-ttu-id="af2a1-185">다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `ProcessData` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-185">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="af2a1-186">기능 추출 및 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="af2a1-186">Extract Features and transform the data</span></span>

<span data-ttu-id="af2a1-187">`GitHubIssue`에 대한 영역 GitHub 레이블을 예측하기 위해 [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 메서드를 사용하여 `Area` 열을 숫자 키 형식 `Label` 열로 변환하고(분류 알고리즘에서 허용하는 형식) 새 데이터 세트 열로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-187">As you want to predict the Area GitHub label for a `GitHubIssue`, use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform the `Area` column into a numeric key type `Label` column (a format accepted by classification algorithms) and add it as a new dataset column:</span></span>

[!code-csharp[MapValueToKey](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#MapValueToKey)]

<span data-ttu-id="af2a1-188">다음으로, 텍스트(`Title` 및 `Description`) 열을 `TitleFeaturized` 및 `DescriptionFeaturized` 각각에서 숫자 벡터로 변환하는 `mlContext.Transforms.Text.FeaturizeText`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-188">Next, call `mlContext.Transforms.Text.FeaturizeText`, which transforms the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="af2a1-189">다음 코드를 사용하여 두 열에 대한 기능화(featurization)를 파이프라인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-189">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#FeaturizeText)]

<span data-ttu-id="af2a1-190">데이터 준비의 마지막 단계에서는 [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) 메서드를 사용하여 모든 기능 열을 **Features** 열에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-190">The last step in data preparation combines all of the feature columns into the **Features** column using the [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) method.</span></span> <span data-ttu-id="af2a1-191">기본적으로, 학습 알고리즘은 **Features** 열의 기능만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-191">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="af2a1-192">다음 코드를 사용하여 이 변환을 파이프라인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-192">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Concatenate)]

 <span data-ttu-id="af2a1-193">다음으로, <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A>를 추가하여 DataView를 캐시합니다. 따라서 해당 캐시를 사용하여 데이터를 여러 번 반복하면 다음 코드를 사용하는 것처럼 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-193">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="af2a1-194">작거나 중간 규모의 데이터 세트에서는 AppendCacheCheckpoint를 사용하여 학습 시간을 단축하세요.</span><span class="sxs-lookup"><span data-stu-id="af2a1-194">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="af2a1-195">규모가 매우 큰 데이터 세트를 다룰 때는 사용하지 마세요(AppendCacheCheckpoint()를 제거).</span><span class="sxs-lookup"><span data-stu-id="af2a1-195">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="af2a1-196">`ProcessData` 메서드의 끝에 파이프라인을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-196">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnPipeline)]

<span data-ttu-id="af2a1-197">이 단계는 전처리/기능화를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-197">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="af2a1-198">ML.NET에서 사용 가능한 추가 구성 요소를 사용하면 모델에서 더 나은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-198">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="af2a1-199">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="af2a1-199">Build and train the model</span></span>

<span data-ttu-id="af2a1-200">`BuildAndTrainModel` 메서드에 다음 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-200">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="af2a1-201">`BuildAndTrainModel` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-201">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="af2a1-202">학습 알고리즘 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-202">Creates the training algorithm class.</span></span>
* <span data-ttu-id="af2a1-203">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-203">Trains the model.</span></span>
* <span data-ttu-id="af2a1-204">학습 데이터를 기반으로 영역을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-204">Predicts area based on training data.</span></span>
* <span data-ttu-id="af2a1-205">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-205">Returns the model.</span></span>

<span data-ttu-id="af2a1-206">다음 코드를 사용하여 `Main` 메서드 바로 뒤에 `BuildAndTrainModel` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-206">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

### <a name="about-the-classification-task"></a><span data-ttu-id="af2a1-207">분류 작업 정보</span><span class="sxs-lookup"><span data-stu-id="af2a1-207">About the classification task</span></span>

<span data-ttu-id="af2a1-208">분류는 데이터를 사용하여 데이터 항목 또는 행의 범주, 형식 또는 클래스를 **확인**하는 기계 학습 작업으로, 보통은 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-208">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data and is frequently one of the following types:</span></span>

* <span data-ttu-id="af2a1-209">이진: A 또는 B.</span><span class="sxs-lookup"><span data-stu-id="af2a1-209">Binary: either A or B.</span></span>
* <span data-ttu-id="af2a1-210">다중 클래스: 단일 모델을 사용하여 예측할 수 있는 여러 범주.</span><span class="sxs-lookup"><span data-stu-id="af2a1-210">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="af2a1-211">이러한 유형의 문제에는 다중 클래스 분류 학습 알고리즘을 사용합니다. 문제 범주 예측이 단 2개(이진)가 아닌 여러 범주(다중 클래스) 중 하나일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-211">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

<span data-ttu-id="af2a1-212">`BuildAndTrainModel()`의 첫 번째 코드 줄로 다음을 추가하여 데이터 변환 정의에 기계 학습 알고리즘을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-212">Append the machine learning algorithm to the data transformation definitions by adding the following as the first line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddTrainer](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTrainer)]

<span data-ttu-id="af2a1-213">[SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer)는 다중 클래스 분류 학습 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-213">The [SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) is your multiclass classification training algorithm.</span></span> <span data-ttu-id="af2a1-214">이것은 `pipeline`에 추가되고 기록 데이터에서 학습할 기능화된 `Title`, `Description`(`Features`) 및 `Label` 입력 매개 변수를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-214">This is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="af2a1-215">모델 학습</span><span class="sxs-lookup"><span data-stu-id="af2a1-215">Train the model</span></span>

<span data-ttu-id="af2a1-216">모델을 `splitTrainSet` 데이터에 맞추고 `BuildAndTrainModel()` 메서드에서 다음 줄의 코드로 다음 항목을 추가하여 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-216">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#TrainModel)]

<span data-ttu-id="af2a1-217">`Fit()` 메서드는 데이터 세트를 변환하고 학습을 적용하여 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-217">The `Fit()`method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="af2a1-218">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스를 전달한 다음, 이 단일 데이터 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-218">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span> <span data-ttu-id="af2a1-219">이 항목을 `BuildAndTrainModel()` 메서드에서 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-219">Add this as the next line in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[CreatePredictionEngine1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="af2a1-220">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="af2a1-220">Predict with the trained model</span></span>

<span data-ttu-id="af2a1-221">`GitHubIssue`의 인스턴스를 만들어 GitHub 문제를 추가하여 `Predict` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-221">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateTestIssue1)]

<span data-ttu-id="af2a1-222">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수를 사용하여 단일 데이터 행에 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-222">Use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="af2a1-223">모델 사용: 예측 결과</span><span class="sxs-lookup"><span data-stu-id="af2a1-223">Using the model: prediction results</span></span>

<span data-ttu-id="af2a1-224">결과를 공유하고 이에 따라 작업을 수행하기 위해 `GitHubIssue` 및 해당 `Area` 레이블 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-224">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="af2a1-225">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과 표시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-225">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="af2a1-226">평가에 사용하기 위해 학습된 모델 반환</span><span class="sxs-lookup"><span data-stu-id="af2a1-226">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="af2a1-227">`BuildAndTrainModel` 메서드의 끝에 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-227">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="af2a1-228">모델 평가</span><span class="sxs-lookup"><span data-stu-id="af2a1-228">Evaluate the model</span></span>

<span data-ttu-id="af2a1-229">이제 모델을 만들고 학습시켰으므로 품질 보증 및 유효성 검사를 위해 다른 데이터 세트를 사용하여 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-229">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="af2a1-230">`Evaluate` 메서드에서는 `BuildAndTrainModel`에서 만들어진 모델을 전달하여 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-230">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="af2a1-231">다음 코드와 같이 `BuildAndTrainModel` 바로 뒤에 `Evaluate` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-231">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(DataViewSchema trainingDataViewSchema)
{

}
```

<span data-ttu-id="af2a1-232">`Evaluate` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-232">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="af2a1-233">테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-233">Loads the test dataset.</span></span>
* <span data-ttu-id="af2a1-234">다중 클래스 평가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-234">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="af2a1-235">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-235">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="af2a1-236">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-236">Displays the metrics.</span></span>

<span data-ttu-id="af2a1-237">다음 코드를 사용하여 `BuildAndTrainModel` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-237">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallEvaluate)]

<span data-ttu-id="af2a1-238">앞의 학습 데이터 세트에서처럼 `Evaluate` 메서드에 다음 코드를 추가하여 테스트 데이트 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-238">As you did previously with the training dataset, load the test dataset by adding the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTestDataset)]

<span data-ttu-id="af2a1-239">[Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) 메서드는 지정된 데이터 세트를 사용하여 모델에 대한 품질 메트릭을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-239">The [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) method computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="af2a1-240">다중 클래스 분류 평가자가 계산한 전체 메트릭을 포함하는 <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-240">It returns a <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="af2a1-241">모델의 품질을 확인하기 위해 메트릭을 표시하려면 먼저 해당 메트릭을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-241">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="af2a1-242">기계 학습 `_trainedModel` 글로벌 변수([ITransformer](xref:Microsoft.ML.ITransformer))의 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 사용하여 기능을 입력하고 예측을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-242">Notice the use of the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the machine learning `_trainedModel` global variable (an [ITransformer](xref:Microsoft.ML.ITransformer)) to input the features and return predictions.</span></span> <span data-ttu-id="af2a1-243">`Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-243">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Evaluate)]

<span data-ttu-id="af2a1-244">다중 클래스 분류에 대한 다음 메트릭이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-244">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="af2a1-245">마이크로 정확도 - 모든 샘플 클래스 쌍은 정확도 메트릭에 동일하게 기여합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-245">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="af2a1-246">마이크로 정확도를 가능한 한 1에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-246">You want Micro Accuracy to be as close to one as possible.</span></span>

* <span data-ttu-id="af2a1-247">매크로 정확도 - 모든 클래스 정확도 메트릭에 동일하게 기여합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-247">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="af2a1-248">소수 클래스는 큰 클래스와 같은 가중치를 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-248">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="af2a1-249">매크로 정확도를 가능한 한 1에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-249">You want Macro Accuracy to be as close to one as possible.</span></span>

* <span data-ttu-id="af2a1-250">로그 손실 - [로그 손실](../resources/glossary.md#log-loss)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af2a1-250">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="af2a1-251">로그 손실을 가능한 한 0에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-251">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="af2a1-252">로그 손실 감소 - [-inf, 1.00]의 범위입니다. 여기서 1.00은 완벽한 예측이고 0은 평균 예측을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-252">Log-loss reduction - Ranges from [-inf, 1.00], where 1.00 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="af2a1-253">로그 손실 감소를 가능한 한 1에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-253">You want Log-loss reduction to be as close to one as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="af2a1-254">모델 유효성 검사를 위해 메트릭 표시</span><span class="sxs-lookup"><span data-stu-id="af2a1-254">Displaying the metrics for model validation</span></span>

<span data-ttu-id="af2a1-255">다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-255">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayMetrics)]

### <a name="save-the-model-to-a-file"></a><span data-ttu-id="af2a1-256">모델을 파일에 저장</span><span class="sxs-lookup"><span data-stu-id="af2a1-256">Save the model to a file</span></span>

<span data-ttu-id="af2a1-257">모델이 만족스러운 경우 나중에 또는 다른 애플리케이션에서 예측을 수행하기 위해 모델을 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-257">Once satisfied with your model, save it to a file to make predictions at a later time or in another application.</span></span> <span data-ttu-id="af2a1-258">`Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-258">Add the following code to the `Evaluate` method.</span></span>

[!code-csharp[SnippetCallSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetCallSaveModel)]

<span data-ttu-id="af2a1-259">`Evaluate` 메서드 아래 `SaveModelAsFile` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-259">Create the `SaveModelAsFile` method below your `Evaluate` method.</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext,DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

<span data-ttu-id="af2a1-260">`SaveModelAsFile` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-260">Add the following code to your `SaveModelAsFile` method.</span></span> <span data-ttu-id="af2a1-261">이 코드에서는 [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) 메서드를 사용하여 학습된 모델을 직렬화하고 zip 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-261">This code uses the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) method to serialize and store the trained model as a zip file.</span></span>

[!code-csharp[SnippetSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetSaveModel)]

## <a name="deploy-and-predict-with-a-model"></a><span data-ttu-id="af2a1-262">모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="af2a1-262">Deploy and Predict with a model</span></span>

<span data-ttu-id="af2a1-263">다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-263">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallPredictIssue)]

<span data-ttu-id="af2a1-264">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 (또한 `SaveModelAsFile` 메서드 바로 앞에) `PredictIssue` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-264">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="af2a1-265">`PredictIssue` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-265">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="af2a1-266">저장된 모델 로드</span><span class="sxs-lookup"><span data-stu-id="af2a1-266">Loads the saved model</span></span>
* <span data-ttu-id="af2a1-267">테스트 데이터의 단일 문제를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-267">Creates a single issue of test data.</span></span>
* <span data-ttu-id="af2a1-268">테스트 데이터를 기반으로 영역을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-268">Predicts Area based on test data.</span></span>
* <span data-ttu-id="af2a1-269">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-269">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="af2a1-270">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-270">Displays the predicted results.</span></span>

<span data-ttu-id="af2a1-271">다음 코드를 `PredictIssue` 메서드에 추가하여 저장된 모델을 애플리케이션에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-271">Load the saved model into your application by adding the following code to the `PredictIssue` method:</span></span>

[!code-csharp[SnippetLoadModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetLoadModel)]

<span data-ttu-id="af2a1-272">`GitHubIssue`의 인스턴스를 만들어 GitHub 문제를 추가하여 `Predict` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-272">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTestIssue)]

<span data-ttu-id="af2a1-273">이전에 수행한 것처럼 다음 코드로 `PredictionEngine` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-273">As you did previously, create a `PredictionEngine` instance with the following code:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine)]

<span data-ttu-id="af2a1-274">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-274">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="af2a1-275">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-275">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="af2a1-276">단일 스레드 또는 프로토타입 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-276">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="af2a1-277">프로덕션 환경에서 성능 및 스레드 보안을 개선하려면 `PredictionEnginePool` 서비스를 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-277">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="af2a1-278">[ASP.NET Core Web API에서 `PredictionEnginePool`을 사용하는 방법](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)에 대한 이 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af2a1-278">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="af2a1-279">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-279">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="af2a1-280">`PredictionEngine`을 사용하여 예측을 위해 다음 코드를 `PredictIssue` 메서드에 추가하여 영역 GitHub 레이블을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-280">Use the `PredictionEngine` to predict the Area GitHub label by adding the following code to the `PredictIssue` method for the prediction:</span></span>

[!code-csharp[PredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="af2a1-281">예측에 로드된 모델 사용</span><span class="sxs-lookup"><span data-stu-id="af2a1-281">Using the loaded model for prediction</span></span>

<span data-ttu-id="af2a1-282">문제를 분류하고 이에 따라 조치를 취하기 위해 `Area`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-282">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="af2a1-283">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 결과 표시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-283">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="af2a1-284">결과</span><span class="sxs-lookup"><span data-stu-id="af2a1-284">Results</span></span>

<span data-ttu-id="af2a1-285">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-285">Your results should be similar to the following.</span></span> <span data-ttu-id="af2a1-286">파이프라인이 처리할 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-286">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="af2a1-287">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="af2a1-288">이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-288">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.738
*       MacroAccuracy:    0.668
*       LogLoss:          .919
*       LogLossReduction: .643
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="af2a1-289">지금까지</span><span class="sxs-lookup"><span data-stu-id="af2a1-289">Congratulations!</span></span> <span data-ttu-id="af2a1-290">이제 GitHub 문제의 영역 레이블을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-290">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="af2a1-291">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-291">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af2a1-292">다음 단계</span><span class="sxs-lookup"><span data-stu-id="af2a1-292">Next steps</span></span>

<span data-ttu-id="af2a1-293">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="af2a1-293">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="af2a1-294">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="af2a1-294">Prepare your data</span></span>
> * <span data-ttu-id="af2a1-295">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="af2a1-295">Transform the data</span></span>
> * <span data-ttu-id="af2a1-296">모델 학습</span><span class="sxs-lookup"><span data-stu-id="af2a1-296">Train the model</span></span>
> * <span data-ttu-id="af2a1-297">모델 평가</span><span class="sxs-lookup"><span data-stu-id="af2a1-297">Evaluate the model</span></span>
> * <span data-ttu-id="af2a1-298">학습된 모델을 통해 예측</span><span class="sxs-lookup"><span data-stu-id="af2a1-298">Predict with the trained model</span></span>
> * <span data-ttu-id="af2a1-299">로드된 모델을 통해 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="af2a1-299">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="af2a1-300">다음 자습서로 이동하여 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="af2a1-300">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="af2a1-301">택시 요금 예측기</span><span class="sxs-lookup"><span data-stu-id="af2a1-301">Taxi Fare Predictor</span></span>](predict-prices.md)

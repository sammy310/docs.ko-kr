---
title: '자습서: 영화 추천기 빌드 - 행렬 인수분해'
description: 이 자습서에서는 .NET Core 콘솔 애플리케이션에서 ML.NET으로 영화 추천기를 빌드하는 방법을 보여 줍니다. 이 단계에서는 C#과 Visual Studio 2019를 사용합니다.
author: briacht
ms.date: 09/30/2019
ms.custom: mvc, title-hack-0516
ms.topic: tutorial
ms.openlocfilehash: 51dcf5cd85913f0e69ea51dff5101426cc57390f
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774458"
---
# <a name="tutorial-build-a-movie-recommender-using-matrix-factorizaton-with-mlnet"></a><span data-ttu-id="4b56f-104">자습서: ML.NET에서 행렬 인수분해를 사용하여 영화 추천기 빌드</span><span class="sxs-lookup"><span data-stu-id="4b56f-104">Tutorial: Build a movie recommender using matrix factorizaton with ML.NET</span></span>

<span data-ttu-id="4b56f-105">이 자습서에서는 .NET Core 콘솔 애플리케이션에서 ML.NET으로 영화 추천기를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-105">This tutorial shows you how to build a movie recommender with ML.NET in a .NET Core console application.</span></span> <span data-ttu-id="4b56f-106">이 단계에서는 C#과 Visual Studio 2019를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-106">The steps use C# and Visual Studio 2019.</span></span>

<span data-ttu-id="4b56f-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="4b56f-108">기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="4b56f-108">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="4b56f-109">데이터 준비 및 로드</span><span class="sxs-lookup"><span data-stu-id="4b56f-109">Prepare and load your data</span></span>
> * <span data-ttu-id="4b56f-110">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="4b56f-110">Build and train a model</span></span>
> * <span data-ttu-id="4b56f-111">모델 평가</span><span class="sxs-lookup"><span data-stu-id="4b56f-111">Evaluate a model</span></span>
> * <span data-ttu-id="4b56f-112">모델 배포 및 사용</span><span class="sxs-lookup"><span data-stu-id="4b56f-112">Deploy and consume a model</span></span>

<span data-ttu-id="4b56f-113">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="4b56f-114">기계 학습 워크플로</span><span class="sxs-lookup"><span data-stu-id="4b56f-114">Machine learning workflow</span></span>

<span data-ttu-id="4b56f-115">다음 단계를 수행하여 기타 모든 ML.NET 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-115">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="4b56f-116">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="4b56f-116">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="4b56f-117">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="4b56f-117">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="4b56f-118">모델 평가</span><span class="sxs-lookup"><span data-stu-id="4b56f-118">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="4b56f-119">모델 사용</span><span class="sxs-lookup"><span data-stu-id="4b56f-119">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="4b56f-120">전제 조건</span><span class="sxs-lookup"><span data-stu-id="4b56f-120">Prerequisites</span></span>

* <span data-ttu-id="4b56f-121">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 버전 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)</span><span class="sxs-lookup"><span data-stu-id="4b56f-121">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="4b56f-122">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="4b56f-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="4b56f-123">영화 목록을 추천하거나 관련 제품 목록을 권장하는 것과 같은 몇 가지 방법으로 권장 문제에 접근할 수 있지만, 이 경우 사용자가 특정 영화에 어떤 등급(1-5)을 부여할지 예측하고 정의된 임계값(등급이 높을수록 사용자가 특정 영화를 좋아할 가능성이 높음)이 높을수록 해당 영화를 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-123">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="4b56f-124">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="4b56f-124">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="4b56f-125">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4b56f-125">Create a project</span></span>

1. <span data-ttu-id="4b56f-126">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="4b56f-127">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="4b56f-128">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="4b56f-129">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="4b56f-130">**이름** 텍스트 상자에 "MovieRecommender"를 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-130">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="4b56f-131">프로젝트에 *Data*라는 디렉터리를 만들어 데이터 세트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-131">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="4b56f-132">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="4b56f-133">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-133">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="4b56f-134">**Microsoft.ML** 및 **Microsoft.ML.Recommender** NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-134">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    <span data-ttu-id="4b56f-135">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="4b56f-136">"nuget.org"를 패키지 소스로 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="4b56f-137">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="4b56f-138">**Microsoft.ML.Recommender**에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-138">Repeat these steps for **Microsoft.ML.Recommender**.</span></span>

4. <span data-ttu-id="4b56f-139">*Program.cs* 파일 맨 위에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-139">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[UsingStatements](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="4b56f-140">데이터 다운로드</span><span class="sxs-lookup"><span data-stu-id="4b56f-140">Download your data</span></span>

1. <span data-ttu-id="4b56f-141">두 개의 데이터 세트를 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-141">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="4b56f-142">[*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv)를 마우스 오른쪽 단추로 클릭하고 "링크(또는 대상)를 다른 이름으로 저장..."을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-142">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
   * <span data-ttu-id="4b56f-143">[*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv)를 마우스 오른쪽 단추로 클릭하고 "링크(또는 대상)를 다른 이름으로 저장..."을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-143">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="4b56f-144">\*.csv 파일을 *Data* 폴더에 저장하거나 다른 곳에 저장한 후 \*.csv 파일을 *Data* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-144">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="4b56f-145">솔루션 탐색기에서 각 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="4b56f-146">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![VS의 최신 버전이면 복사](./media/movie-recommendation/copytoout.gif)

## <a name="load-your-data"></a><span data-ttu-id="4b56f-148">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="4b56f-148">Load your data</span></span>

<span data-ttu-id="4b56f-149">ML.NET 프로세스의 첫 번째 단계는 모델 학습 및 테스트 데이터를 준비하고 로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-149">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="4b56f-150">권장 등급 데이터는 `Train` 및 `Test` 데이터 세트로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-150">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="4b56f-151">`Train` 데이터는 모델에 맞게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-151">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="4b56f-152">`Test` 데이터는 학습된 모델로 예측하고 모델 성능을 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-152">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="4b56f-153">`Train` 및 `Test` 데이터로 80/20 분할을 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-153">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="4b56f-154">다음은 \*.csv 파일의 데이터 미리 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-154">Below is a preview of the data from your \*.csv files:</span></span>

![데이터 미리 보기](./media/movie-recommendation/csv-dataset-preview.png)

<span data-ttu-id="4b56f-156">\*.csv 파일에는 다음 네 개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-156">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="4b56f-157">기계 학습에서 예측을 수행하는 데 사용되는 열을 [Features](../resources/glossary.md#feature)라고 하고, 반환된 예측이 있는 열을 [Label](../resources/glossary.md#label)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-157">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="4b56f-158">영화 등급을 예측하려는 경우 등급 열은 `Label`입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-158">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="4b56f-159">다른 세 개의 열 `userId`, `movieId` 및 `timestamp`는 모두 `Features`가 `Label`을 예측하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-159">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="4b56f-160">기능</span><span class="sxs-lookup"><span data-stu-id="4b56f-160">Features</span></span>      | <span data-ttu-id="4b56f-161">레이블</span><span class="sxs-lookup"><span data-stu-id="4b56f-161">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

<span data-ttu-id="4b56f-162">`Label`을 예측하는 데 사용되는 `Features`를 결정하는 것은 사용자에게 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-162">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="4b56f-163">또한 [Feature Permutation 중요도](../how-to-guides/determine-global-feature-importance-in-model.md)와 같은 방법을 사용하여 최상의 `Features`를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-163">You can also use methods like [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="4b56f-164">이 경우, 타임스탬프는 사용자가 특정 영화를 평가하는 방식에 실제로 영향을 주지 않고 더 정확한 예측에 기여하지 않기 때문에 `timestamp` 열을 `Feature`로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-164">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="4b56f-165">기능</span><span class="sxs-lookup"><span data-stu-id="4b56f-165">Features</span></span>      | <span data-ttu-id="4b56f-166">레이블</span><span class="sxs-lookup"><span data-stu-id="4b56f-166">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

<span data-ttu-id="4b56f-167">다음으로, 입력 클래스에 대한 데이터 구조를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-167">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="4b56f-168">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-168">Add a new class to your project:</span></span>

1. <span data-ttu-id="4b56f-169">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-169">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="4b56f-170">**새 항목 추가 대화 상자**에서 **클래스**를 선택하고 **이름** 필드를 *MovieRatingData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-170">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="4b56f-171">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-171">Then, select the **Add** button.</span></span>

<span data-ttu-id="4b56f-172">*MovieRatingData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-172">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="4b56f-173">다음 `using` 문을 *MovieRatingData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-173">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="4b56f-174">기존 클래스 정의를 제거하고 *MovieRatingData.cs*에 다음 코드를 추가하여 `MovieRating`라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-174">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

<span data-ttu-id="4b56f-175">`MovieRating`은 입력 데이터 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-175">`MovieRating` specifies an input data class.</span></span> <span data-ttu-id="4b56f-176">[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 특성은 데이터 세트에서 로드해야 하는 열(열 인덱스 기준)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-176">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="4b56f-177">`userId` 및 `movieId` 열은 `Features`(모델에서 `Label`을 예측하기 위해 제공하는 입력)이고, 등급 열은 예측할 `Label`(모델의 출력)입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-177">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="4b56f-178">*MovieRatingData.cs*의 `MovieRating` 클래스 뒤에 다음 코드를 추가하여 예측 결과를 나타내는 또 다른 클래스(`MovieRatingPrediction`)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-178">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="4b56f-179">*Program.cs*에서 `Console.WriteLine("Hello World!")`을 `Main()` 내부의 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-179">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="4b56f-180">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작점이며, `mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-180">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="4b56f-181">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-181">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="4b56f-182">`Main()` 다음에 `LoadData()`라는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-182">After `Main()`, create a method called `LoadData()`:</span></span>

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> <span data-ttu-id="4b56f-183">이 메서드는 다음 단계에서 return 문을 추가할 때까지 오류를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-183">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="4b56f-184">데이터 경로 변수를 초기화하여 \*.csv 파일에서 데이터를 로드하고 `LoadData()`의 다음 코드 줄로 다음 항목을 추가하여 `Train` 및 `Test` 데이터를 `IDataView` 개체로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-184">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="4b56f-185">ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-185">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="4b56f-186">`IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-186">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="4b56f-187">데이터를 텍스트 파일 또는 실시간(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-187">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="4b56f-188">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)은 데이터 스키마를 정의하고 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-188">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="4b56f-189">데이터 경로 변수를 가져와서 `IDataView`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-189">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="4b56f-190">이 경우, `Test` 및 `Train` 파일의 경로를 제공하고 텍스트 파일 헤더(열 이름을 올바르게 사용할 수 있도록)와 쉼표 문자 데이터 구분 기호(기본 구분 기호는 탭)를 모두 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-190">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="4b56f-191">`Main()` 메서드에서 다음 코드를 추가하여 `LoadData()` 메서드를 호출하고 `Train` 및 `Test` 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-191">Add the following code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a><span data-ttu-id="4b56f-192">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="4b56f-192">Build and train your model</span></span>

<span data-ttu-id="4b56f-193">ML.NET에는 세 가지 주요 개념이 있습니다. [데이터](../resources/glossary.md#data), [변환기](../resources/glossary.md#transformer) 및 [평가자](../resources/glossary.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="4b56f-193">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

<span data-ttu-id="4b56f-194">기계 학습 알고리즘은 특정 형식의 데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-194">Machine learning training algorithms require data in a certain format.</span></span> <span data-ttu-id="4b56f-195">`Transformers`는 표 형식 데이터를 호환 가능한 형식으로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-195">`Transformers` are used to transform tabular data to a compatible format.</span></span>

![변환기 이미지](./media/movie-recommendation/transformer.png)

<span data-ttu-id="4b56f-197">`Estimators`를 생성하여 ML.NET에서 `Transformers`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-197">You create `Transformers` in ML.NET by creating `Estimators`.</span></span> <span data-ttu-id="4b56f-198">`Estimators`는 데이터를 가져와서 `Transformers`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-198">`Estimators` take in data and return `Transformers`.</span></span>

![평가자 이미지](./media/movie-recommendation/estimator.png)

<span data-ttu-id="4b56f-200">모델 학습에 사용할 권장 학습 알고리즘은 `Estimator`의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-200">The recommendation training algorithm you will use for training your model is an example of an `Estimator`.</span></span>

<span data-ttu-id="4b56f-201">다음 단계를 수행하여 `Estimator`를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-201">Build an `Estimator` with the following steps:</span></span>

<span data-ttu-id="4b56f-202">다음 코드를 사용하여 `LoadData()` 메서드 바로 뒤에 `BuildAndTrainModel()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-202">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> <span data-ttu-id="4b56f-203">이 메서드는 다음 단계에서 return 문을 추가할 때까지 오류를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-203">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="4b56f-204">`BuildAndTrainModel()`에 다음 코드를 추가하여 데이터 변환을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-204">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>

[!code-csharp[DataTransformations](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="4b56f-205">`userId` 및 `movieId`는 실제 값이 아닌 사용자와 영화 제목을 나타내기 때문에 [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 메서드를 사용하여 각 `userId` 및 각 `movieId`를 숫자 키 형식 `Feature` 열(권장 알고리즘에서 허용하는 형식)로 변환하고 새 데이터 세트 열로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-205">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="4b56f-206">userId</span><span class="sxs-lookup"><span data-stu-id="4b56f-206">userId</span></span> | <span data-ttu-id="4b56f-207">movieId</span><span class="sxs-lookup"><span data-stu-id="4b56f-207">movieId</span></span> | <span data-ttu-id="4b56f-208">레이블</span><span class="sxs-lookup"><span data-stu-id="4b56f-208">Label</span></span> | <span data-ttu-id="4b56f-209">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="4b56f-209">userIdEncoded</span></span> | <span data-ttu-id="4b56f-210">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="4b56f-210">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="4b56f-211">1</span><span class="sxs-lookup"><span data-stu-id="4b56f-211">1</span></span> | <span data-ttu-id="4b56f-212">1</span><span class="sxs-lookup"><span data-stu-id="4b56f-212">1</span></span> | <span data-ttu-id="4b56f-213">4</span><span class="sxs-lookup"><span data-stu-id="4b56f-213">4</span></span> | <span data-ttu-id="4b56f-214">userKey1</span><span class="sxs-lookup"><span data-stu-id="4b56f-214">userKey1</span></span> | <span data-ttu-id="4b56f-215">movieKey1</span><span class="sxs-lookup"><span data-stu-id="4b56f-215">movieKey1</span></span> |
| <span data-ttu-id="4b56f-216">1</span><span class="sxs-lookup"><span data-stu-id="4b56f-216">1</span></span> | <span data-ttu-id="4b56f-217">3</span><span class="sxs-lookup"><span data-stu-id="4b56f-217">3</span></span> | <span data-ttu-id="4b56f-218">4</span><span class="sxs-lookup"><span data-stu-id="4b56f-218">4</span></span> | <span data-ttu-id="4b56f-219">userKey1</span><span class="sxs-lookup"><span data-stu-id="4b56f-219">userKey1</span></span> | <span data-ttu-id="4b56f-220">movieKey2</span><span class="sxs-lookup"><span data-stu-id="4b56f-220">movieKey2</span></span> |
| <span data-ttu-id="4b56f-221">1</span><span class="sxs-lookup"><span data-stu-id="4b56f-221">1</span></span> | <span data-ttu-id="4b56f-222">6</span><span class="sxs-lookup"><span data-stu-id="4b56f-222">6</span></span> | <span data-ttu-id="4b56f-223">4</span><span class="sxs-lookup"><span data-stu-id="4b56f-223">4</span></span> | <span data-ttu-id="4b56f-224">userKey1</span><span class="sxs-lookup"><span data-stu-id="4b56f-224">userKey1</span></span> | <span data-ttu-id="4b56f-225">movieKey3</span><span class="sxs-lookup"><span data-stu-id="4b56f-225">movieKey3</span></span> |

<span data-ttu-id="4b56f-226">기계 학습 알고리즘을 선택하고 `BuildAndTrainModel()`의 다음 코드 줄로 다음 항목을 추가하여 데이터 변환 정의에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-226">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="4b56f-227">[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29)는 권장 학습 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-227">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="4b56f-228">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems))은 사용자가 이전에 제품을 평가한 방법에 대한 데이터가 있을 때 권장되는 일반적인 접근 방법입니다. 이는 이 자습서의 데이터 세트에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-228">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="4b56f-229">다른 데이터를 사용할 수 있는 경우에 대한 기타 권장 알고리즘이 있습니다(자세한 내용은 아래의 [기타 권장 알고리즘](#other-recommendation-algorithms) 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="4b56f-229">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span>

<span data-ttu-id="4b56f-230">이 경우, `Matrix Factorization` 알고리즘은 "공동 작업 필터링"이라는 방법을 사용합니다. 이 방법은 사용자 1이 특정 문제에 대해 사용자 2와 의견이 같으면, 다른 문제에 대해 사용자 1이 사용자 2와 동일한 방식으로 느낄 가능성이 높다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-230">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="4b56f-231">예를 들어 사용자 1과 사용자 2가 영화를 비슷하게 평가한다면 사용자 2는 사용자 1이 시청하고 높게 평가한 영화를 즐길 가능성이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-231">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="4b56f-232">사용자 1</span><span class="sxs-lookup"><span data-stu-id="4b56f-232">User 1</span></span> | <span data-ttu-id="4b56f-233">시청하고 좋아하는 영화</span><span class="sxs-lookup"><span data-stu-id="4b56f-233">Watched and liked movie</span></span> | <span data-ttu-id="4b56f-234">시청하고 좋아하는 영화</span><span class="sxs-lookup"><span data-stu-id="4b56f-234">Watched and liked movie</span></span> | <span data-ttu-id="4b56f-235">시청하고 좋아하는 영화</span><span class="sxs-lookup"><span data-stu-id="4b56f-235">Watched and liked movie</span></span> |
| <span data-ttu-id="4b56f-236">사용자 2</span><span class="sxs-lookup"><span data-stu-id="4b56f-236">User 2</span></span> | <span data-ttu-id="4b56f-237">시청하고 좋아하는 영화</span><span class="sxs-lookup"><span data-stu-id="4b56f-237">Watched and liked movie</span></span> | <span data-ttu-id="4b56f-238">시청하고 좋아하는 영화</span><span class="sxs-lookup"><span data-stu-id="4b56f-238">Watched and liked movie</span></span> | <span data-ttu-id="4b56f-239">시청하지 않음 -- 추천 영화</span><span class="sxs-lookup"><span data-stu-id="4b56f-239">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="4b56f-240">`Matrix Factorization` 강사는 몇 가지 [옵션](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options)이 있으며, 아래의 [알고리즘 하이퍼 매개 변수](#algorithm-hyperparameters) 섹션에서 자세히 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-240">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="4b56f-241">모델을 `Train` 데이터에 맞추고 `BuildAndTrainModel()` 메서드에서 다음 줄의 코드로 다음 항목을 추가하여 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-241">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="4b56f-242">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) 메서드는 제공된 학습 데이터 세트를 통해 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-242">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="4b56f-243">기술적으로 데이터를 변환하고 학습을 적용하여 `Estimator` 정의를 실행하고, 학습된 모델인 `Transformer`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-243">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="4b56f-244">`Main()` 메서드에서 다음 줄의 코드로 다음 항목을 추가하여 `BuildAndTrainModel()` 메서드를 호출하고 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-244">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="4b56f-245">모델 평가</span><span class="sxs-lookup"><span data-stu-id="4b56f-245">Evaluate your model</span></span>

<span data-ttu-id="4b56f-246">모델을 학습한 후에는 테스트 데이터를 사용하여 모델의 성능을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-246">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span>

<span data-ttu-id="4b56f-247">다음 코드를 사용하여 `BuildAndTrainModel()` 메서드 바로 뒤에 `EvaluateModel()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-247">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

<span data-ttu-id="4b56f-248">`EvaluateModel()`에 다음 코드를 추가하여 `Test`데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-248">Transform the `Test` data by adding the following code to `EvaluateModel()`:</span></span>

[!code-csharp[Transform](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]

<span data-ttu-id="4b56f-249">[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드는 테스트 데이터 세트의 여러 입력 행을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-249">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="4b56f-250">`EvaluateModel()` 메서드에서 다음 코드 줄로 다음 항목을 추가하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-250">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="4b56f-251">예측 집합이 있으면 [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) 메서드는 모델을 평가하여 예측된 값을 테스트 데이터 세트의 실제 `Labels`와 비교하고, 모델 수행 방법에 대한 메트릭을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-251">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="4b56f-252">`EvaluateModel()` 메서드에 다음 코드 줄로 다음 항목을 추가하여 평가 메트릭을 콘솔에 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-252">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="4b56f-253">`EvaluateModel()` 메서드를 호출하려면 `Main()` 메서드에서 다음 코드 줄로 다음 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-253">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="4b56f-254">지금까지의 출력은 다음 텍스트와 비슷해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-254">The output so far should look similar to the following text:</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

<span data-ttu-id="4b56f-255">이 출력에는 20번의 반복이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-255">In this output, there are 20 iterations.</span></span> <span data-ttu-id="4b56f-256">각각의 반복에서 오류의 측정값은 줄어들고 0에 가깝게 수렴합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-256">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="4b56f-257">`root of mean squared error`(RMS 또는 RMSE)는 모델 예측 값과 테스트 데이터 세트 관찰 값 간의 차이를 측정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-257">The `root of mean squared error` (RMS or RMSE) is used to measure the differences between the model predicted values and the test dataset observed values.</span></span> <span data-ttu-id="4b56f-258">기술적으로 오차 제곱 평균의 제곱근입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-258">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="4b56f-259">RMS가 낮을수록 더 나은 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-259">The lower it is, the better the model is.</span></span>

<span data-ttu-id="4b56f-260">`R Squared`는 데이터가 모델에 얼마나 잘 맞는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-260">`R Squared` indicates how well data fits a model.</span></span> <span data-ttu-id="4b56f-261">범위는 0에서 1까지입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-261">Ranges from 0 to 1.</span></span> <span data-ttu-id="4b56f-262">0 값은 데이터가 무작위이거나 모델에 맞지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-262">A value of 0 means that the data is random or otherwise can't be fit to the model.</span></span> <span data-ttu-id="4b56f-263">값 1은 모델이 데이터와 정확히 일치함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-263">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="4b56f-264">`R Squared` 점수를 가능한 한 1에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-264">You want your `R Squared` score to be as close to 1 as possible.</span></span>

<span data-ttu-id="4b56f-265">성공한 모델 빌드하는 것은 반복적인 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-265">Building successful models is an iterative process.</span></span> <span data-ttu-id="4b56f-266">자습서에서는 작은 데이터 세트를 사용하여 빠른 모델 학습을 제공하므로 이 모델은 초기 품질이 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-266">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="4b56f-267">모델 품질에 만족하지 않는 경우 더 큰 학습 데이터 세트를 제공하거나 각 알고리즘에 대한 다양한 하이퍼 매개 변수와 함께 다양한 학습 알고리즘을 선택하여 모델 품질을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-267">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span> <span data-ttu-id="4b56f-268">자세한 내용은 아래 [모델 개선](#improve-your-model) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b56f-268">For more information, check out the [Improve your model](#improve-your-model) section below.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="4b56f-269">모델 사용</span><span class="sxs-lookup"><span data-stu-id="4b56f-269">Use your model</span></span>

<span data-ttu-id="4b56f-270">이제 학습된 모델을 사용하여 새 데이터를 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-270">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="4b56f-271">다음 코드를 사용하여 `EvaluateModel()` 메서드 바로 뒤에 `UseModelForSinglePrediction()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-271">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="4b56f-272">`UseModelForSinglePrediction()`에 다음 코드를 추가하여 등급을 예측하려면 `PredictionEngine`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-272">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="4b56f-273">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-273">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="4b56f-274">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-274">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="4b56f-275">단일 스레드 또는 프로토타입 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-275">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="4b56f-276">프로덕션 환경에서 성능 및 스레드 보안을 개선하려면 `PredictionEnginePool` 서비스를 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-276">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="4b56f-277">[ASP.NET Core Web API에서 `PredictionEnginePool`을 사용하는 방법](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)에 대한 이 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b56f-277">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="4b56f-278">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-278">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="4b56f-279">`testInput`이라는 `MovieRating`의 인스턴스를 만들고 `UseModelForSinglePrediction()` 메서드에서 다음 코드 줄로 다음 항목을 추가하여 예측 엔진에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-279">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="4b56f-280">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수는 단일 데이터 열의 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-280">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="4b56f-281">그런 다음, `Score` 또는 예측 등급을 사용하여 movieId 10을 통해 사용자 6에게 영화를 추천할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-281">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="4b56f-282">`Score`가 높을수록 사용자가 특정 영화를 좋아할 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-282">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="4b56f-283">이 경우, 예측된 등급이 >3.5인 영화를 추천한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-283">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="4b56f-284">결과를 인쇄하려면 `UseModelForSinglePrediction()` 메서드에서 다음 코드 줄로 다음 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-284">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="4b56f-285">`UseModelForSinglePrediction()` 메서드를 호출하려면 `Main()` 메서드에서 다음 코드 줄로 다음 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-285">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="4b56f-286">이 메서드의 출력은 다음 텍스트와 비슷해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-286">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="4b56f-287">모델 저장</span><span class="sxs-lookup"><span data-stu-id="4b56f-287">Save your model</span></span>

<span data-ttu-id="4b56f-288">최종 사용자 애플리케이션에서 모델을 사용하여 예측하려면 먼저 모델을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-288">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="4b56f-289">다음 코드를 사용하여 `UseModelForSinglePrediction()` 메서드 바로 뒤에 `SaveModel()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-289">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>

```csharp
public static void SaveModel(MLContext mlContext, DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

<span data-ttu-id="4b56f-290">`SaveModel()` 메서드의 다음 코드를 추가하여 학습된 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-290">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="4b56f-291">이 메서드는 학습된 모델을 .zip 파일("Data" 폴더에 있음)에 저장한 다음, 이를 다른 .NET 애플리케이션에서 예측을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-291">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="4b56f-292">`SaveModel()` 메서드를 호출하려면 `Main()` 메서드에서 다음 코드 줄로 다음 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-292">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="4b56f-293">저장된 모델 사용</span><span class="sxs-lookup"><span data-stu-id="4b56f-293">Use your saved model</span></span>

<span data-ttu-id="4b56f-294">학습된 모델을 저장한 후에는 다양한 환경에서 모델을 사용할 수 있습니다(앱에서 학습된 기계 학습 모델을 작동하는 방법에 대한 자세한 내용은 ["방법 가이드"](../how-to-guides/consuming-model-ml-net.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="4b56f-294">Once you have saved your trained model, you can consume the model in different environments (see the ["How-to guide"](../how-to-guides/consuming-model-ml-net.md) to learn how to operationalize a trained machine learning model in apps).</span></span>

## <a name="results"></a><span data-ttu-id="4b56f-295">결과</span><span class="sxs-lookup"><span data-stu-id="4b56f-295">Results</span></span>

<span data-ttu-id="4b56f-296">위의 단계를 수행한 후 콘솔 앱을 실행합니다(Ctrl + F5).</span><span class="sxs-lookup"><span data-stu-id="4b56f-296">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="4b56f-297">위의 단일 예측 결과는 다음과 비슷해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-297">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="4b56f-298">경고 또는 처리 메시지가 표시될 수 있지만, 이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-298">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

<span data-ttu-id="4b56f-299">지금까지</span><span class="sxs-lookup"><span data-stu-id="4b56f-299">Congratulations!</span></span> <span data-ttu-id="4b56f-300">이제 영화 추천을 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-300">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="4b56f-301">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-301">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="4b56f-302">모델 개선</span><span class="sxs-lookup"><span data-stu-id="4b56f-302">Improve your model</span></span>

<span data-ttu-id="4b56f-303">보다 정확한 예측을 할 수 있도록 모델의 성능을 개선할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-303">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="4b56f-304">데이터</span><span class="sxs-lookup"><span data-stu-id="4b56f-304">Data</span></span>

<span data-ttu-id="4b56f-305">각 사용자 및 영화 id에 대한 충분한 샘플이 있는 학습 데이터를 추가하면 권장 모델의 품질을 개선하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-305">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="4b56f-306">[교차 유효성 검사](../how-to-guides/train-cross-validation-ml-net.md)는 임의로 데이터를 하위 집합으로 분할하여(이 자습서에서처럼 테스트 데이터 세트를 추출하는 대신) 그룹 중 일부는 학습 데이터로, 일부는 테스트 데이터로 가져오는 모델을 평가하는 기법입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-306">[Cross validation](../how-to-guides/train-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="4b56f-307">이 메서드는 모델 품질 면에서 학습-테스트 분할을 수행하는 것보다 뛰어난 성능을 냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-307">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="4b56f-308">기능</span><span class="sxs-lookup"><span data-stu-id="4b56f-308">Features</span></span>

<span data-ttu-id="4b56f-309">이 자습서에서는 데이터 세트에서 제공하는 세 개의 `Features`(`user id`, `movie id` 및 `rating`)만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-309">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span>

<span data-ttu-id="4b56f-310">시작은 좋지만 실제로는 데이터 세트에 포함된 다른 특성 또는 `Features`(예: 나이, 성별, 지리적 위치 등)를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-310">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="4b56f-311">관련성이 높은 `Features`를 추가하면 권장 모델의 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-311">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span>

<span data-ttu-id="4b56f-312">`Features`가 기계 학습 작업에 가장 관련이 있는지 확실하지 않은 경우, ML.NET에서 가장 영향력 있는 `Features`를 검색하기 위해 제공되는 FCC(Feature Contribution Calculation) 및 [Feature Permutation 중요도](../how-to-guides/determine-global-feature-importance-in-model.md)를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-312">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="4b56f-313">알고리즘 하이퍼 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b56f-313">Algorithm hyperparameters</span></span>

<span data-ttu-id="4b56f-314">ML.NET은 좋은 기본 학습 알고리즘을 제공하지만 알고리즘의 [하이퍼 매개 변수](../resources/glossary.md#hyperparameter)를 변경하여 성능을 더욱 미세하게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-314">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="4b56f-315">`Matrix Factorization`의 경우 [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) 및 [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank)와 같은 하이퍼 매개 변수로 실험하여 더 나은 결과를 얻을 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-315">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="4b56f-316">예를 들어 이 자습서에서 알고리즘 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-316">For instance, in this tutorial the algorithm options are:</span></span>

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded",
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="4b56f-317">기타 권장 알고리즘</span><span class="sxs-lookup"><span data-stu-id="4b56f-317">Other Recommendation Algorithms</span></span>

<span data-ttu-id="4b56f-318">공동 작업 필터링을 사용하는 행렬 인수 분해 알고리즘은 영화 추천을 수행하는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-318">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="4b56f-319">대부분의 경우 등급 데이터를 사용할 수 없고 사용자로부터 영화 기록만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-319">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="4b56f-320">다른 경우에는 사용자의 등급 데이터 이상만 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-320">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="4b56f-321">알고리즘</span><span class="sxs-lookup"><span data-stu-id="4b56f-321">Algorithm</span></span>       | <span data-ttu-id="4b56f-322">시나리오</span><span class="sxs-lookup"><span data-stu-id="4b56f-322">Scenario</span></span>           | <span data-ttu-id="4b56f-323">예제</span><span class="sxs-lookup"><span data-stu-id="4b56f-323">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="4b56f-324">하나의 클래스 행렬 인수 분해</span><span class="sxs-lookup"><span data-stu-id="4b56f-324">One Class Matrix Factorization</span></span> | <span data-ttu-id="4b56f-325">userId 및 movieId만 있을 때 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-325">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="4b56f-326">이 스타일 권장 사항은 공동 구매 시나리오 또는 함께 자주 구매되는 제품을 기반으로 합니다. 즉, 구매 주문 내역에 따라 고객에게 제품 세트를 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-326">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="4b56f-327">>사용해 보기</span><span class="sxs-lookup"><span data-stu-id="4b56f-327">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="4b56f-328">필드 인식 인수 분해 머신</span><span class="sxs-lookup"><span data-stu-id="4b56f-328">Field Aware Factorization Machines</span></span> | <span data-ttu-id="4b56f-329">userId, productId 및 등급(예: 제품 설명 또는 제품 가격) 이외에 더 많은 기능이 있는 경우 이 옵션을 사용하여 권장 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-329">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="4b56f-330">이 메서드는 또한 공동 작업 필터링 접근 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-330">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="4b56f-331">>사용해 보기</span><span class="sxs-lookup"><span data-stu-id="4b56f-331">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="4b56f-332">새로운 사용자 시나리오</span><span class="sxs-lookup"><span data-stu-id="4b56f-332">New user scenario</span></span>

<span data-ttu-id="4b56f-333">공동 작업 필터링의 일반적인 문제 중 하나는 추론을 도출할 이전 데이터가 없는 새로운 사용자가 있을 때 발생하는 콜드 시작 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-333">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="4b56f-334">이 문제는 종종 새로운 사용자에게 프로필을 만들고 이전에 시청한 영화를 평가하도록 요청함으로써 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-334">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="4b56f-335">이 메서드는 사용자에 다소 부담을 주지만 등급 기록이 없는 새로운 사용자에 대한 일부 시작 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-335">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="4b56f-336">리소스</span><span class="sxs-lookup"><span data-stu-id="4b56f-336">Resources</span></span>

<span data-ttu-id="4b56f-337">이 자습서에 사용된 데이터는 [MovieLens 데이터 세트](http://files.grouplens.org/datasets/movielens/)에서 파생되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-337">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b56f-338">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4b56f-338">Next steps</span></span>

<span data-ttu-id="4b56f-339">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b56f-339">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="4b56f-340">기계 학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="4b56f-340">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="4b56f-341">데이터 준비 및 로드</span><span class="sxs-lookup"><span data-stu-id="4b56f-341">Prepare and load your data</span></span>
> * <span data-ttu-id="4b56f-342">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="4b56f-342">Build and train a model</span></span>
> * <span data-ttu-id="4b56f-343">모델 평가</span><span class="sxs-lookup"><span data-stu-id="4b56f-343">Evaluate a model</span></span>
> * <span data-ttu-id="4b56f-344">모델 배포 및 사용</span><span class="sxs-lookup"><span data-stu-id="4b56f-344">Deploy and consume a model</span></span>

<span data-ttu-id="4b56f-345">다음 자습서로 이동하여 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4b56f-345">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="4b56f-346">감정 분석</span><span class="sxs-lookup"><span data-stu-id="4b56f-346">Sentiment Analysis</span></span>](sentiment-analysis.md)

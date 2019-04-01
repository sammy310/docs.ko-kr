---
title: 클러스터링 학습자를 사용하여 아이리스 꽃 클러스터링 - ML.NET
description: 클러스터링 시나리오에서 ML.NET을 사용하는 방법 알아보기
author: pkulikov
ms.author: johalex
ms.date: 03/18/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: be59760091767b7229d80693cd69434581a8b140
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634416"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="fa726-103">자습서: ML.NET을 통해 클러스터링 학습자를 사용하여 아이리스 꽃 클러스터링</span><span class="sxs-lookup"><span data-stu-id="fa726-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="fa726-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="fa726-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa726-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="fa726-106">이 자습서와 관련 샘플에서는 현재 **ML.NET 버전 0.11**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-106">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="fa726-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa726-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="fa726-108">이 자습서에서는 ML.NET을 사용하여 [아이리스 꽃 데이터 집합](https://en.wikipedia.org/wiki/Iris_flower_data_set)을 위해 [클러스터링 모델](../resources/tasks.md#clustering)을 빌드하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-108">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="fa726-109">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="fa726-110">문제 이해</span><span class="sxs-lookup"><span data-stu-id="fa726-110">Understand the problem</span></span>
> - <span data-ttu-id="fa726-111">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="fa726-111">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="fa726-112">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="fa726-112">Prepare the data</span></span>
> - <span data-ttu-id="fa726-113">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="fa726-113">Load and transform the data</span></span>
> - <span data-ttu-id="fa726-114">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="fa726-114">Choose a learning algorithm</span></span>
> - <span data-ttu-id="fa726-115">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fa726-115">Train the model</span></span>
> - <span data-ttu-id="fa726-116">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fa726-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa726-117">전제 조건</span><span class="sxs-lookup"><span data-stu-id="fa726-117">Prerequisites</span></span>

- <span data-ttu-id="fa726-118">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="fa726-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="fa726-119">문제 이해</span><span class="sxs-lookup"><span data-stu-id="fa726-119">Understand the problem</span></span>

<span data-ttu-id="fa726-120">이 문제는 꽃 특징을 기반으로 아이리스 꽃 집합을 여러 그룹으로 나누는 것에 관한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-120">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="fa726-121">그 특징은 꽃받침의 길이 및 너비와 꽃잎의 길이 및 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-121">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="fa726-122">이 자습서에서는 각 꽃 유형이 알려지지 않은 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-122">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="fa726-123">특정으로부터 데이터 집합의 구조를 파악하고 데이터 인스턴스가 이 구조에 어떻게 맞는지 예측해보려 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-123">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="fa726-124">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="fa726-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="fa726-125">각 꽃이 속한 그룹을 모르기 때문에 [감독되지 않는 기계 학습](../resources/glossary.md#unsupervised-machine-learning) 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-125">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="fa726-126">같은 그룹의 요소를 다른 그룹의 요소보다 더 서로 유사한 방식으로 그룹의 데이터 집합을 나누려면 [클러스터링](../resources/tasks.md#clustering) 기계 학습 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-126">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="fa726-127">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fa726-127">Create a console application</span></span>

1. <span data-ttu-id="fa726-128">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="fa726-129">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="fa726-130">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="fa726-131">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="fa726-132">**이름** 텍스트 상자에 "IrisFlowerClustering"을 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-132">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="fa726-133">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합과 모델 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-133">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="fa726-134">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="fa726-135">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-135">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="fa726-136">**Microsoft.ML** NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-136">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="fa726-137">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="fa726-138">“nuget.org”를 패키지 소스로 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="fa726-139">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="fa726-140">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="fa726-140">Prepare the data</span></span>

1. <span data-ttu-id="fa726-141">[iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) 데이터 집합을 다운로드하고 이전 단계에서 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-141">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="fa726-142">아이리스 데이터 집합에 대한 자세한 내용은 [아이리스 꽃 데이터 집합](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia 페이지와 데이터 집합의 출처인 [아이리스 데이터 집합](https://archive.ics.uci.edu/ml/datasets/Iris) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa726-142">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="fa726-143">**솔루션 탐색기**에서 *iris.data* 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-143">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="fa726-144">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-144">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="fa726-145">*iris.data* 파일에는 다음을 나타내는 5개의 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-145">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="fa726-146">꽃받침 길이(cm)</span><span class="sxs-lookup"><span data-stu-id="fa726-146">sepal length in centimetres</span></span>
- <span data-ttu-id="fa726-147">꽃받침 너비(cm)</span><span class="sxs-lookup"><span data-stu-id="fa726-147">sepal width in centimetres</span></span>
- <span data-ttu-id="fa726-148">꽃잎 길이(cm)</span><span class="sxs-lookup"><span data-stu-id="fa726-148">petal length in centimetres</span></span>
- <span data-ttu-id="fa726-149">꽃잎 너비(cm)</span><span class="sxs-lookup"><span data-stu-id="fa726-149">petal width in centimetres</span></span>
- <span data-ttu-id="fa726-150">아이리스 꽃의 종류</span><span class="sxs-lookup"><span data-stu-id="fa726-150">type of iris flower</span></span>

<span data-ttu-id="fa726-151">클러스터링 예제에서 이 자습서는 마지막 열을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-151">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="fa726-152">데이터 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="fa726-152">Create data classes</span></span>

<span data-ttu-id="fa726-153">입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-153">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="fa726-154">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-154">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="fa726-155">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *IrisData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-155">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="fa726-156">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-156">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="fa726-157">새 파일에 다음 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-157">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="fa726-158">기존 클래스 정의를 제거하고 `IrisData` 및 `ClusterPrediction` 클래스를 정의하는 다음 코드를 *IrisData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-158">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="fa726-159">`IrisData`는 입력 데이터 클래스이며 각 데이터 집합의 각 특징에 대한 정의를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-159">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="fa726-160">[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) 특성을 사용하여 데이터 세트 파일에서 소스 열의 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-160">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="fa726-161">`ClusterPrediction` 클래스는 `IrisData` 인스턴스에 적용된 클러스터링 모델의 출력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-161">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="fa726-162">[ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) 속성을 사용하여 `PredictedClusterId` 및 `Distances` 필드를 각각 **PredictedLabel** 및 **Score** 열에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-162">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="fa726-163">클러스터링 작업의 경우 이들 열의 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-163">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="fa726-164">**PredictedLabel**열에는 예측된 클러스터의 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-164">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="fa726-165">**Score** 열에는 클러스터 중심까지 제곱 유클리드 거리가 있는 배열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-165">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="fa726-166">배열 길이는 클러스터와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-166">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="fa726-167">`float` 유형을 사용하여 입력 및 예측 데이터 클래스에서 부동 소수점 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-167">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="fa726-168">데이터 및 모델 경로 정의</span><span class="sxs-lookup"><span data-stu-id="fa726-168">Define data and model paths</span></span>

<span data-ttu-id="fa726-169">*Program.cs* 파일로 돌아가서 두 개의 필드를 추가하여 데이터 집합 파일에 대한 경로와 모델을 저장할 파일에 대한 경로를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-169">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="fa726-170">`_dataPath`에는 모델을 학습하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-170">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="fa726-171">`_modelPath`에는 학습된 모델이 저장되는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-171">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="fa726-172">`Main` 메서드 바로 위에 다음 코드를 추가하여 해당 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-172">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="fa726-173">위의 코드를 컴파일하려면 *Program.cs* 파일의 맨 위에 있는 다음 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-173">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="fa726-174">ML 컨텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="fa726-174">Create ML context</span></span>

<span data-ttu-id="fa726-175">*Program.cs* 파일 맨 위에 다음 추가 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-175">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="fa726-176">`Main` 메서드에서 `Console.WriteLine("Hello World!");` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-176">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="fa726-177"><xref:Microsoft.ML.MLContext?displayProperty=nameWithType> 클래스는 기계 학습 환경 연결을 나타내며 데이터 로드, 모델 학습, 예측 및 기타 작업에 대한 로깅 및 진입점에 대한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-177">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="fa726-178">이는 Entity Framework에서 `DbContext`를 사용하는 것과 개념이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-178">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="fa726-179">데이터 로드 설정</span><span class="sxs-lookup"><span data-stu-id="fa726-179">Setup data loading</span></span>

<span data-ttu-id="fa726-180">`Main` 메서드에 다음 코드를 추가하여 데이터를 로드하는 방법을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-180">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SetupTextLoader)]

<span data-ttu-id="fa726-181">[LoadFromTextFile 메서드](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)에 대해 제네릭`MLContext.Data.LoadFromTextFile`래퍼를 사용하여 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-181">Load the data using the generic `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="fa726-182">`IrisData` 데이터 모델 형식의 데이터 세트 스키마를 유추하고 데이터 세트 헤더를 사용하는 <xref:Microsoft.Data.DataView.IDataView>를 반환하고 콤마로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-182">It returns a <xref:Microsoft.Data.DataView.IDataView> which infers the dataset schema from the `IrisData` data model type, uses the dataset header and is separated by a comma.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="fa726-183">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="fa726-183">Create a learning pipeline</span></span>

<span data-ttu-id="fa726-184">이 자습서의 경우 클러스터링 작업의 학습 파이프라인은 다음 두 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-184">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="fa726-185">로드된 열을 클러스터링 교육 담당자가 사용하는 하나의 **기능** 열로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-185">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="fa726-186"><xref:Microsoft.ML.Trainers.KMeansPlusPlusTrainer> 교육 담당자를 사용하여 k-means++ 클러스터링 알고리즘을 사용하는 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-186">use a <xref:Microsoft.ML.Trainers.KMeansPlusPlusTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="fa726-187">`Main` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-187">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="fa726-188">코드는 데이터 세트를 3개의 클러스터로 분할해야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-188">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="fa726-189">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fa726-189">Train the model</span></span>

<span data-ttu-id="fa726-190">이전 섹션에서 추가된 단계는 교육을 위한 파이프라인을 준비했지만 아무 것도 실행되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-190">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="fa726-191">다음 줄을 `Main` 메서드에 추가하여 데이터 로드 및 모델 학습을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-191">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="fa726-192">모델 저장</span><span class="sxs-lookup"><span data-stu-id="fa726-192">Save the model</span></span>

<span data-ttu-id="fa726-193">이 시점에 기존 또는 새 .NET 애플리케이션에 통합할 수 있는 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-193">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="fa726-194">모델을 .zip 파일로 저장하려면 `Main` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-194">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="fa726-195">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fa726-195">Use the model for predictions</span></span>

<span data-ttu-id="fa726-196">예측을 수행하려면 변환기 파이프라인을 통해 입력 형식의 인스턴스를 사용하고 출력 형식의 인스턴스를 생성하는 <xref:Microsoft.ML.PredictionEngine%602> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-196">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="fa726-197">다음 줄을 `Main` 메서드에 추가하여 해당 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-197">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="fa726-198">테스트 데이터 인스턴스를 수용할 수 있도록 `TestIrisData` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-198">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="fa726-199">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-199">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="fa726-200">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TestIrisData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-200">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="fa726-201">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-201">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="fa726-202">다음 예제처럼 클래스를 static으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-202">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="fa726-203">이 자습서에서는 이 클래스 내에 하나의 아이리스 데이터 인스턴스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-203">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="fa726-204">이 모델로 실험할 다른 시나리오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-204">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="fa726-205">다음 코드를 `TestIrisData` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-205">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="fa726-206">지정된 항목이 속한 클러스터를 찾으려면 *Program.cs* 파일로 돌아가 다음 코드를 `Main` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-206">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="fa726-207">프로그램을 실행하여 지정된 데이터 인스턴스가 포함된 클러스터와 해당 인스턴스에서 클러스터 중심까지 제곱 거리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-207">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="fa726-208">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-208">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="fa726-209">지금까지</span><span class="sxs-lookup"><span data-stu-id="fa726-209">Congratulations!</span></span> <span data-ttu-id="fa726-210">이제 아이리스 클러스터링을 위한 기계 학습 모델을 성공적으로 구축하고 예측을 위해 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-210">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="fa726-211">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-211">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa726-212">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fa726-212">Next steps</span></span>

<span data-ttu-id="fa726-213">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa726-213">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="fa726-214">문제 이해</span><span class="sxs-lookup"><span data-stu-id="fa726-214">Understand the problem</span></span>
> - <span data-ttu-id="fa726-215">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="fa726-215">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="fa726-216">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="fa726-216">Prepare the data</span></span>
> - <span data-ttu-id="fa726-217">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="fa726-217">Load and transform the data</span></span>
> - <span data-ttu-id="fa726-218">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="fa726-218">Choose a learning algorithm</span></span>
> - <span data-ttu-id="fa726-219">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fa726-219">Train the model</span></span>
> - <span data-ttu-id="fa726-220">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fa726-220">Use the model for predictions</span></span>

<span data-ttu-id="fa726-221">학습을 계속하고 더 많은 샘플을 찾으려면 GitHub 리포지토리를 체크 아웃하세요.</span><span class="sxs-lookup"><span data-stu-id="fa726-221">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="fa726-222">dotnet/machinelearning GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="fa726-222">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)

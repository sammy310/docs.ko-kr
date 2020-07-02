---
title: '자습서: 회귀를 사용하여 가격 예측'
description: 이 자습서에서는 ML.NET을 사용하여 가격(특히, 뉴욕 시 택시 요금)을 예측하기 위한 회귀 모델을 빌드하는 방법에 대해 설명합니다.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 0a8ab9ca07d2d83f41b40a3f5782e8e7e201976f
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803237"
---
# <a name="tutorial-predict-prices-using-regression-with-mlnet"></a><span data-ttu-id="f04b2-103">자습서: ML.NET와 함께 회귀를 사용하여 가격 예측</span><span class="sxs-lookup"><span data-stu-id="f04b2-103">Tutorial: Predict prices using regression with ML.NET</span></span>

<span data-ttu-id="f04b2-104">이 자습서에서는 ML.NET을 사용하여 가격(특히, 뉴욕 시 택시 요금)을 예측하기 위한 [회귀 모델](../resources/glossary.md#regression)을 빌드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-104">This tutorial illustrates how to build a [regression model](../resources/glossary.md#regression) using ML.NET to predict prices, specifically, New York City taxi fares.</span></span>

<span data-ttu-id="f04b2-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="f04b2-106">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="f04b2-106">Prepare and understand the data</span></span>
> * <span data-ttu-id="f04b2-107">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="f04b2-107">Load and transform the data</span></span>
> * <span data-ttu-id="f04b2-108">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="f04b2-108">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f04b2-109">모델 학습</span><span class="sxs-lookup"><span data-stu-id="f04b2-109">Train the model</span></span>
> * <span data-ttu-id="f04b2-110">모델 평가</span><span class="sxs-lookup"><span data-stu-id="f04b2-110">Evaluate the model</span></span>
> * <span data-ttu-id="f04b2-111">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="f04b2-111">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f04b2-112">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f04b2-112">Prerequisites</span></span>

* <span data-ttu-id="f04b2-113">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상 또는 Visual Studio 2017 버전 15.6 이상.</span><span class="sxs-lookup"><span data-stu-id="f04b2-113">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f04b2-114">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="f04b2-114">Create a console application</span></span>

1. <span data-ttu-id="f04b2-115">"TaxiFarePrediction"이라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-115">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="f04b2-116">프로젝트에서 *Data* 디렉터리를 만들어 데이터 세트와 모델 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-116">Create a directory named *Data* in your project to store the data set and model files.</span></span>

1. <span data-ttu-id="f04b2-117">**Microsoft.ML** NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-117">Install the **Microsoft.ML** NuGet Package:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="f04b2-118">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-118">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f04b2-119">"nuget.org"를 패키지 소스로 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-119">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f04b2-120">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-120">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="f04b2-121">**Microsoft.ML.FastTree** NuGet 패키지에 대해 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-121">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="f04b2-122">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="f04b2-122">Prepare and understand the data</span></span>

1. <span data-ttu-id="f04b2-123">[taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 및 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 데이터 집합을 다운로드하여 이전 단계에서 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-123">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="f04b2-124">이러한 데이터 집합을 사용하여 기계 학습 모델을 학습한 다음, 모델의 정확성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-124">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="f04b2-125">이러한 데이터 집합은 원래 [NYC TLC Taxi Trip 데이터 집합](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-125">These data sets are originally from the [NYC TLC Taxi Trip data set](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).</span></span>

1. <span data-ttu-id="f04b2-126">**솔루션 탐색기**에서 각 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-126">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="f04b2-127">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="f04b2-128">**taxi-fare-train.csv** 데이터 집합을 열고 첫 번째 행에서 열 머리글을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-128">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="f04b2-129">각 열을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="f04b2-129">Take a look at each of the columns.</span></span> <span data-ttu-id="f04b2-130">데이터를 이해하고 **기능** 및 **레이블**로 사용할 열을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-130">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="f04b2-131">`label`은 예측할 열입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-131">The `label` is the column you want to predict.</span></span> <span data-ttu-id="f04b2-132">식별된 `Features`는 `Label` 예측을 위해 모델에 제공하는 입력입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-132">The identified `Features`are the inputs you give the model to predict the `Label`.</span></span>

<span data-ttu-id="f04b2-133">제공된 데이터 집합에는 다음과 같은 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-133">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="f04b2-134">**vendor_id:** 택시 공급업체의 ID가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="f04b2-135">**rate_code:** 택시 이동의 요금 유형이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="f04b2-136">**passenger_count:** 이동하는 승객 수가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="f04b2-137">**trip_time_in_secs:** 이동에 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f04b2-138">이동을 완료하기 전에 이동 요금을 예측하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="f04b2-139">해당 시간에는 이동이 얼마나 길지 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-139">At that moment, you don't know how long the trip would take.</span></span> <span data-ttu-id="f04b2-140">따라서 이동 시간은 기능이 아니며 모델에서 이 열을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="f04b2-141">**trip_distance:** 이동 거리가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-141">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="f04b2-142">**payment_type:** 결제 방법(현금 또는 신용 카드)이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="f04b2-143">**fare_amount:** 지급한 총 택시 요금이 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="f04b2-144">데이터 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="f04b2-144">Create data classes</span></span>

<span data-ttu-id="f04b2-145">입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-145">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="f04b2-146">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-146">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="f04b2-147">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TaxiTrip.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="f04b2-148">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-148">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="f04b2-149">새 파일에 다음 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-149">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="f04b2-150">기존 클래스 정의를 제거하고 두 개의 클래스 `TaxiTrip` 및 `TaxiTripFarePrediction`가 있는 다음 코드를 *TaxiTrip.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-150">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="f04b2-151">`TaxiTrip`은 입력 데이터 클래스이며 각 데이터 집합 열의 정의를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-151">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="f04b2-152"><xref:Microsoft.ML.Data.LoadColumnAttribute> 특성을 사용하여 데이터 세트에서 소스 열의 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-152">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="f04b2-153">`TaxiTripFarePrediction` 클래스는 예측된 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-153">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="f04b2-154">여기에는 `FareAmount`라는 단일 부동 필드가 있으며 `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> 특성이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-154">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="f04b2-155">회귀 작업의 경우 **점수** 열에 예측된 레이블 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-155">In case of the regression task, the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="f04b2-156">`float` 유형을 사용하여 입력 및 예측 데이터 클래스에서 부동 소수점 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-156">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

### <a name="define-data-and-model-paths"></a><span data-ttu-id="f04b2-157">데이터 및 모델 경로 정의</span><span class="sxs-lookup"><span data-stu-id="f04b2-157">Define data and model paths</span></span>

<span data-ttu-id="f04b2-158">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-158">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="f04b2-159">데이터 세트가 있는 파일 및 모델을 저장할 파일의 경로를 포함할 세 개의 필드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-159">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="f04b2-160">`_trainDataPath`에는 모델을 학습하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-160">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="f04b2-161">`_testDataPath`에는 모델을 평가하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-161">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="f04b2-162">`_modelPath`에는 학습된 모델이 저장되는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-162">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="f04b2-163">`Main` 메서드 바로 위에 다음 코드를 추가하여 해당 경로와 `_textLoader` 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-163">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="f04b2-164">모든 ML.NET 작업은 [MLContext 클래스](xref:Microsoft.ML.MLContext)에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-164">All ML.NET operations start in the [MLContext class](xref:Microsoft.ML.MLContext).</span></span> <span data-ttu-id="f04b2-165">`mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-165">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="f04b2-166">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-166">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="f04b2-167">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="f04b2-167">Initialize variables in Main</span></span>

<span data-ttu-id="f04b2-168">`Main` 메서드의 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 대체하여 `mlContext` 변수를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-168">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="f04b2-169">`Train` 메서드를 호출하려면 `Main` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-169">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#5 "Train your model")]

<span data-ttu-id="f04b2-170">`Train()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-170">The `Train()` method executes the following tasks:</span></span>

* <span data-ttu-id="f04b2-171">데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-171">Loads the data.</span></span>
* <span data-ttu-id="f04b2-172">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-172">Extracts and transforms the data.</span></span>
* <span data-ttu-id="f04b2-173">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-173">Trains the model.</span></span>
* <span data-ttu-id="f04b2-174">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-174">Returns the model.</span></span>

<span data-ttu-id="f04b2-175">`Train` 메서드는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-175">The `Train` method trains the model.</span></span> <span data-ttu-id="f04b2-176">다음 코드를 사용하여 `Main` 바로 아래 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-176">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

## <a name="load-and-transform-data"></a><span data-ttu-id="f04b2-177">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="f04b2-177">Load and transform data</span></span>

<span data-ttu-id="f04b2-178">ML.NET은 숫자 또는 텍스트 테이블 형식 데이터를 설명하는 효율적인 방법으로 [IDataView 클래스](xref:Microsoft.ML.IDataView)를 유연하게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-178">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="f04b2-179">`IDataView`는 텍스트 파일을 또는 실시간으로 로드할 수 있습니다(예: SQL 데이터베이스 또는 로그 파일).</span><span class="sxs-lookup"><span data-stu-id="f04b2-179">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span> <span data-ttu-id="f04b2-180">다음 코드를 `Train()` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-180">Add the following code as the first line of the `Train()` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#6 "loading training dataset")]

<span data-ttu-id="f04b2-181">택시 요금 예측에서 `FareAmount` 열은 예측할(모델의 출력) `Label`입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-181">As you want to predict the taxi trip fare, the `FareAmount` column is the `Label` that you will predict (the output of the model).</span></span> <span data-ttu-id="f04b2-182">`CopyColumnsEstimator` 변환 클래스를 사용하여 `FareAmount`를 복사하고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-182">Use the `CopyColumnsEstimator` transformation class to copy `FareAmount`, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="f04b2-183">모델을 학습시키는 알고리즘에는 **숫자** 기능이 필요하므로 범주 데이터(`VendorId`, `RateCode` 및 `PaymentType`) 값을 숫자(`VendorIdEncoded`, `RateCodeEncoded` 및 `PaymentTypeEncoded`)로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-183">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="f04b2-184">이 작업을 수행하려면 각 열의 값마다 다른 숫자 키 값을 할당하는 [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer) 변환 클래스를 사용하고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-184">To do that, use the [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer) transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="f04b2-185">데이터 준비의 마지막 단계에서는 `mlContext.Transforms.Concatenate` 변환 클래스를 사용하여 모든 기능 열을 **Features** 열에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-185">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="f04b2-186">기본적으로, 학습 알고리즘은 **Features** 열의 기능만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-186">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="f04b2-187">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-187">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="f04b2-188">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="f04b2-188">Choose a learning algorithm</span></span>

<span data-ttu-id="f04b2-189">이 문제는 뉴욕 시의 택시 요금 예측에 관한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-189">This problem is about predicting a taxi trip fare in New York City.</span></span> <span data-ttu-id="f04b2-190">처음에는 요금이 단순히 주행 거리에 따라 결정되는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-190">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="f04b2-191">그러나 뉴욕 택시 업체는 추가 승객 또는 현금 대신 신용 카드 결제 등의 다른 요소를 고려하여 다양한 금액을 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-191">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span> <span data-ttu-id="f04b2-192">데이터 세트의 기타 요인에 따라 실제 값인 가격 값을 예측하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-192">You want to predict the price value, which is a real value, based on the other factors in the dataset.</span></span> <span data-ttu-id="f04b2-193">이렇게 하려면 [회귀](../resources/glossary.md#regression) 기계 학습 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-193">To do that, you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

<span data-ttu-id="f04b2-194">`Train()`에서 다음 코드 줄에 다음을 추가하여 [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) 기계 학습 작업을 데이터 변환 정의에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-194">Append the [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) machine learning task to the data transformation definitions by adding the following as the next line of code in `Train()`:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="f04b2-195">모델 학습</span><span class="sxs-lookup"><span data-stu-id="f04b2-195">Train the model</span></span>

<span data-ttu-id="f04b2-196">모델을 `dataview` 학습에 맞추고 `Train()` 메서드에서 다음 줄의 코드를 추가하여 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-196">Fit the model to the training `dataview` and return the trained model by adding the following line of code in the `Train()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#11 "Train the model")]

<span data-ttu-id="f04b2-197">[Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) 메서드는 데이터 세트를 변환하고 학습을 적용하여 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-197">The [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="f04b2-198">`Train()` 메서드에서 다음 코드 줄을 사용하여 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-198">Return the trained model with the following line of code in the `Train()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#12 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="f04b2-199">모델 평가</span><span class="sxs-lookup"><span data-stu-id="f04b2-199">Evaluate the model</span></span>

<span data-ttu-id="f04b2-200">다음으로, 품질 보증 및 유효성 검사를 위해 테스트 데이터로 모델 성능을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-200">Next, evaluate your model performance with your test data for quality assurance and validation.</span></span> <span data-ttu-id="f04b2-201">다음 코드로 `Train()` 바로 뒤에 `Evaluate()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-201">Create the `Evaluate()` method, just after `Train()`, with the following code:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="f04b2-202">`Evaluate` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-202">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="f04b2-203">테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-203">Loads the test dataset.</span></span>
* <span data-ttu-id="f04b2-204">회귀 평가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-204">Creates the regression evaluator.</span></span>
* <span data-ttu-id="f04b2-205">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-205">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="f04b2-206">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-206">Displays the metrics.</span></span>

<span data-ttu-id="f04b2-207">다음 코드를 사용하여 `Train` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-207">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="f04b2-208">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) 메서드를 사용하여 테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-208">Load the test dataset using the [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method.</span></span> <span data-ttu-id="f04b2-209">이 데이터 세트를 품질 검사로 사용하여 `Evaluate` 메서드에 다음 코드를 추가하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-209">Evaluate the model using this dataset as a quality check by adding the following code in the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="f04b2-210">이제 `Evaluate()`에 다음 코드를 추가하여 `Test` 데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-210">Next, transform the `Test` data by adding the following code to `Evaluate()`:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="f04b2-211">[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드는 테스트 데이터 세트 입력 행에 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-211">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for the test dataset input rows.</span></span>

<span data-ttu-id="f04b2-212">`RegressionContext.Evaluate` 메서드는 지정된 데이터 세트를 사용하여 `PredictionModel`에 대한 품질 메트릭을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-212">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="f04b2-213">회귀 평가자가 계산한 전체 메트릭이 포함된 <xref:Microsoft.ML.Data.RegressionMetrics> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-213">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span>

<span data-ttu-id="f04b2-214">모델의 품질을 확인하기 위해 이러한 메트릭을 표시하려면 먼저 메트릭을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-214">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="f04b2-215">`Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-215">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="f04b2-216">예측 집합이 있으면 [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) 메서드는 모델을 평가하여 예측된 값을 테스트 데이터 세트의 실제 `Labels`와 비교하고, 모델 수행 방법에 대한 메트릭을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-216">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="f04b2-217">다음 코드를 추가하여 모델을 평가하고 평가 메트릭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-217">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="f04b2-218">[RSquared](../resources/glossary.md#coefficient-of-determination)는 회귀 모델의 다른 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-218">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="f04b2-219">RSquared에서는 0과 1 사이의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-219">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="f04b2-220">해당 값이 1에 가까울수록 더 나은 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-220">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="f04b2-221">RSquared 값을 표시하려면 `Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-221">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="f04b2-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse)는 회귀 모델의 평가 메트릭 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="f04b2-223">RMS가 낮을수록 더 나은 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-223">The lower it is, the better the model is.</span></span> <span data-ttu-id="f04b2-224">RMS 값을 표시하려면 `Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-224">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="f04b2-225">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="f04b2-225">Use the model for predictions</span></span>

<span data-ttu-id="f04b2-226">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `TestSinglePrediction` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-226">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="f04b2-227">`TestSinglePrediction` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-227">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="f04b2-228">테스트 데이터의 단일 댓글을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-228">Creates a single comment of test data.</span></span>
* <span data-ttu-id="f04b2-229">테스트 데이터를 기준으로 요금 금액을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-229">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="f04b2-230">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-230">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="f04b2-231">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-231">Displays the predicted results.</span></span>

<span data-ttu-id="f04b2-232">다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-232">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="f04b2-233">`TestSinglePrediction()`에 다음 코드를 추가하여 요금을 예측하기 위해 `PredictionEngine`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-233">Use the `PredictionEngine` to predict the fare by adding the following code to `TestSinglePrediction()`:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#22 "Create the PredictionFunction")]

<span data-ttu-id="f04b2-234">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-234">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="f04b2-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="f04b2-236">단일 스레드 또는 프로토타입 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-236">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="f04b2-237">프로덕션 환경에서 성능 및 스레드 보안을 개선하려면 `PredictionEnginePool` 서비스를 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-237">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="f04b2-238">[ASP.NET Core Web API에서 `PredictionEnginePool`을 사용하는 방법](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)에 대한 이 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f04b2-238">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="f04b2-239">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-239">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="f04b2-240">이 자습서에서는 이 클래스 내에서 하나의 테스트 이동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-240">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="f04b2-241">나중에 이 모델로 실험할 다른 시나리오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-241">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="f04b2-242">`TaxiTrip` 인스턴스를 만들어 주행을 추가하여 `TestSinglePrediction()` 메서드에서 학습된 모델의 비용 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-242">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction()` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#23 "Create test data for single prediction")]

<span data-ttu-id="f04b2-243">이제 택시 이동 데이터의 단일 인스턴스를 기준으로 요금을 예측하고 `TestSinglePrediction()` 메서드에 다음 코드 줄로 다음을 추가하여 `PredictionEngine`에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-243">Next, predict the fare based on a single instance of the taxi trip data and pass it to the `PredictionEngine` by adding the following as the next lines of code in the `TestSinglePrediction()` method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="f04b2-244">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수는 단일 데이터 인스턴스에 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-244">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single instance of data.</span></span>

<span data-ttu-id="f04b2-245">지정한 주행의 예상 운임을 표시하려면 `TestSinglePrediction` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-245">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="f04b2-246">프로그램을 실행하여 테스트 사례에 대해 예측된 택시 요금을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-246">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="f04b2-247">지금까지</span><span class="sxs-lookup"><span data-stu-id="f04b2-247">Congratulations!</span></span> <span data-ttu-id="f04b2-248">택시 요금 예측을 위한 기계 학습 모델을 성공적으로 빌드하고, 정확도를 평가하고, 예측하는 데 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-248">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="f04b2-249">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-249">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f04b2-250">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f04b2-250">Next steps</span></span>

<span data-ttu-id="f04b2-251">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="f04b2-251">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="f04b2-252">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="f04b2-252">Prepare and understand the data</span></span>
> * <span data-ttu-id="f04b2-253">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="f04b2-253">Create a learning pipeline</span></span>
> * <span data-ttu-id="f04b2-254">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="f04b2-254">Load and transform the data</span></span>
> * <span data-ttu-id="f04b2-255">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="f04b2-255">Choose a learning algorithm</span></span>
> * <span data-ttu-id="f04b2-256">모델 학습</span><span class="sxs-lookup"><span data-stu-id="f04b2-256">Train the model</span></span>
> * <span data-ttu-id="f04b2-257">모델 평가</span><span class="sxs-lookup"><span data-stu-id="f04b2-257">Evaluate the model</span></span>
> * <span data-ttu-id="f04b2-258">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="f04b2-258">Use the model for predictions</span></span>

<span data-ttu-id="f04b2-259">다음 자습서로 이동하여 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f04b2-259">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f04b2-260">아이리스 클러스터링</span><span class="sxs-lookup"><span data-stu-id="f04b2-260">Iris clustering</span></span>](iris-clustering.md)

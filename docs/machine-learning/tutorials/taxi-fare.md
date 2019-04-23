---
title: ML.NET와 함께 회귀 학습자를 사용하여 가격 예측
description: ML.NET와 함께 회귀 학습자를 사용하여 가격을 예측합니다.
author: aditidugar
ms.author: johalex
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 49770672ebcff98d8779a888372b5c9f40a55b1d
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611811"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a><span data-ttu-id="1519e-103">자습서: ML.NET와 함께 회귀 학습자를 사용하여 가격 예측</span><span class="sxs-lookup"><span data-stu-id="1519e-103">Tutorial: Predict prices using a regression learner with ML.NET</span></span>

<span data-ttu-id="1519e-104">이 자습서에서는 ML.NET을 사용하여 가격(특히, 뉴욕시 택시 요금)을 예측하기 위한 [회귀 모델](../resources/glossary.md#regression)을 빌드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-104">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting prices, specifically, New York City taxi fares.</span></span>

> [!NOTE]
> <span data-ttu-id="1519e-105">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="1519e-106">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1519e-106">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="1519e-107">이 자습서와 관련 샘플에서는 현재 **ML.NET 버전 0.11**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-107">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="1519e-108">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1519e-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="1519e-109">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="1519e-110">문제 이해</span><span class="sxs-lookup"><span data-stu-id="1519e-110">Understand the problem</span></span>
> * <span data-ttu-id="1519e-111">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="1519e-111">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="1519e-112">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="1519e-112">Prepare and understand the data</span></span>
> * <span data-ttu-id="1519e-113">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="1519e-113">Create a learning pipeline</span></span>
> * <span data-ttu-id="1519e-114">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="1519e-114">Load and transform the data</span></span>
> * <span data-ttu-id="1519e-115">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="1519e-115">Choose a learning algorithm</span></span>
> * <span data-ttu-id="1519e-116">모델 학습</span><span class="sxs-lookup"><span data-stu-id="1519e-116">Train the model</span></span>
> * <span data-ttu-id="1519e-117">모델 평가</span><span class="sxs-lookup"><span data-stu-id="1519e-117">Evaluate the model</span></span>
> * <span data-ttu-id="1519e-118">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="1519e-118">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1519e-119">전제 조건</span><span class="sxs-lookup"><span data-stu-id="1519e-119">Prerequisites</span></span>

* <span data-ttu-id="1519e-120">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="1519e-120">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="1519e-121">문제 이해</span><span class="sxs-lookup"><span data-stu-id="1519e-121">Understand the problem</span></span>

<span data-ttu-id="1519e-122">이 문제는 뉴욕시의 택시 요금 예측에 관한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-122">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="1519e-123">처음에는 요금이 단순히 주행 거리에 따라 결정되는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-123">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="1519e-124">그러나 뉴욕 택시 업체는 추가 승객 또는 현금 대신 신용 카드 결제 등의 다른 요소를 고려하여 다양한 금액을 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-124">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="1519e-125">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="1519e-125">Select the appropriate machine learning task</span></span>

<span data-ttu-id="1519e-126">데이터 집합의 기타 요인에 따라 실제 값인 가격 값을 예측하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-126">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="1519e-127">이렇게 하려면 [회귀](../resources/glossary.md#regression) 기계 학습 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-127">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="1519e-128">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="1519e-128">Create a console application</span></span>

1. <span data-ttu-id="1519e-129">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="1519e-130">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="1519e-131">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="1519e-132">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="1519e-133">**이름** 텍스트 상자에 “TaxiFarePrediction”을 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="1519e-134">프로젝트에서 *Data* 디렉터리를 만들어 데이터 집합과 모델 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-134">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="1519e-135">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-135">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="1519e-136">“Data”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-136">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="1519e-137">**Microsoft.ML** NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-137">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="1519e-138">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-138">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="1519e-139">“nuget.org”를 패키지 소스로 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-139">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="1519e-140">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="1519e-141">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="1519e-141">Prepare and understand the data</span></span>

1. <span data-ttu-id="1519e-142">[taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 및 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 데이터 집합을 다운로드하여 이전 단계에서 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="1519e-143">이러한 데이터 집합을 사용하여 기계 학습 모델을 학습한 다음, 모델의 정확성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-143">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="1519e-144">이러한 데이터 집합은 원래 [NYC TLC Taxi Trip 데이터 집합](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="1519e-145">**솔루션 탐색기**에서 각 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-145">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="1519e-146">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="1519e-147">**taxi-fare-train.csv** 데이터 집합을 열고 첫 번째 행에서 열 머리글을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-147">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="1519e-148">각 열을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="1519e-148">Take a look at each of the columns.</span></span> <span data-ttu-id="1519e-149">데이터를 이해하고 **기능** 및 **레이블**로 사용할 열을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-149">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="1519e-150">**레이블**은 예측하려는 열의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-150">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="1519e-151">식별된 **기능**은 레이블을 예측하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-151">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="1519e-152">제공된 데이터 집합에는 다음과 같은 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-152">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="1519e-153">**vendor_id:** 택시 공급업체의 ID가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-153">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="1519e-154">**rate_code:** 택시 이동의 요금 유형이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-154">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="1519e-155">**passenger_count:** 이동하는 승객 수가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-155">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="1519e-156">**trip_time_in_secs:** 이동에 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-156">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="1519e-157">이동을 완료하기 전에 이동 요금을 예측하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-157">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="1519e-158">해당 시간에는 이동이 얼마나 길지 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-158">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="1519e-159">따라서 이동 시간은 기능이 아니며 모델에서 이 열을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-159">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="1519e-160">**trip_distance:** 이동 거리가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-160">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="1519e-161">**payment_type:** 결제 방법(현금 또는 신용 카드)이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-161">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="1519e-162">**fare_amount:** 지급한 총 택시 요금이 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-162">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="1519e-163">데이터 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="1519e-163">Create data classes</span></span>

<span data-ttu-id="1519e-164">입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-164">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="1519e-165">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-165">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="1519e-166">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *TaxiTrip.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-166">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="1519e-167">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-167">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="1519e-168">새 파일에 다음 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-168">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="1519e-169">기존 클래스 정의를 제거하고 두 개의 클래스 `TaxiTrip` 및 `TaxiTripFarePrediction`가 있는 다음 코드를 *TaxiTrip.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-169">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="1519e-170">`TaxiTrip`은 입력 데이터 클래스이며 각 데이터 집합 열의 정의를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-170">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="1519e-171"><xref:Microsoft.ML.Data.LoadColumnAttribute> 특성을 사용하여 데이터 세트에서 소스 열의 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-171">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="1519e-172">`TaxiTripFarePrediction` 클래스는 예측된 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-172">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="1519e-173">여기에는 `FareAmount`라는 단일 부동 필드가 있으며 `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> 특성이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-173">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="1519e-174">회귀 작업의 경우 **점수** 열에 예측된 레이블 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-174">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="1519e-175">`float` 유형을 사용하여 입력 및 예측 데이터 클래스에서 부동 소수점 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-175">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="1519e-176">데이터 및 모델 경로 정의</span><span class="sxs-lookup"><span data-stu-id="1519e-176">Define data and model paths</span></span>

<span data-ttu-id="1519e-177">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-177">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="1519e-178">데이터 세트가 있는 파일 및 모델을 저장할 파일의 경로를 포함할 세 개의 필드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-178">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="1519e-179">`_trainDataPath`에는 모델을 학습하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-179">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="1519e-180">`_testDataPath`에는 모델을 평가하는 데 사용되는 데이터 집합이 있는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-180">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="1519e-181">`_modelPath`에는 학습된 모델이 저장되는 파일에 대한 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-181">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="1519e-182">`Main` 메서드 바로 위에 다음 코드를 추가하여 해당 경로와 `_textLoader` 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-182">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="1519e-183">ML.NET을 사용하여 모델을 작성하는 경우 먼저 ML 컨텍스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-183">When building a model with ML.NET you start by creating an ML Context.</span></span> <span data-ttu-id="1519e-184">이는 Entity Framework에서 `DbContext`를 사용하는 것과 개념이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-184">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="1519e-185">환경은 예외 추적 및 로깅에 사용할 수 있는 기계 학습 작업의 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-185">The environment provides a context for your machine learning job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="1519e-186">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="1519e-186">Initialize variables in Main</span></span>

<span data-ttu-id="1519e-187">`mlContext`라는 변수를 만들고 `MLContext`의 새 인스턴스로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-187">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="1519e-188">`Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-188">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="1519e-189">`Train` 메서드를 호출하려면 `Main` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-189">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="1519e-190">`Train` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-190">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="1519e-191">데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-191">Loads the data.</span></span>
* <span data-ttu-id="1519e-192">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-192">Extracts and transforms the data.</span></span>
* <span data-ttu-id="1519e-193">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-193">Trains the model.</span></span>
* <span data-ttu-id="1519e-194">모델을 .zip 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-194">Saves the model as .zip file.</span></span>
* <span data-ttu-id="1519e-195">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-195">Returns the model.</span></span>

<span data-ttu-id="1519e-196">`Train` 메서드는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-196">The `Train` method trains the model.</span></span> <span data-ttu-id="1519e-197">다음 코드를 사용하여 `Main` 바로 아래 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-197">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="1519e-198">`Train` 메서드에 두 개의 매개 변수를 전달합니다. 하나는 컨텍스트(`mlContext`)를 나타내는 `MLContext`이고, 다른 하나는 데이터 세트 경로(`dataPath`)를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-198">We are passing two parameters into the `Train` method; an `MLContext` for the context (`mlContext`), and a string for the dataset path (`dataPath`).</span></span> <span data-ttu-id="1519e-199">데이터 세트를 로드하기 위해 이 메서드를 다시 사용하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-199">We're going to reuse this method for loading datasets.</span></span>

## <a name="load-and-transform-data"></a><span data-ttu-id="1519e-200">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="1519e-200">Load and transform data</span></span>

<span data-ttu-id="1519e-201">[LoadFromTextFile 메서드](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)에 대해 `MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-201">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="1519e-202"><xref:Microsoft.Data.DataView.IDataView>가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-202">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span>

<span data-ttu-id="1519e-203">`Transforms`의 입력 및 출력으로 사용되는 `DataView`는 `LINQ`의 `IEnumerable`과 비슷한 기본적인 데이터 파이프라인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-203">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="1519e-204">ML.NET에서 데이터는 SQL 뷰와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-204">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="1519e-205">지연 계산되고, 스키마화되며, 형식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-205">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="1519e-206">개체가 파이프라인의 첫 번째 부분이며 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-206">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="1519e-207">이 자습서에서는 택시 주행 가격 정보가 포함된 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-207">For this tutorial, it loads a dataset with taxi trip pricing information.</span></span> <span data-ttu-id="1519e-208">이 데이터 세트는 모델을 만들고 학습시키는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-208">This is used to create the model, and train it.</span></span>

<span data-ttu-id="1519e-209">다음 코드를 `Train` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-209">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="1519e-210">다음 단계에서는 `TaxiTrip` 클래스에 정의된 이름으로 해당 열을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-210">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="1519e-211">모델을 학습하고 평가할 때 기본적으로 **Label** 열의 값이 예측할 올바른 값으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-211">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="1519e-212">택시 요금을 예측하려면 `FareAmount` 열을 **Label** 열로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-212">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="1519e-213">이 작업을 수행하려면 `CopyColumnsEstimator` 변환 클래스를 사용하고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-213">To do that, use the `CopyColumnsEstimator` transformation class, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="1519e-214">모델을 학습시키는 알고리즘에는 **숫자** 기능이 필요하므로 범주 데이터(`VendorId`, `RateCode` 및 `PaymentType`) 값을 숫자(`VendorIdEncoded`, `RateCodeEncoded` 및 `PaymentTypeEncoded`)로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-214">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="1519e-215">이 작업을 수행하려면 각 열의 값마다 다른 숫자 키 값을 할당하는 Microsoft.ML.Transforms.OneHotEncodingTransformer> 변환 클래스를 사용하고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-215">To do that, use the Microsoft.ML.Transforms.OneHotEncodingTransformer> transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="1519e-216">데이터 준비의 마지막 단계에서는 `mlContext.Transforms.Concatenate` 변환 클래스를 사용하여 모든 기능 열을 **Features** 열에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-216">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="1519e-217">기본적으로, 학습 알고리즘은 **Features** 열의 기능만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-217">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="1519e-218">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-218">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="1519e-219">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="1519e-219">Choose a learning algorithm</span></span>

<span data-ttu-id="1519e-220">파이프라인에 데이터를 추가하고 데이터를 올바른 입력 형식으로 변환한 후 학습 알고리즘(**학습자**)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-220">After adding the data to the pipeline and transforming it into the correct input format, we select a learning algorithm (**learner**).</span></span> <span data-ttu-id="1519e-221">학습자는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-221">The learner trains the model.</span></span> <span data-ttu-id="1519e-222">이 문제에 대해 **회귀** 작업을 선택했으므로 ML.NET에서 제공하는 회귀 학습자 중 하나인 `FastTreeRegressionTrainer` 학습자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-222">We chose a **regression** task for this problem, so we use a `FastTreeRegressionTrainer` learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="1519e-223">`FastTreeRegressionTrainer` 학습 알고리즘은 그래디언트 부스팅을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-223">The `FastTreeRegressionTrainer` training algorithm utilizes gradient boosting.</span></span> <span data-ttu-id="1519e-224">그라데이션 승격은 회귀 문제에 대한 기계 학습 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-224">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="1519e-225">이 파이프라인은 각 회귀 트리를 단계적으로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-225">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="1519e-226">미리 정의된 손실 함수를 사용하여 각 단계에서 오류를 측정한 다음, 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-226">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="1519e-227">결과는 실제로 더 약한 예측 모델의 앙상블인 예측 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-227">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="1519e-228">그라데이션 승격에 대한 자세한 내용은 [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)(승격된 의사 결정 트리 회귀)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1519e-228">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="1519e-229">`Train` 메서드에 다음 코드를 추가하여 이전 단계에서 추가한 데이터 처리 코드에 `FastTreeRegressionTrainer`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-229">Add the following code into the `Train` method to add the `FastTreeRegressionTrainer` to the data processing code added in the previous step:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="1519e-230">모델 학습</span><span class="sxs-lookup"><span data-stu-id="1519e-230">Train the model</span></span>

<span data-ttu-id="1519e-231">마지막 단계에서는 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-231">The final step is to train the model.</span></span> <span data-ttu-id="1519e-232">로드되고 변환된 데이터 세트를 기준으로 <xref:Microsoft.ML.Data.TransformerChain> 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-232">We train the model, <xref:Microsoft.ML.Data.TransformerChain>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="1519e-233">추정기가 정의되면, 이미 로드된 학습 데이터를 제공하는 동시에 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A>을 사용하여 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-233">Once the estimator has been defined, we train the model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="1519e-234">그러면 예측에 사용할 모델이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-234">This returns a model to use for predictions.</span></span> <span data-ttu-id="1519e-235">`pipeline.Fit()`은 파이프라인을 학습시키고, 전달된 `DataView`에 따라 `Transformer`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-235">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="1519e-236">이 문제가 발생할 때까지 실험이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-236">The experiment is not executed until this happens.</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

### <a name="save-the-model"></a><span data-ttu-id="1519e-237">모델 저장</span><span class="sxs-lookup"><span data-stu-id="1519e-237">Save the model</span></span>

<span data-ttu-id="1519e-238">이 시점에는 기존 또는 새 .NET 애플리케이션에 통합할 수 있는 <xref:Microsoft.ML.Data.TransformerChain> 형식의 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-238">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="1519e-239">모델을 .zip 파일로 저장하려면 `Train` 메서드 끝에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-239">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="1519e-240">모델을 .zip 파일로 저장</span><span class="sxs-lookup"><span data-stu-id="1519e-240">Save the model as a .zip file</span></span>

<span data-ttu-id="1519e-241">다음 코드를 사용하여 `Train` 메서드 바로 뒤에 `SaveModelAsFile` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-241">Create the `SaveModelAsFile` method, just after the `Train` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="1519e-242">`SaveModelAsFile` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-242">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="1519e-243">모델을 .zip 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-243">Saves the model as a .zip file.</span></span>

<span data-ttu-id="1519e-244">다른 애플리케이션에서 다시 사용하고 이용할 수 있도록 모델을 저장하는 메서드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-244">We need to create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="1519e-245">`ITransformer`에는 `_modelPath` 전역 필드를 사용하는 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 메서드와 <xref:System.IO.Stream>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-245">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="1519e-246">이 파일을 zip 파일로 저장하려고 하기 때문에 `SaveTo` 메서드를 호출하기 직전에 `FileStream`을 만들겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-246">Since we want to save this as a zip file, we'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="1519e-247">`SaveModelAsFile` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-247">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

<span data-ttu-id="1519e-248">다음 코드를 사용해서 `_modelPath`가 포함된 콘솔 메시지를 작성하여 파일이 작성된 위치를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-248">We could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="1519e-249">모델 평가</span><span class="sxs-lookup"><span data-stu-id="1519e-249">Evaluate the model</span></span>

<span data-ttu-id="1519e-250">평가는 모델이 레이블 값을 얼마나 잘 예측하는지 확인하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-250">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="1519e-251">모델을 학습될 때 사용하지 않은 데이터를 기반으로 모델이 적절한 예측을 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-251">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="1519e-252">이를 수행하는 한 가지 방법은 이 자습서에서 한 것처럼 데이터를 학습 및 테스트 데이터 집합으로 분할하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-252">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="1519e-253">학습 데이터를 기반으로 모델을 학습시켰으므로 테스트 데이터에서 모델이 얼마나 잘 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-253">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="1519e-254">`Evaluate` 메서드는 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-254">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="1519e-255">해당 메서드를 만들려면 `Train` 메서드 아래에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-255">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="1519e-256">`Evaluate` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-256">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="1519e-257">테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-257">Loads the test dataset.</span></span>
* <span data-ttu-id="1519e-258">회귀 평가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-258">Creates the regression evaluator.</span></span>
* <span data-ttu-id="1519e-259">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-259">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="1519e-260">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-260">Displays the metrics.</span></span>

<span data-ttu-id="1519e-261">다음 코드를 사용하여 `Train` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-261">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="1519e-262">`MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-262">Load the test dataset using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="1519e-263">이 데이터 세트를 품질 검사로 사용하여 모델을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-263">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="1519e-264">`Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-264">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="1519e-265">다음으로, 기계 학습 `model` 매개 변수(변환기)를 사용하여 기능을 입력하고 예측을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-265">Next, use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="1519e-266">`Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-266">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="1519e-267">`RegressionContext.Evaluate` 메서드는 지정된 데이터 세트를 사용하여 `PredictionModel`에 대한 품질 메트릭을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-267">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="1519e-268">회귀 평가자가 계산한 전체 메트릭이 포함된 <xref:Microsoft.ML.Data.RegressionMetrics> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-268">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span> <span data-ttu-id="1519e-269">모델의 품질을 확인하기 위해 이러한 메트릭을 표시하려면 먼저 메트릭을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-269">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="1519e-270">`Evaluate` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-270">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="1519e-271">다음 코드를 추가하여 모델을 평가하고 평가 메트릭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-271">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="1519e-272">[RSquared](../resources/glossary.md#coefficient-of-determination)는 회귀 모델의 다른 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-272">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="1519e-273">RSquared에서는 0과 1 사이의 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-273">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="1519e-274">해당 값이 1에 가까울수록 더 나은 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-274">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="1519e-275">RSquared 값을 표시하려면 `Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-275">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="1519e-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse)는 회귀 모델의 평가 메트릭 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="1519e-277">RMS가 낮을수록 더 나은 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-277">The lower it is, the better the model is.</span></span> <span data-ttu-id="1519e-278">RMS 값을 표시하려면 `Evaluate` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-278">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="1519e-279">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="1519e-279">Use the model for predictions</span></span>

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="1519e-280">모델 및 단일 댓글을 사용하여 테스트 데이터 결과를 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-280">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="1519e-281">다음 코드를 사용하여 `Evaluate` 메서드 바로 뒤에 `TestSinglePrediction` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-281">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

<span data-ttu-id="1519e-282">`TestSinglePrediction` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-282">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="1519e-283">테스트 데이터의 단일 댓글을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-283">Creates a single comment of test data.</span></span>
* <span data-ttu-id="1519e-284">테스트 데이터를 기준으로 요금 금액을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-284">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="1519e-285">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-285">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="1519e-286">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-286">Displays the predicted results.</span></span>

<span data-ttu-id="1519e-287">다음 코드를 사용하여 `Evaluate` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-287">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="1519e-288">저장한 zip 파일에서 모델을 로드하려고 하기 때문에 `Load` 메서드를 호출하기 직전에 `FileStream`을 만들겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-288">Since we want to load the model from the zip file we saved, we'll create the `FileStream` immediately before calling the `Load` method.</span></span> <span data-ttu-id="1519e-289">`TestSinglePrediction` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-289">Add the following code to the `TestSinglePrediction` method as the next line:</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

<span data-ttu-id="1519e-290">`model`은 여러 데이터 행에서 작동하는 `transformer`이지만, 일반적인 프로덕션 시나리오에서는 개별 예제에 대한 예측이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-290">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="1519e-291"><xref:Microsoft.ML.PredictionEngine%602>은 `CreatePredictionEngine` 메서드에서 반환되는 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-291">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="1519e-292">다음 코드를 추가하여 `PredictionEngine`을 `TestSinglePrediction` 메서드의 다음 줄로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-292">Let's add the following code to create the `PredictionEngine` as the next line in the `TestSinglePrediction` Method:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]

<span data-ttu-id="1519e-293">이 자습서에서는 이 클래스 내에서 하나의 테스트 이동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-293">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="1519e-294">나중에 이 모델로 실험할 다른 시나리오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-294">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="1519e-295">`TaxiTrip` 인스턴스를 만들어 주행을 추가하여 `TestSinglePrediction` 메서드에서 학습된 모델의 비용 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-295">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

<span data-ttu-id="1519e-296">해당 메서드를 사용하여 택시 주행 데이터의 단일 인스턴스를 기준으로 운임을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-296">We can use that to predict the fare based on a single instance of the taxi trip data.</span></span> <span data-ttu-id="1519e-297">예측을 가져오려면 데이터에 대해 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-297">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="1519e-298">입력 데이터는 문자열이고 모델은 기능화를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-298">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="1519e-299">파이프라인은 학습 및 예측 중에 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-299">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="1519e-300">특별히 예측을 위해 전처리/기능화 코드를 작성할 필요가 없고 동일한 API가 배치 및 일회성 예측을 둘 다 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-300">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="1519e-301">지정한 주행의 예상 운임을 표시하려면 `TestSinglePrediction` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-301">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="1519e-302">프로그램을 실행하여 테스트 사례에 대해 예측된 택시 요금을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-302">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="1519e-303">지금까지</span><span class="sxs-lookup"><span data-stu-id="1519e-303">Congratulations!</span></span> <span data-ttu-id="1519e-304">택시 요금 예측을 위한 기계 학습 모델을 성공적으로 빌드하고, 정확도를 평가하고, 예측하는 데 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-304">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="1519e-305">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-305">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1519e-306">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1519e-306">Next steps</span></span>

<span data-ttu-id="1519e-307">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="1519e-307">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="1519e-308">문제 이해</span><span class="sxs-lookup"><span data-stu-id="1519e-308">Understand the problem</span></span>
> * <span data-ttu-id="1519e-309">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="1519e-309">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="1519e-310">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="1519e-310">Prepare and understand the data</span></span>
> * <span data-ttu-id="1519e-311">학습 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="1519e-311">Create a learning pipeline</span></span>
> * <span data-ttu-id="1519e-312">데이터 로드 및 변환</span><span class="sxs-lookup"><span data-stu-id="1519e-312">Load and transform the data</span></span>
> * <span data-ttu-id="1519e-313">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="1519e-313">Choose a learning algorithm</span></span>
> * <span data-ttu-id="1519e-314">모델 학습</span><span class="sxs-lookup"><span data-stu-id="1519e-314">Train the model</span></span>
> * <span data-ttu-id="1519e-315">모델 평가</span><span class="sxs-lookup"><span data-stu-id="1519e-315">Evaluate the model</span></span>
> * <span data-ttu-id="1519e-316">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="1519e-316">Use the model for predictions</span></span>

<span data-ttu-id="1519e-317">다음 자습서로 이동하여 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1519e-317">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1519e-318">아이리스 클러스터링</span><span class="sxs-lookup"><span data-stu-id="1519e-318">Iris clustering</span></span>](iris-clustering.md)

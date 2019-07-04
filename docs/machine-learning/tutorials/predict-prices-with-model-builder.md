---
title: 모델 작성기와 함께 회귀를 사용하여 가격 예측
description: 이 자습서에서는 ML.NET 모델 작성기를 사용하여 가격(특히, 뉴욕 시 택시 요금)을 예측하기 위한 회귀 모델을 빌드하는 방법에 대해 설명합니다.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: db9788e3065a0f2f21d712b2d4826efea2d8a829
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410581"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="fe6a4-103">모델 작성기와 함께 회귀를 사용하여 가격 예측</span><span class="sxs-lookup"><span data-stu-id="fe6a4-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="fe6a4-104">ML.NET 모델 작성기 빌드를 사용하여 가격을 예측하기 위한 [회귀 모델](../resources/glossary.md#regression)을 빌드하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-104">Learn how to use ML.NET Model Builder to build a [regression model](../resources/glossary.md#regression) to predict prices.</span></span>  <span data-ttu-id="fe6a4-105">이 자습서에서 개발하는 .NET 콘솔 앱은 뉴욕의 과거 택시 요금 데이터를 기반으로 택시 요금을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="fe6a4-106">모델 작성기 가격 예측 템플릿은 숫자 예측 값이 필요한 모든 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="fe6a4-107">예제 시나리오에는 집값 예측, 수요 예측 및 판매 예측 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="fe6a4-108">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="fe6a4-109">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="fe6a4-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="fe6a4-110">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="fe6a4-110">Choose a scenario</span></span>
> * <span data-ttu-id="fe6a4-111">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fe6a4-111">Load the data</span></span>
> * <span data-ttu-id="fe6a4-112">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fe6a4-112">Train the model</span></span>
> * <span data-ttu-id="fe6a4-113">모델 평가</span><span class="sxs-lookup"><span data-stu-id="fe6a4-113">Evaluate the model</span></span>
> * <span data-ttu-id="fe6a4-114">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fe6a4-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="fe6a4-115">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="fe6a4-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fe6a4-116">Pre-requisites</span></span>

<span data-ttu-id="fe6a4-117">필수 구성 요소 및 설치 지침 목록을 보려면 [모델 작성기 설치 가이드](../how-to-guides/install-model-builder.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="fe6a4-118">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fe6a4-118">Create a console application</span></span>

1. <span data-ttu-id="fe6a4-119">"TaxiFarePrediction"이라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="fe6a4-120">**Microsoft.ML** NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-120">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="fe6a4-121">**솔루션 탐색기**에서 *TaxiFarePrediction* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-121">In **Solution Explorer**, right-click the *TaxiFarePrediction* project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="fe6a4-122">"nuget.org"를 패키지 소스로 선택하고, **찾아보기** 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-122">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="fe6a4-123">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="fe6a4-124">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="fe6a4-124">Prepare and understand the data</span></span>

1. <span data-ttu-id="fe6a4-125">프로젝트에 *Data*라는 디렉터리를 만들어 데이터 세트 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-125">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="fe6a4-126">[taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 데이터 세트를 다운로드하고 이전 단계에서 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-126">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) data set and save it to the *Data* folder you created at the previous step.</span></span> <span data-ttu-id="fe6a4-127">이 데이터 세트는 기계 학습 및 모델을 학습하고 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-127">This data set is used to train and evaluate the machine learning model.</span></span> <span data-ttu-id="fe6a4-128">이 데이터 세트는 원래 [NYC TLC Taxi Trip 데이터 세트](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-128">This data set is originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="fe6a4-129">**솔루션 탐색기**에서 *taxi-fare-train.csv* 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-129">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="fe6a4-130">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-130">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="fe6a4-131">`taxi-fare-train.csv` 데이터 세트의 각 행에는 택시에서 수행한 주행에 대한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-131">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span> 

1. <span data-ttu-id="fe6a4-132">**taxi-fare-train.csv** 데이터 세트 열기</span><span class="sxs-lookup"><span data-stu-id="fe6a4-132">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="fe6a4-133">제공된 데이터 집합에는 다음과 같은 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-133">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="fe6a4-134">**vendor_id:** 택시 공급업체의 ID가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="fe6a4-135">**rate_code:** 택시 이동의 요금 유형이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="fe6a4-136">**passenger_count:** 이동하는 승객 수가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="fe6a4-137">**trip_time_in_secs:** 이동에 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="fe6a4-138">이동을 완료하기 전에 이동 요금을 예측하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="fe6a4-139">해당 시간에는 이동이 얼마나 길지 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-139">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="fe6a4-140">따라서 이동 시간은 기능이 아니며 모델에서 이 열을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    * <span data-ttu-id="fe6a4-141">**trip_distance:** 이동 거리가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-141">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="fe6a4-142">**payment_type:** 결제 방법(현금 또는 신용 카드)이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="fe6a4-143">**fare_amount:** 지급한 총 택시 요금이 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="fe6a4-144">`label`은 예측할 열입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-144">The `label` is the column you want to predict.</span></span> <span data-ttu-id="fe6a4-145">회귀 작업을 수행할 때 목표는 숫자 값을 예측하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-145">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="fe6a4-146">이 가격 예측 시나리오에서는 택시 승차 비용이 예측됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-146">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="fe6a4-147">따라서 **fare_amount**는 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-147">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="fe6a4-148">식별된 `features`는 `label` 예측을 위해 모델에 제공하는 입력입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-148">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="fe6a4-149">이 경우에 나머지 열은 요금 금액을 예측하는 기능 또는 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-149">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="fe6a4-150">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="fe6a4-150">Choose a scenario</span></span>

<span data-ttu-id="fe6a4-151">모델을 학습하려면 모델 작성기에서 제공하는 사용 가능한 기계 학습 시나리오 목록에서 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-151">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="fe6a4-152">이 경우에 시나리오는 `Price Prediction`입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-152">In this case, the scenario is `Price Prediction`.</span></span> <span data-ttu-id="fe6a4-153">보다 광범위한 목록을 보려면 [모델 작성기 개요 문서](../automate-training-with-model-builder.md#scenarios)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-153">For a more extensive list visit the [Model Builder overview article](../automate-training-with-model-builder.md#scenarios).</span></span>

1. <span data-ttu-id="fe6a4-154">**솔루션 탐색기**에서 *TaxiFarePrediction* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **Machine Learning**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-154">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="fe6a4-155">모델 작성기 도구의 시나리오 단계에서 *가격 예측* 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-155">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="fe6a4-156">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fe6a4-156">Load the data</span></span>

<span data-ttu-id="fe6a4-157">모델 작성기는 SQL Server 데이터베이스 또는 로컬 파일 csv 또는 tsv 파일의 두 가지 소스에서 데이터를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-157">Model Builder accepts data from two sources, a SQL Server database or a local file csv or tsv file.</span></span> <span data-ttu-id="fe6a4-158">데이터 형식 요구 사항에 대한 자세한 내용은 [링크](../how-to-guides/install-model-builder.md#limitations)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-158">For more information on data format requirements, visit the following [link](../how-to-guides/install-model-builder.md#limitations).</span></span>

1. <span data-ttu-id="fe6a4-159">모델 작성기 도구의 데이터 단계의 데이터 원본 드롭다운에서 *파일*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-159">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="fe6a4-160">*파일 선택* 텍스트 상자 옆의 있는 단추를 선택하고 파일 탐색기를 사용하여 *Data* 디렉터리에서 *taxi-fare-test.csv*를 찾아서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-160">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="fe6a4-161">*예측할 레이블 또는 열* 드롭다운에서 *fare_amount*를 선택하고 모델 작성기 도구의 학습 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-161">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="fe6a4-162">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fe6a4-162">Train the model</span></span>

<span data-ttu-id="fe6a4-163">이 자습서에서 가격 예측 모델을 학습하는 데 사용되는 기계 학습 작업은 회귀입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-163">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="fe6a4-164">모델 학습 프로세스 중에 모델 작성기는 다른 회귀 알고리즘 및 설정을 통해 개별 모델을 학습하여 데이터 세트에 가장 적합한 모델을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-164">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="fe6a4-165">모델을 학습하는 데 필요한 시간은 데이터 양에 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-165">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="fe6a4-166">이 차트를 지침으로 사용하여 `Time to train (seconds)` 필드에 적절한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-166">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="fe6a4-167">\*데이터 세트 크기</span><span class="sxs-lookup"><span data-stu-id="fe6a4-167">\*Dataset Size</span></span>  | <span data-ttu-id="fe6a4-168">데이터 세트 형식</span><span class="sxs-lookup"><span data-stu-id="fe6a4-168">Dataset Type</span></span>       | <span data-ttu-id="fe6a4-169">평균 학습 시간\*</span><span class="sxs-lookup"><span data-stu-id="fe6a4-169">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="fe6a4-170">0 - 10Mb</span><span class="sxs-lookup"><span data-stu-id="fe6a4-170">0 - 10 Mb</span></span>     | <span data-ttu-id="fe6a4-171">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="fe6a4-171">Numeric and Text</span></span>   | <span data-ttu-id="fe6a4-172">10초</span><span class="sxs-lookup"><span data-stu-id="fe6a4-172">10 sec</span></span>
<span data-ttu-id="fe6a4-173">10 - 100Mb</span><span class="sxs-lookup"><span data-stu-id="fe6a4-173">10 - 100 Mb</span></span>   | <span data-ttu-id="fe6a4-174">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="fe6a4-174">Numeric and Text</span></span>   | <span data-ttu-id="fe6a4-175">10분</span><span class="sxs-lookup"><span data-stu-id="fe6a4-175">10 min</span></span>
<span data-ttu-id="fe6a4-176">100 - 500Mb</span><span class="sxs-lookup"><span data-stu-id="fe6a4-176">100 - 500 Mb</span></span>  | <span data-ttu-id="fe6a4-177">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="fe6a4-177">Numeric and Text</span></span>   | <span data-ttu-id="fe6a4-178">30분</span><span class="sxs-lookup"><span data-stu-id="fe6a4-178">30 min</span></span>
<span data-ttu-id="fe6a4-179">500 - 1Gb</span><span class="sxs-lookup"><span data-stu-id="fe6a4-179">500 - 1 Gb</span></span>    | <span data-ttu-id="fe6a4-180">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="fe6a4-180">Numeric and Text</span></span>   | <span data-ttu-id="fe6a4-181">60분</span><span class="sxs-lookup"><span data-stu-id="fe6a4-181">60 min</span></span>
<span data-ttu-id="fe6a4-182">1Gb+</span><span class="sxs-lookup"><span data-stu-id="fe6a4-182">1 Gb+</span></span>         | <span data-ttu-id="fe6a4-183">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="fe6a4-183">Numeric and Text</span></span>   | <span data-ttu-id="fe6a4-184">3시간+</span><span class="sxs-lookup"><span data-stu-id="fe6a4-184">3 hour+</span></span>

1. <span data-ttu-id="fe6a4-185">학습 데이터 파일이 10MB보다 크기 때문에 *학습 시간(초)* 의 값으로 600초(10 분)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-185">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="fe6a4-186">*학습 시작*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-186">Select *Start Training*.</span></span>

<span data-ttu-id="fe6a4-187">학습 프로세스 전체에서 진행률 데이터는 학습 단계의 `Progress` 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-187">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="fe6a4-188">상태는 학습 프로세스의 완료 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-188">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="fe6a4-189">가장 높은 정확도는 모델 작성기가 현재까지 찾은 최고 성능 모델의 정확도를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-189">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="fe6a4-190">더 높은 정확도는 테스트 데이터에서 모델이 더 정확하게 예측된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-190">Higher accuracy means the model predicted more correctly on test data.</span></span> 
- <span data-ttu-id="fe6a4-191">최상의 알고리즘은 모델 작성기가 현재까지 찾은 최고 성능 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-191">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="fe6a4-192">마지막 알고리즘은 모델 작성기가 가장 최근에 학습하기 위해 사용한 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-192">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="fe6a4-193">학습이 완료되면 평가 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-193">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="fe6a4-194">모델 평가</span><span class="sxs-lookup"><span data-stu-id="fe6a4-194">Evaluate the model</span></span>

<span data-ttu-id="fe6a4-195">학습 단계의 결과는 최상의 성능을 가진 하나의 모델이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-195">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="fe6a4-196">모델 작성기 도구의 평가 단계인 출력 섹션에는 *최상의 모델* 항목에서 가장 성능이 좋은 모델에서 사용되는 알고리즘과 *최상의 모델 품질(RSquared)* 의 메트릭이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-196">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="fe6a4-197">또한 상위 5개 모델 및 해당 메트릭을 포함하는 요약 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-197">Additionally, a summary table containing top five models and their metrics.</span></span> <span data-ttu-id="fe6a4-198">[모델 메트릭 평가](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics)에 대해 자세히 알아보려면 다음 링크를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-198">Visit the following link to learn more about [evaluating model metrics](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span></span>

<span data-ttu-id="fe6a4-199">정확도 메트릭에 만족하지 않는 경우 모델 정확도를 개선하기 위한 몇 가지 쉬운 방법은 모델을 학습하거나 더 많은 데이터를 사용하기 위한 시간을 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-199">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="fe6a4-200">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fe6a4-200">Use the model for predictions</span></span>

<span data-ttu-id="fe6a4-201">학습 프로세스의 결과로 두 개의 프로젝트가 만들어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-201">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="fe6a4-202">TaxiFarePredictionML.ConsoleApp: 모델 학습 및 소비 코드가 포함된 .NET 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-202">TaxiFarePredictionML.ConsoleApp: A .NET Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="fe6a4-203">TaxiFarePredictionML.Model: 입력 및 출력 모델 데이터의 스키마를 정의하는 데이터 모델뿐만 아니라 학습 중 가장 성능이 뛰어난 모델의 지속 버전을 포함하는 .NET Standard 클래스 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-203">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="fe6a4-204">모델 작성기 도구의 코드 섹션에서 **프로젝트 추가**를 선택하여 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-204">In the code section of the Model Builder tool, select **Added Projects** to add the projects to the solution.</span></span>
1. <span data-ttu-id="fe6a4-205">솔루션 탐색기에서 *TaxiFarePrediction* 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-205">In solution explorer, right-click the *TaxiFarePrediction* project.</span></span> <span data-ttu-id="fe6a4-206">그런 다음, 선택 **추가 > 기존 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-206">Then, select **Add > Existing Item**.</span></span> <span data-ttu-id="fe6a4-207">파일 유형 드롭다운의 경우 `All Files`를 선택하고 *TaxiFarePredictionML.Model* 프로젝트 디렉터리로 이동하여 `MLModel.zip` 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-207">For file type drop down, select `All Files`, navigate to the *TaxiFarePredictionML.Model* project directory and select the `MLModel.zip` file.</span></span> <span data-ttu-id="fe6a4-208">그런 다음, 최근에 추가한 `MLModel.zip` 파일을 마우스 오른쪽 단추로 클릭하고 *속성*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-208">Then right-click the recently added `MLModel.zip` file and select *Properties*.</span></span> <span data-ttu-id="fe6a4-209">출력 디렉터리에 복사 옵션의 경우 드롭다운에서 *변경된 내용만 복사*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-209">For the Copy to Output Directory option, select *Copy if Newer* from the dropdown.</span></span>
1. <span data-ttu-id="fe6a4-210">*TaxiFarePrediction* 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-210">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="fe6a4-211">그런 다음, **추가 > 참조**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-211">Then, **Add > Reference**.</span></span> <span data-ttu-id="fe6a4-212">**프로젝트 > 솔루션** 노드를 선택하고 목록에서 *TaxiFarePredictionML.Model* 프로젝트를 확인하고 OK를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-212">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>

4. <span data-ttu-id="fe6a4-213">*TaxiFarePrediction* 프로젝트에서 *Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-213">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
5. <span data-ttu-id="fe6a4-214">다음 using 명령문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-214">Add the following using statements:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. <span data-ttu-id="fe6a4-215">`Program` 클래스에 `ConsumeModel` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-215">Add the `ConsumeModel` method to the `Program` class.</span></span> <span data-ttu-id="fe6a4-216">`ConsumeModel`은 모델 작성기에서 생성된 모델을 기반으로 `PredictionEngine`을 만들어 새 데이터를 예측하고 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-216">The `ConsumeModel` will create a `PredictionEngine` based on the model generated by Model Builder to make predictions on new data and print them out to the console.</span></span>

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. <span data-ttu-id="fe6a4-217">다음 코드를 `Main` 메서드에 추가하고 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-217">Add the following code to the `Main` method and run the application.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    <span data-ttu-id="fe6a4-218">프로그램에서 생성된 출력은 아래 코드 조각과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-218">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="fe6a4-219">생성된 프로젝트를 나중에 다른 솔루션 내에서 참조해야 하는 경우 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 디렉터리 내에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-219">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe6a4-220">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fe6a4-220">Next Steps</span></span>

<span data-ttu-id="fe6a4-221">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-221">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="fe6a4-222">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="fe6a4-222">Prepare and understand the data</span></span>
> * <span data-ttu-id="fe6a4-223">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="fe6a4-223">Choose a scenario</span></span>
> * <span data-ttu-id="fe6a4-224">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fe6a4-224">Load the data</span></span>
> * <span data-ttu-id="fe6a4-225">모델 학습</span><span class="sxs-lookup"><span data-stu-id="fe6a4-225">Train the model</span></span>
> * <span data-ttu-id="fe6a4-226">모델 평가</span><span class="sxs-lookup"><span data-stu-id="fe6a4-226">Evaluate the model</span></span>
> * <span data-ttu-id="fe6a4-227">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="fe6a4-227">Use the model for predictions</span></span>

<span data-ttu-id="fe6a4-228">모델을 배포하는 방법을 알아보려면 다음 방법 문서 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6a4-228">Advance to either of the following how-to articles to learn how to deploy your model.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fe6a4-229">Azure Functions에 모델 배포</span><span class="sxs-lookup"><span data-stu-id="fe6a4-229">Deploy a model to Azure Functions</span></span>](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="fe6a4-230">Web API에 모델 배포</span><span class="sxs-lookup"><span data-stu-id="fe6a4-230">Deploy a model to a Web API</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)

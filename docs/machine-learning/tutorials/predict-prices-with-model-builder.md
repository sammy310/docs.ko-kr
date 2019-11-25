---
title: '자습서: 모델 작성기와 함께 회귀를 사용하여 가격 예측'
description: 이 자습서에서는 ML.NET 모델 작성기를 사용하여 가격(특히, 뉴욕 시 택시 요금)을 예측하기 위한 회귀 모델을 빌드하는 방법에 대해 설명합니다.
author: luisquintanilla
ms.author: luquinta
ms.date: 10/08/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bd6acd83df4d2d5f19d30da847212d60b1576199
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977350"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="7d0e2-103">자습서: 모델 작성기와 함께 회귀를 사용하여 가격 예측</span><span class="sxs-lookup"><span data-stu-id="7d0e2-103">Tutorial: Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="7d0e2-104">ML.NET 모델 작성기 빌드를 사용하여 가격을 예측하기 위한 회귀 모델을 빌드하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-104">Learn how to use ML.NET Model Builder to build a regression model to predict prices.</span></span>  <span data-ttu-id="7d0e2-105">이 자습서에서 개발하는 .NET 콘솔 앱은 뉴욕의 과거 택시 요금 데이터를 기반으로 택시 요금을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="7d0e2-106">모델 작성기 가격 예측 템플릿은 숫자 예측 값이 필요한 모든 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="7d0e2-107">예제 시나리오에는 집값 예측, 수요 예측 및 판매 예측 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="7d0e2-108">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="7d0e2-109">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="7d0e2-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="7d0e2-110">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="7d0e2-110">Choose a scenario</span></span>
> - <span data-ttu-id="7d0e2-111">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="7d0e2-111">Load the data</span></span>
> - <span data-ttu-id="7d0e2-112">모델 학습</span><span class="sxs-lookup"><span data-stu-id="7d0e2-112">Train the model</span></span>
> - <span data-ttu-id="7d0e2-113">모델 평가</span><span class="sxs-lookup"><span data-stu-id="7d0e2-113">Evaluate the model</span></span>
> - <span data-ttu-id="7d0e2-114">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="7d0e2-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="7d0e2-115">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="7d0e2-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7d0e2-116">Pre-requisites</span></span>

<span data-ttu-id="7d0e2-117">필수 구성 요소 및 설치 지침 목록을 보려면 [모델 작성기 설치 가이드](../how-to-guides/install-model-builder.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="7d0e2-118">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="7d0e2-118">Create a console application</span></span>

1. <span data-ttu-id="7d0e2-119">"TaxiFarePrediction"이라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="7d0e2-120">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="7d0e2-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="7d0e2-121">프로젝트에 *Data*라는 디렉터리를 만들어 데이터 세트 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="7d0e2-122">기계 학습 모델을 교육하고 평가하는 데 사용되는 데이터 세트는 원래 NYC TLC 택시 여행 데이터 세트에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    1. <span data-ttu-id="7d0e2-123">데이터 세트를 다운로드하려면 [taxi-fare-train.csv 다운로드 링크](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    1. <span data-ttu-id="7d0e2-124">페이지가 로드되면 페이지의 아무 곳이나 마우스 오른쪽 단추로 클릭하고 **다른 이름으로 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    1. <span data-ttu-id="7d0e2-125">**다른 이름으로 저장 대화 상자**를 사용하여 이전 단계에서 만든 *Data* 폴더에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="7d0e2-126">**솔루션 탐색기**에서 *taxi-fare-train.csv* 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="7d0e2-127">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="7d0e2-128">`taxi-fare-train.csv` 데이터 세트의 각 행에는 택시에서 수행한 주행에 대한 세부 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="7d0e2-129">**taxi-fare-train.csv** 데이터 세트 열기</span><span class="sxs-lookup"><span data-stu-id="7d0e2-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="7d0e2-130">제공된 데이터 집합에는 다음과 같은 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="7d0e2-131">**vendor_id:** 택시 공급업체의 ID가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="7d0e2-132">**rate_code:** 택시 이동의 요금 유형이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="7d0e2-133">**passenger_count:** 이동하는 승객 수가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="7d0e2-134">**trip_time_in_secs:** 이동에 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-134">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="7d0e2-135">이동을 완료하기 전에 이동 요금을 예측하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-135">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="7d0e2-136">해당 시간에는 이동이 얼마나 길지 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-136">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="7d0e2-137">따라서 이동 시간은 기능이 아니며 모델에서 이 열을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-137">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    - <span data-ttu-id="7d0e2-138">**trip_distance:** 이동 거리가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-138">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="7d0e2-139">**payment_type:** 결제 방법(현금 또는 신용 카드)이 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-139">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="7d0e2-140">**fare_amount:** 지급한 총 택시 요금이 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-140">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="7d0e2-141">`label`은 예측할 열입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-141">The `label` is the column you want to predict.</span></span> <span data-ttu-id="7d0e2-142">회귀 작업을 수행할 때 목표는 숫자 값을 예측하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-142">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="7d0e2-143">이 가격 예측 시나리오에서는 택시 승차 비용이 예측됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-143">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="7d0e2-144">따라서 **fare_amount**는 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-144">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="7d0e2-145">식별된 `features`는 `label` 예측을 위해 모델에 제공하는 입력입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-145">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="7d0e2-146">이 경우에 **trip_time_in_secs**를 제외한 나머지 열은 요금을 예측하는 기능 또는 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-146">In this case, the rest of the columns with the exception of **trip_time_in_secs** are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="7d0e2-147">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="7d0e2-147">Choose a scenario</span></span>

<span data-ttu-id="7d0e2-148">모델을 학습하려면 모델 작성기에서 제공하는 사용 가능한 기계 학습 시나리오 목록에서 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-148">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="7d0e2-149">이 경우에 시나리오는 `Price Prediction`입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-149">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="7d0e2-150">**솔루션 탐색기**에서 *TaxiFarePrediction* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **Machine Learning**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-150">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="7d0e2-151">모델 작성기 도구의 시나리오 단계에서 *가격 예측* 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-151">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="7d0e2-152">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="7d0e2-152">Load the data</span></span>

<span data-ttu-id="7d0e2-153">모델 작성기는 SQL Server 데이터베이스 또는 로컬 파일 csv 또는 tsv 형식의 두 가지 소스에서 데이터를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-153">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="7d0e2-154">모델 작성기 도구의 데이터 단계의 데이터 원본 드롭다운에서 *파일*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-154">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="7d0e2-155">*파일 선택* 텍스트 상자 옆의 있는 단추를 선택하고 파일 탐색기를 사용하여 *Data* 디렉터리에서 *taxi-fare-test.csv*를 찾아서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-155">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="7d0e2-156">*예측할 열(레이블)* 드롭다운에서 *fare_amount*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-156">Choose *fare_amount* in the *Column to Predict (Label)* dropdown.</span></span>
1. <span data-ttu-id="7d0e2-157">*입력 열(기능)*  드롭다운을 확장하고 *trip_time_in_secs* 열을 선택 취소하여 학습 동안 기능으로서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-157">Expand the *Input Columns (Features)* dropdown and uncheck the *trip_time_in_secs* column to exclude it as a feature during training.</span></span>  <span data-ttu-id="7d0e2-158">모델 작성기 도구의 학습 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-158">Navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="7d0e2-159">모델 학습</span><span class="sxs-lookup"><span data-stu-id="7d0e2-159">Train the model</span></span>

<span data-ttu-id="7d0e2-160">이 자습서에서 가격 예측 모델을 학습하는 데 사용되는 기계 학습 작업은 회귀입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-160">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="7d0e2-161">모델 학습 프로세스 중에 모델 작성기는 다른 회귀 알고리즘 및 설정을 통해 개별 모델을 학습하여 데이터 세트에 가장 적합한 모델을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-161">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="7d0e2-162">모델을 학습하는 데 필요한 시간은 데이터 양에 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-162">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="7d0e2-163">모델 작성기는 데이터 소스의 크기에 따라 **학습 시간(초)** 의 기본값을 자동으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-163">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="7d0e2-164">더 긴 학습 시간을 원하지 않는다면 *학습 시간(초)* 의 기본값을 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-164">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="7d0e2-165">*학습 시작*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-165">Select *Start Training*.</span></span>

<span data-ttu-id="7d0e2-166">학습 프로세스 전체에서 진행률 데이터는 학습 단계의 `Progress` 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-166">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="7d0e2-167">상태는 학습 프로세스의 완료 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-167">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="7d0e2-168">가장 높은 정확도는 모델 작성기가 현재까지 찾은 최고 성능 모델의 정확도를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-168">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="7d0e2-169">더 높은 정확도는 테스트 데이터에서 모델이 더 정확하게 예측된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-169">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="7d0e2-170">최상의 알고리즘은 모델 작성기가 현재까지 찾은 최고 성능 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-170">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="7d0e2-171">마지막 알고리즘은 모델 작성기가 가장 최근에 학습하기 위해 사용한 알고리즘의 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-171">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="7d0e2-172">학습이 완료되면 평가 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-172">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="7d0e2-173">모델 평가</span><span class="sxs-lookup"><span data-stu-id="7d0e2-173">Evaluate the model</span></span>

<span data-ttu-id="7d0e2-174">학습 단계의 결과는 최상의 성능을 가진 하나의 모델이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-174">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="7d0e2-175">모델 작성기 도구의 평가 단계인 출력 섹션에는 *최상의 모델* 항목에서 가장 성능이 좋은 모델에서 사용되는 알고리즘과 *최상의 모델 품질(RSquared)* 의 메트릭이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-175">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="7d0e2-176">또한 상위 5개 모델 및 해당 메트릭을 포함하는 요약 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-176">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="7d0e2-177">정확도 메트릭에 만족하지 않는 경우 모델 정확도를 개선하기 위한 몇 가지 쉬운 방법은 모델을 학습하거나 더 많은 데이터를 사용하기 위한 시간을 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-177">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="7d0e2-178">그렇지 않으면 코드 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-178">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="7d0e2-179">코드를 추가하여 예측하기</span><span class="sxs-lookup"><span data-stu-id="7d0e2-179">Add the code to make predictions</span></span>

<span data-ttu-id="7d0e2-180">학습 프로세스의 결과로 두 개의 프로젝트가 만들어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-180">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="7d0e2-181">TaxiFarePredictionML.ConsoleApp: 모델 학습 및 샘플 소비 코드가 포함된 .NET Core 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-181">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and sample consumption code.</span></span>
- <span data-ttu-id="7d0e2-182">TaxiFarePredictionML.Model: 입력 및 출력 모델 데이터의 스키마를 정의하는 데이터 모델, 학습 중 가장 성능이 뛰어난 모델의 저장된 버전, 예측을 위한 `ConsumeModel`이라는 도우미 클래스를 포함하는 .NET Standard 클래스 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-182">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data, the saved version of the best performing model during training and a helper class called `ConsumeModel` to make predictions.</span></span>

1. <span data-ttu-id="7d0e2-183">모델 작성기 도구의 코드 단계에서 **프로젝트 추가**를 선택하여 자동 생성된 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-183">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="7d0e2-184">*TaxiFarePrediction* 프로젝트에서 *Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-184">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="7d0e2-185">*TaxiFarePredictionML.Model* 프로젝트를 참조하도록 다음 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-185">Add the following using statement to reference the *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. <span data-ttu-id="7d0e2-186">모델을 사용하여 새 데이터에 대해 예측을 수행하려면 `Main` 메서드 내부에 `ModelInput` 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-186">To make a prediction on new data using the model, create a new instance of the `ModelInput` class inside the `Main` method of your application.</span></span> <span data-ttu-id="7d0e2-187">요금 금액은 입력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-187">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="7d0e2-188">모델에서 해당 금액을 예측하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-188">This is because the model will generate the prediction for it.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. <span data-ttu-id="7d0e2-189">`ConsumeModel` 클래스의 `Predict` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-189">Use the `Predict` method from the `ConsumeModel` class.</span></span> <span data-ttu-id="7d0e2-190">`Predict` 메서드는 학습된 모델을 로드하고 모델에 대한 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만든 후 새 데이터에 대해 예측하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-190">The `Predict` method loads the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and uses it to make predictions on new data.</span></span>

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. <span data-ttu-id="7d0e2-191">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-191">Run the application.</span></span>

    <span data-ttu-id="7d0e2-192">프로그램에서 생성된 출력은 아래 코드 조각과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-192">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 14.96086
    ```

<span data-ttu-id="7d0e2-193">생성된 프로젝트를 나중에 다른 솔루션 내에서 참조해야 하는 경우 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 디렉터리 내에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-193">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d0e2-194">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7d0e2-194">Next Steps</span></span>

<span data-ttu-id="7d0e2-195">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-195">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="7d0e2-196">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="7d0e2-196">Prepare and understand the data</span></span>
> - <span data-ttu-id="7d0e2-197">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="7d0e2-197">Choose a scenario</span></span>
> - <span data-ttu-id="7d0e2-198">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="7d0e2-198">Load the data</span></span>
> - <span data-ttu-id="7d0e2-199">모델 학습</span><span class="sxs-lookup"><span data-stu-id="7d0e2-199">Train the model</span></span>
> - <span data-ttu-id="7d0e2-200">모델 평가</span><span class="sxs-lookup"><span data-stu-id="7d0e2-200">Evaluate the model</span></span>
> - <span data-ttu-id="7d0e2-201">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="7d0e2-201">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7d0e2-202">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="7d0e2-202">Additional Resources</span></span>

<span data-ttu-id="7d0e2-203">이 자습서에서 언급한 항목에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d0e2-203">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="7d0e2-204">모델 작성기 시나리오</span><span class="sxs-lookup"><span data-stu-id="7d0e2-204">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="7d0e2-205">재발</span><span class="sxs-lookup"><span data-stu-id="7d0e2-205">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="7d0e2-206">회귀 모델 메트릭</span><span class="sxs-lookup"><span data-stu-id="7d0e2-206">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="7d0e2-207">NYC TLC 택시 여행 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="7d0e2-207">NYC TLC Taxi Trip data set</span></span>](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

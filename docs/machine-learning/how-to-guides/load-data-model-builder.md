---
title: 모델 작성기용 학습 데이터 로드
description: ML.NET의 모델 작성기 시나리오 중 하나에서 사용하기 위해 SQL Server 데이터베이스 또는 파일에서 학습 데이터를 로드하는 방법에 대해 알아봅니다.
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: cc93b3f77284ed283a8d7cbd52b8cd02b4fd9066
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977059"
---
# <a name="load-training-data-into-model-builder"></a><span data-ttu-id="fe262-103">모델 작성기로 학습 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fe262-103">Load training data into Model Builder</span></span>

<span data-ttu-id="fe262-104">ML.NET의 모델 작성기 시나리오 중 하나에서 사용하기 위해 파일 또는 SQL Server 데이터베이스에서 학습 데이터 세트를 로드하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-104">Learn how to load your training datasets from a file or a SQL Server database for use in one of the Model Builder scenarios for ML.NET.</span></span> <span data-ttu-id="fe262-105">모델 작성기 시나리오에서는 SQL Server 데이터베이스, 이미지 파일, CSV 또는 TSV 파일 형식을 학습 데이터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-105">Model Builder scenarios can use SQL Server databases, image files, and CSV or TSV file formats as training data.</span></span>

## <a name="training-dataset-limitations-in-model-builder"></a><span data-ttu-id="fe262-106">모델 작성기의 학습 데이터 세트 제한 사항</span><span class="sxs-lookup"><span data-stu-id="fe262-106">Training dataset limitations in Model Builder</span></span>

<span data-ttu-id="fe262-107">모델 작성기는 학습 모델에 사용할 수 있는 데이터의 양과 형식을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-107">Model Builder limits the amount and type of data you can use for training models:</span></span>

- <span data-ttu-id="fe262-108">SQL Server 데이터: 100,000개 행</span><span class="sxs-lookup"><span data-stu-id="fe262-108">SQL Server data: 100,000 rows</span></span>
- <span data-ttu-id="fe262-109">CSV 및 TSV 파일: 크기 제한 없음</span><span class="sxs-lookup"><span data-stu-id="fe262-109">CSV and TSV files: No size limit</span></span>
- <span data-ttu-id="fe262-110">이미지: PNG 및 JPG만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-110">Images: PNG and JPG only.</span></span>

## <a name="model-builder-scenarios"></a><span data-ttu-id="fe262-111">모델 작성기 시나리오</span><span class="sxs-lookup"><span data-stu-id="fe262-111">Model Builder scenarios</span></span>

<span data-ttu-id="fe262-112">모델 작성기를 사용하면 다음과 같은 기계 학습 시나리오에 대한 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-112">Model Builder helps you create models for the following machine learning scenarios:</span></span>

- <span data-ttu-id="fe262-113">감정 분석(이진 분류): 텍스트 데이터를 두 가지 범주로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-113">Sentiment analysis (binary classification): Classify textual data into two categories.</span></span>
- <span data-ttu-id="fe262-114">문제 분류(다중 클래스 분류): 텍스트 데이터를 세 가지 이상 범주로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-114">Issue classification (multiclass classification): Classify textual data into 3 or more categories.</span></span>
- <span data-ttu-id="fe262-115">가격 예측(회귀): 숫자 값을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-115">Price prediction (regression): Predict a numeric value.</span></span>
- <span data-ttu-id="fe262-116">이미지 분류(딥 러닝): 특성을 기반으로 이미지를 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-116">Image classification (deep learning): Categorize images based on characteristics.</span></span>
- <span data-ttu-id="fe262-117">사용자 지정 시나리오: 회귀, 분류 및 기타 작업을 사용하여 데이터에서 사용자 지정 시나리오를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-117">Custom scenario: Build custom scenarios from your data using regression, classification, and other tasks.</span></span>

<span data-ttu-id="fe262-118">이 문서에서는 텍스트 또는 숫자 데이터를 사용하는 분류 및 회귀 시나리오와 이미지 분류 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-118">This article covers classification and regression scenarios with textual or numerical data, and image classification scenarios.</span></span>

## <a name="load-text-or-numeric-data-from-a-file"></a><span data-ttu-id="fe262-119">파일에서 텍스트 또는 숫자 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fe262-119">Load text or numeric data from a file</span></span>

<span data-ttu-id="fe262-120">파일의 텍스트 또는 숫자 데이터를 모델 작성기로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-120">You can load text or numeric data from a file into Model Builder.</span></span> <span data-ttu-id="fe262-121">쉼표로 구분된(CSV) 파일 형식 또는 탭으로 구분된(TSV) 파일 형식을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-121">It accepts comma-delimited (CSV) or tab-delimited (TSV) file formats.</span></span>

1. <span data-ttu-id="fe262-122">모델 작성기의 데이터 단계에서 데이터 원본 드롭다운의 **파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-122">In the data step of Model Builder, select **File** from the data source dropdown.</span></span>
2. <span data-ttu-id="fe262-123">**파일 선택** 텍스트 상자 옆의 있는 단추를 선택하고 파일 탐색기를 사용하여 데이터 파일을 찾고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-123">Select the button next to the **Select a file** text box, and use File Explorer to browse and select the data file.</span></span>
3. <span data-ttu-id="fe262-124">**예측할 열(레이블)** 드롭다운에서 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-124">Choose a category in the **Column to Predict (Label)** dropdown.</span></span>
4. <span data-ttu-id="fe262-125">**입력 열(기능)** 드롭다운에서 포함하려는 데이터 열이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-125">From the **Input Columns (Features)** dropdown, confirm the data columns you want to include are checked.</span></span>

<span data-ttu-id="fe262-126">모델 작성기에 대한 데이터 원본 파일을 설정하는 작업을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-126">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="fe262-127">**학습** 링크를 선택하여 모델 작성기의 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-127">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="load-data-from-a-sql-server-database"></a><span data-ttu-id="fe262-128">SQL Server 데이터베이스에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="fe262-128">Load data from a SQL Server database</span></span>

<span data-ttu-id="fe262-129">모델 작성기는 로컬 및 원격 SQL Server 데이터베이스에서 데이터를 로드할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-129">Model Builder supports loading data from local and remote SQL Server databases.</span></span>

<span data-ttu-id="fe262-130">SQL Server 데이터베이스에서 모델 작성기로 데이터를 로드하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-130">To load data from a SQL Server database into Module Builder:</span></span>

1. <span data-ttu-id="fe262-131">모델 작성기의 데이터 단계에서 데이터 원본 드롭다운의 **SQL Server**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-131">In the data step of Model Builder, select **SQL Server** from the data source dropdown.</span></span>
1. <span data-ttu-id="fe262-132">**SQL Server 데이터베이스에 연결** 텍스트 상자 옆에 있는 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-132">Select the button next to the **Connect to SQL Server database** text box.</span></span>
    1. <span data-ttu-id="fe262-133">**데이터 선택** 대화 상자에서 **Microsoft SQL Server 데이터베이스 파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-133">In the **Choose Data** dialog, select **Microsoft SQL Server Database File**.</span></span>
    1. <span data-ttu-id="fe262-134">**항상 이 선택 사용** 확인란의 선택을 취소하고 **계속**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-134">Uncheck the **Always use this selection** checkbox and select **Continue**</span></span>
    1. <span data-ttu-id="fe262-135">**연결 속성** 대화 상자에서 **찾아보기**를 선택한 후 다운로드한 .MDF 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-135">In the **Connection Properties** dialog, select **Browse** and select the downloaded .MDF file.</span></span>
    1. <span data-ttu-id="fe262-136">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-136">Select **OK**</span></span>
1. <span data-ttu-id="fe262-137">**테이블 이름** 드롭다운에서 데이터 세트 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-137">Choose the dataset name from the **Table Name** dropdown.</span></span>
1. <span data-ttu-id="fe262-138">**예측할 열(레이블)** 드롭다운에서 예측을 수행하려는 데이터 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-138">From the **Column to Predict (Label)** dropdown, choose the data category on which you want to make a prediction.</span></span>
1. <span data-ttu-id="fe262-139">**입력 열(기능)** 드롭다운에서 포함하려는 열이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-139">From the **Input Columns (Features)** dropdown, confirm the columns you want to include are checked.</span></span>

<span data-ttu-id="fe262-140">모델 작성기에 대한 데이터 원본 파일을 설정하는 작업을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-140">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="fe262-141">**학습** 링크를 선택하여 모델 작성기의 다음 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-141">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="set-up-image-data-files"></a><span data-ttu-id="fe262-142">이미지 데이터 파일 설정</span><span class="sxs-lookup"><span data-stu-id="fe262-142">Set up image data files</span></span>

<span data-ttu-id="fe262-143">모델 작성기에서는 이미지 데이터가 분류 범주에 해당하는 폴더에 구성된 JPG 또는 PNG 파일이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-143">Model Builder expects image data to be JPG or PNG files organized in folders that correspond to the categories of the classification.</span></span>

<span data-ttu-id="fe262-144">모델 작성기에 이미지를 로드하려면 단일 최상위 디렉터리에 대한 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-144">To load images into Model Builder, provide the path to a single top-level directory:</span></span>

- <span data-ttu-id="fe262-145">이 최상위 디렉터리에는 예측할 각 범주에 대한 하위 폴더가 하나씩 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-145">This top-level directory contains one subfolder for each of the categories to predict.</span></span>
- <span data-ttu-id="fe262-146">각 하위 폴더에는 해당 범주에 속하는 이미지 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-146">Each subfolder contains the image files belonging to its category.</span></span>

<span data-ttu-id="fe262-147">아래 그림에 나와 있는 폴더 구조에서 최상위 디렉터리는 *flower_photos*입니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-147">In the folder structure illustrated below, the top-level directory is *flower_photos*.</span></span> <span data-ttu-id="fe262-148">예측하려는 범주에 해당하는 5개의 하위 디렉터리(daisy, dandelion, roses, sunflowers 및 tulips)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-148">There are five subdirectories corresponding to the categories you want to predict: daisy, dandelion, roses, sunflowers, and tulips.</span></span> <span data-ttu-id="fe262-149">이러한 각 하위 디렉터리는 해당 범주에 속하는 이미지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-149">Each of these subdirectories contains images belonging to its respective category.</span></span>

```text
\---flower_photos
    +---daisy
    |       100080576_f52e8ee070_n.jpg
    |       102841525_bd6628ae3c.jpg
    |       105806915_a9c13e2106_n.jpg
    |
    +---dandelion
    |       10443973_aeb97513fc_m.jpg
    |       10683189_bd6e371b97.jpg
    |       10919961_0af657c4e8.jpg
    |
    +---roses
    |       102501987_3cdb8e5394_n.jpg
    |       110472418_87b6a3aa98_m.jpg
    |       118974357_0faa23cce9_n.jpg
    |
    +---sunflowers
    |       127192624_afa3d9cb84.jpg
    |       145303599_2627e23815_n.jpg
    |       147804446_ef9244c8ce_m.jpg
    |
    \---tulips
            100930342_92e8746431_n.jpg
            107693873_86021ac4ea_n.jpg
            10791227_7168491604.jpg
```

## <a name="next-steps"></a><span data-ttu-id="fe262-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fe262-150">Next steps</span></span>

<span data-ttu-id="fe262-151">모델 작성기를 사용하여 기계 학습 앱을 빌드하려면 다음 자습서를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fe262-151">Follow these tutorials to build machine learning apps with Model Builder:</span></span>

- [<span data-ttu-id="fe262-152">회귀를 사용하여 가격 예측</span><span class="sxs-lookup"><span data-stu-id="fe262-152">Predict prices using regression</span></span>](../tutorials/predict-prices-with-model-builder.md)
- [<span data-ttu-id="fe262-153">이진 분류를 사용하여 웹 애플리케이션에서 감정 분석</span><span class="sxs-lookup"><span data-stu-id="fe262-153">Analyze sentiment in a web application using binary classification</span></span>](../tutorials/sentiment-analysis-model-builder.md )

<span data-ttu-id="fe262-154">코드를 사용하여 모델을 학습하는 경우 [ML.NET API를 사용하여 데이터를 로드하는 방법을 알아보세요](load-data-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="fe262-154">If you're training a model using code, [learn how to load data using the ML.NET API](load-data-ml-net.md).</span></span>

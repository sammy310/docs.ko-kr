---
title: 모델 작성기란 무엇이며 어떻게 작동하나요?
description: ML.NET 모델 작성기를 사용하여 기계 학습 모델을 자동으로 학습하는 방법
ms.date: 06/01/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 80f5f5d064c4e0c4097dacc6022d4624c1516ab9
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679679"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="033cb-103">모델 작성기란 무엇이며 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="033cb-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="033cb-104">ML.NET 모델 작성기는 사용자 지정 기계 학습 모델을 빌드, 학습 및 배포하기 위한 직관적인 그래픽 Visual Studio 확장 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="033cb-105">모델 작성기는 AutoML(자동 기계 학습)을 사용하여 다양한 기계 학습 알고리즘과 설정을 탐색하여 시나리오에 가장 적합한 것을 찾아냅니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="033cb-106">모델 작성기를 사용하기 위해 기계 학습 전문 지식이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="033cb-107">필요한 것은 약간의 데이터와 해결해야 할 문제뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="033cb-108">모델 작성기는 .NET 애플리케이션에 모델을 추가하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![모델 작성기 Visual Studio 확장 사용자 인터페이스 애니메이션](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="033cb-110">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-110">Model Builder is currently in Preview.</span></span>

## <a name="scenario"></a><span data-ttu-id="033cb-111">시나리오</span><span class="sxs-lookup"><span data-stu-id="033cb-111">Scenario</span></span>

<span data-ttu-id="033cb-112">애플리케이션에 대한 기계 학습 모델을 생성하기 위해 모델 작성기에 다양한 시나리오를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="033cb-113">시나리오는 데이터를 사용하여 수행할 예측 유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="033cb-114">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="033cb-114">For example:</span></span>

- <span data-ttu-id="033cb-115">과거 판매 데이터를 기반으로 향후 제품 판매량 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="033cb-116">고객 리뷰에 따라 감정을 긍정 또는 부정으로 분류</span><span class="sxs-lookup"><span data-stu-id="033cb-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="033cb-117">은행 트랜잭션이 사기인지 여부를 검색</span><span class="sxs-lookup"><span data-stu-id="033cb-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="033cb-118">고객 피드백 문제를 회사의 올바른 팀에 전달</span><span class="sxs-lookup"><span data-stu-id="033cb-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="033cb-119">어떤 기계 학습 시나리오가 나에게 적합한가요?</span><span class="sxs-lookup"><span data-stu-id="033cb-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="033cb-120">모델 작성기에서 시나리오를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="033cb-121">시나리오 형식은 수행하려는 예측의 종류에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="text-classification"></a><span data-ttu-id="033cb-122">텍스트 분류</span><span class="sxs-lookup"><span data-stu-id="033cb-122">Text classification</span></span>

<span data-ttu-id="033cb-123">분류는 데이터를 범주로 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-123">Classification is used to categorize data into categories.</span></span>

![사기 탐지, 위험 완화 및 애플리케이션 심사를 포함한 이진 분류의 예를 보여 주는 다이어그램](media/binary-classification-examples.png)

![문서 및 제품 분류, 지원 티켓 라우팅 및 고객 이슈 우선 순위 지정을 포함한 다중 클래스 분류의 예](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a><span data-ttu-id="033cb-126">값 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-126">Value prediction</span></span>

<span data-ttu-id="033cb-127">회귀는 숫자를 예측하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-127">Regression is used to predict numbers.</span></span>

![가격 예측, 매출 예측 및 예측 유지 관리와 같은 회귀 예를 보여 주는 다이어그램](media/regression-examples.png)

#### <a name="image-classification"></a><span data-ttu-id="033cb-129">이미지 분류</span><span class="sxs-lookup"><span data-stu-id="033cb-129">Image classification</span></span>

<span data-ttu-id="033cb-130">이미지 분류는 다른 범주의 이미지를 식별하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-130">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="033cb-131">예를 들어 다른 종류의 지형이나 동물 또는 제조 결함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-131">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="033cb-132">이미지 집합이 있고 이미지를 여러 범주로 분류하려는 경우 이미지 분류 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-132">You can use the image classification scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="recommendation"></a><span data-ttu-id="033cb-133">권장</span><span class="sxs-lookup"><span data-stu-id="033cb-133">Recommendation</span></span>

<span data-ttu-id="033cb-134">추천 시나리오는 특정 사용자의 좋아요 및 싫어요가 다른 사용자와 얼마나 비슷한지에 따라 해당 사용자에 대한 추천 항목 목록을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-134">The recommendation scenario predicts a list of suggested items for a particular user, based on how similar their likes and dislikes are to other users'.</span></span>

<span data-ttu-id="033cb-135">사용자 집합과 "제품" 집합(예: 구매할 항목, 영화, 책 또는 TV 프로그램) 그리고 해당 제품에 대한 사용자 "평점"이 있는 경우 추천 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-135">You can use the recommendation scenario when you have a set of users and a set of "products", such as items to purchase, movies, books, or TV shows, along with a set of users' "ratings" of those products.</span></span>

## <a name="environment"></a><span data-ttu-id="033cb-136">환경</span><span class="sxs-lookup"><span data-stu-id="033cb-136">Environment</span></span>

<span data-ttu-id="033cb-137">컴퓨터에서 로컬로 또는 Azure 클라우드에서 기계 학습 모델을 학습시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-137">You can train your machine learning model locally on your machine or in the cloud on Azure.</span></span>

<span data-ttu-id="033cb-138">로컬로 학습시키는 경우 컴퓨터 리소스(CPU, 메모리 및 디스크)의 제약 조건 내에서 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-138">When you train locally, you work within the constraints of your computer resources (CPU, memory, and disk).</span></span> <span data-ttu-id="033cb-139">클라우드에서 학습시키는 경우에는 특히 대규모 데이터 집합의 시나리오 요구 사항에 맞게 리소스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-139">When you train in the cloud, you can scale up your resources to meet the demands of your scenario, especially for large datasets.</span></span>

<span data-ttu-id="033cb-140">로컬 학습은 모든 시나리오에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-140">Local training is supported for all scenarios.</span></span>

<span data-ttu-id="033cb-141">Azure 학습은 이미지 분류에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-141">Azure training is supported for Image Classification.</span></span>

## <a name="data"></a><span data-ttu-id="033cb-142">데이터</span><span class="sxs-lookup"><span data-stu-id="033cb-142">Data</span></span>

<span data-ttu-id="033cb-143">시나리오를 선택하면 모델 작성기에서 데이터 세트를 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-143">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="033cb-144">이 데이터는 시나리오에 가장 적합한 모델을 학습, 평가 및 선택하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-144">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![모델 작성기 단계를 보여 주는 다이어그램](media/model-builder-steps.png)

<span data-ttu-id="033cb-146">모델 작성기는 SQL 데이터베이스 형식 뿐만 아니라 .tsv, .csv, .txt 형식의 데이터 세트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-146">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="033cb-147">.txt 파일을 사용하는 경우 열을 `,`, `;` 또는 `/t`로 구분해야 하며 파일에는 머리글 행이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-147">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="033cb-148">데이터 세트가 이미지로 구성된 경우 지원되는 파일 형식은 `.jpg` 및 `.png`입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-148">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="033cb-149">자세한 내용은 [모델 작성기로 학습 데이터 로드](how-to-guides/load-data-model-builder.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="033cb-149">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="033cb-150">예측할 출력을 선택합니다(레이블).</span><span class="sxs-lookup"><span data-stu-id="033cb-150">Choose the output to predict (label)</span></span>

<span data-ttu-id="033cb-151">데이터 세트는 학습 예제의 행과 특성 열을 나열한 표입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-151">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="033cb-152">각 행에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-152">Each row has:</span></span>

- <span data-ttu-id="033cb-153">**레이블**(예측하려는 특성)</span><span class="sxs-lookup"><span data-stu-id="033cb-153">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="033cb-154">**기능**(레이블을 예측하기 위한 입력으로 사용되는 특성).</span><span class="sxs-lookup"><span data-stu-id="033cb-154">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="033cb-155">주택 가격 예측 시나리오의 경우 다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-155">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="033cb-156">집의 평방 피트</span><span class="sxs-lookup"><span data-stu-id="033cb-156">the square footage of the house</span></span>
- <span data-ttu-id="033cb-157">침실과 욕실의 수</span><span class="sxs-lookup"><span data-stu-id="033cb-157">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="033cb-158">우편 번호</span><span class="sxs-lookup"><span data-stu-id="033cb-158">the zip code</span></span>

<span data-ttu-id="033cb-159">이 레이블은 평방 피트, 침실, 욕실 값 및 우편 번호 행에 대해 기록한 주택 가격입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-159">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![크기 객실 우편 번호 및 가격 레이블로 구성된 기능을 갖춘 주택 가격 데이터의 행과 열을 보여주는 표](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="033cb-161">예제 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="033cb-161">Example datasets</span></span>

<span data-ttu-id="033cb-162">아직 사용자 고유의 데이터가 없는 경우 다음 데이터 세트 중 하나를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="033cb-162">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="033cb-163">시나리오</span><span class="sxs-lookup"><span data-stu-id="033cb-163">Scenario</span></span>|<span data-ttu-id="033cb-164">예제</span><span class="sxs-lookup"><span data-stu-id="033cb-164">Example</span></span>|<span data-ttu-id="033cb-165">데이터</span><span class="sxs-lookup"><span data-stu-id="033cb-165">Data</span></span>|<span data-ttu-id="033cb-166">레이블</span><span class="sxs-lookup"><span data-stu-id="033cb-166">Label</span></span>|<span data-ttu-id="033cb-167">기능</span><span class="sxs-lookup"><span data-stu-id="033cb-167">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="033cb-168">분류</span><span class="sxs-lookup"><span data-stu-id="033cb-168">Classification</span></span>|<span data-ttu-id="033cb-169">판매 변칙 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-169">Predict sales anomalies</span></span>|[<span data-ttu-id="033cb-170">제품 판매 데이터</span><span class="sxs-lookup"><span data-stu-id="033cb-170">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="033cb-171">제품 판매</span><span class="sxs-lookup"><span data-stu-id="033cb-171">Product Sales</span></span>|<span data-ttu-id="033cb-172">월</span><span class="sxs-lookup"><span data-stu-id="033cb-172">Month</span></span>|
||<span data-ttu-id="033cb-173">웹 사이트 댓글의 감정 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-173">Predict sentiment of website comments</span></span>|[<span data-ttu-id="033cb-174">웹 사이트 주석 데이터</span><span class="sxs-lookup"><span data-stu-id="033cb-174">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="033cb-175">레이블(부정적인 감정인 경우 0, 긍정적인 감정인 경우 1)</span><span class="sxs-lookup"><span data-stu-id="033cb-175">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="033cb-176">주석, 연도</span><span class="sxs-lookup"><span data-stu-id="033cb-176">Comment, Year</span></span>|
||<span data-ttu-id="033cb-177">사기성 신용 카드 거래 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-177">Predict fraudulent credit card transactions</span></span>|[<span data-ttu-id="033cb-178">신용 카드 데이터</span><span class="sxs-lookup"><span data-stu-id="033cb-178">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CCFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="033cb-179">클래스(사기일 경우 1, 그렇지 않으면 0)</span><span class="sxs-lookup"><span data-stu-id="033cb-179">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="033cb-180">수량, V1-V28(익명화된 기능)</span><span class="sxs-lookup"><span data-stu-id="033cb-180">Amount, V1-V28 (anonymized features)</span></span>|
||<span data-ttu-id="033cb-181">GitHub 리포지토리에서 문제 유형 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-181">Predict the type of issue in a GitHub repository</span></span>|[<span data-ttu-id="033cb-182">GitHub 문제 데이터</span><span class="sxs-lookup"><span data-stu-id="033cb-182">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="033cb-183">Area</span><span class="sxs-lookup"><span data-stu-id="033cb-183">Area</span></span>|<span data-ttu-id="033cb-184">제목, 설명</span><span class="sxs-lookup"><span data-stu-id="033cb-184">Title, Description</span></span>|
|<span data-ttu-id="033cb-185">값 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-185">Value prediction</span></span>|<span data-ttu-id="033cb-186">택시 요금 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-186">Predict taxi fare price</span></span>|[<span data-ttu-id="033cb-187">택시 요금 데이터</span><span class="sxs-lookup"><span data-stu-id="033cb-187">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="033cb-188">요금</span><span class="sxs-lookup"><span data-stu-id="033cb-188">Fare</span></span>|<span data-ttu-id="033cb-189">운행 시간, 거리</span><span class="sxs-lookup"><span data-stu-id="033cb-189">Trip time, distance</span></span>|
|<span data-ttu-id="033cb-190">이미지 분류</span><span class="sxs-lookup"><span data-stu-id="033cb-190">Image classification</span></span>|<span data-ttu-id="033cb-191">꽃의 범주 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-191">Predict the category of a flower</span></span> |[<span data-ttu-id="033cb-192">꽃 이미지</span><span class="sxs-lookup"><span data-stu-id="033cb-192">flower images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="033cb-193">꽃의 종류: 데이지, 민들레, 장미, 해바라기, 튤립</span><span class="sxs-lookup"><span data-stu-id="033cb-193">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="033cb-194">이미지 데이터 자체</span><span class="sxs-lookup"><span data-stu-id="033cb-194">The image data itself</span></span>|
|<span data-ttu-id="033cb-195">권장</span><span class="sxs-lookup"><span data-stu-id="033cb-195">Recommendation</span></span>|<span data-ttu-id="033cb-196">좋아하는 영화 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-196">Predict movies that someone will like</span></span>|[<span data-ttu-id="033cb-197">영화 평점</span><span class="sxs-lookup"><span data-stu-id="033cb-197">movie ratings</span></span>](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|<span data-ttu-id="033cb-198">사용자, 영화</span><span class="sxs-lookup"><span data-stu-id="033cb-198">Users, Movies</span></span>|<span data-ttu-id="033cb-199">등급</span><span class="sxs-lookup"><span data-stu-id="033cb-199">Ratings</span></span>|

## <a name="train"></a><span data-ttu-id="033cb-200">학습</span><span class="sxs-lookup"><span data-stu-id="033cb-200">Train</span></span>

<span data-ttu-id="033cb-201">시나리오, 환경, 데이터 및 레이블을 선택하면 모델 작성기가 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-201">Once you select your scenario, environment, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="033cb-202">학습이란?</span><span class="sxs-lookup"><span data-stu-id="033cb-202">What is training?</span></span>

<span data-ttu-id="033cb-203">학습은 모델 작성기가 시나리오에 대한 질문에 대답하는 방법을 모델에 알려주는 자동 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-203">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="033cb-204">학습하면 이전에 없었던 입력 데이터로 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-204">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="033cb-205">예를 들어 주택 가격을 예측하고 새 집이 시장에 나온다면 판매 가격을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-205">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="033cb-206">모델 작성기는 AutoML(자동 기계학습)을 사용하기 때문에 학습 중에 입력하거나 튜닝할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-206">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="033cb-207">얼마나 학습해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="033cb-207">How long should I train for?</span></span>

<span data-ttu-id="033cb-208">모델 작성기는 AutoML을 사용하여 여러 모델을 탐색하고 가장 잘 수행하는 모델을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-208">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="033cb-209">학습 기간이 길수록 AutoML에서 더 넓은 설정 범위로 더 많은 모델을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-209">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="033cb-210">아래 표는 로컬 컴퓨터에서 예제 데이터 세트에 대해 양호한 성능을 얻는 데 걸리는 평균 시간을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-210">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="033cb-211">데이터 세트 크기</span><span class="sxs-lookup"><span data-stu-id="033cb-211">Dataset size</span></span>|<span data-ttu-id="033cb-212">평균 학습 시간</span><span class="sxs-lookup"><span data-stu-id="033cb-212">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="033cb-213">0 - 10MB</span><span class="sxs-lookup"><span data-stu-id="033cb-213">0 - 10 MB</span></span>|<span data-ttu-id="033cb-214">10초</span><span class="sxs-lookup"><span data-stu-id="033cb-214">10 sec</span></span>|
|<span data-ttu-id="033cb-215">10 - 100MB</span><span class="sxs-lookup"><span data-stu-id="033cb-215">10 - 100 MB</span></span>|<span data-ttu-id="033cb-216">10분</span><span class="sxs-lookup"><span data-stu-id="033cb-216">10 min</span></span>|
|<span data-ttu-id="033cb-217">100 - 500MB</span><span class="sxs-lookup"><span data-stu-id="033cb-217">100 - 500 MB</span></span>|<span data-ttu-id="033cb-218">30분</span><span class="sxs-lookup"><span data-stu-id="033cb-218">30 min</span></span>|
|<span data-ttu-id="033cb-219">500 - 1GB</span><span class="sxs-lookup"><span data-stu-id="033cb-219">500 - 1 GB</span></span>|<span data-ttu-id="033cb-220">60분</span><span class="sxs-lookup"><span data-stu-id="033cb-220">60 min</span></span>|
|<span data-ttu-id="033cb-221">1GB+</span><span class="sxs-lookup"><span data-stu-id="033cb-221">1 GB+</span></span>|<span data-ttu-id="033cb-222">3시간 이상</span><span class="sxs-lookup"><span data-stu-id="033cb-222">3+ hours</span></span>|

<span data-ttu-id="033cb-223">이러한 숫자는 단지 안내일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-223">These numbers are a guide only.</span></span> <span data-ttu-id="033cb-224">정확한 학습 길이는 다음에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-224">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="033cb-225">모델에 대한 입력으로 사용되는 기능(열)의 수</span><span class="sxs-lookup"><span data-stu-id="033cb-225">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="033cb-226">열의 형식</span><span class="sxs-lookup"><span data-stu-id="033cb-226">the type of columns</span></span>
- <span data-ttu-id="033cb-227">ML 작업</span><span class="sxs-lookup"><span data-stu-id="033cb-227">the ML task</span></span>
- <span data-ttu-id="033cb-228">학습에 사용되는 컴퓨터의 CPU, 디스크 및 메모리 성능</span><span class="sxs-lookup"><span data-stu-id="033cb-228">the CPU, disk, and memory performance of the machine used for training</span></span>

<span data-ttu-id="033cb-229">일반적으로 100개 미만의 행을 데이터 세트로 사용하면 결과가 생성되지 않을 수 있고, 학습에 상당히 오랜 시간이 걸릴 수 있으므로 100개가 넘는 행을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-229">It's generally advised that you use more than 100 rows as datasets with less than that may not produce any results and may take a significantly longer time to train.</span></span>

## <a name="evaluate"></a><span data-ttu-id="033cb-230">Evaluate</span><span class="sxs-lookup"><span data-stu-id="033cb-230">Evaluate</span></span>

<span data-ttu-id="033cb-231">평가는 모델의 성능을 측정하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-231">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="033cb-232">모델 작성기는 학습된 모델을 통해 새 테스트 데이터를 사용하여 예측한 다음, 예측이 얼마나 올바른지를 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-232">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="033cb-233">모델 작성기는 학습 데이터를 학습 집합과 테스트 집합으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-233">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="033cb-234">학습 데이터(80%)는 모델을 학습하는 데 사용되며, 테스트 데이터(20%)는 모델을 평가하기 위해 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-234">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="033cb-235">모델 성능을 어떻게 이해할까요?</span><span class="sxs-lookup"><span data-stu-id="033cb-235">How do I understand my model performance?</span></span>

<span data-ttu-id="033cb-236">시나리오는 기계 학습 작업에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-236">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="033cb-237">각 ML 작업에는 고유한 평가 메트릭 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-237">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="value-prediction"></a><span data-ttu-id="033cb-238">값 예측</span><span class="sxs-lookup"><span data-stu-id="033cb-238">Value prediction</span></span>

<span data-ttu-id="033cb-239">값 예측 문제에 대한 기본 메트릭은 RSquared이고, RSquared 값의 범위는 0과 1 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-239">The default metric for value prediction problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="033cb-240">가능한 최고의 값은 1입니다. 즉, RSquared의 값이 1에 가까울수록 모델의 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-240">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="033cb-241">절대 손실, 제곱 손실 및 RMS 손실과 같이 보고된 다른 메트릭은 추가 메트릭이며 모델의 성능을 이해하고 다른 값 예측 모델과 비교하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-241">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other value prediction models.</span></span>

#### <a name="classification-2-categories"></a><span data-ttu-id="033cb-242">분류(2개 범주)</span><span class="sxs-lookup"><span data-stu-id="033cb-242">Classification (2 categories)</span></span>

<span data-ttu-id="033cb-243">분류 문제에 대한 기본 메트릭은 정확도입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-243">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="033cb-244">정확도는 모델이 테스트 데이터 세트에 대해 내리는 정확한 예측 비율을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-244">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="033cb-245">100% 또는 1.0에 가까울수록 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-245">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="033cb-246">참 긍정 비율과 거짓 긍정 비율을 측정하는 AUC(곡선 아래의 영역)와 같은 보고된 기타 메트릭은 허용 가능한 모델에 대해 0.50보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-246">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="033cb-247">F1 점수와 같은 추가 메트릭을 사용하여 전체 정밀도와 재현율 간의 균형을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-247">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="classification-3-categories"></a><span data-ttu-id="033cb-248">분류(3개 이상 범주)</span><span class="sxs-lookup"><span data-stu-id="033cb-248">Classification (3+ categories)</span></span>

<span data-ttu-id="033cb-249">다중 클래스 분류에 대한 기본 메트릭은 Micro 정확도입니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-249">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="033cb-250">Micro 정확도는 100% 또는 1.0에 가까울수록 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-250">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="033cb-251">다중 클래스 분류에 대한 또 다른 중요한 메트릭은 Macro 정확도입니다. Micro 정확도와 마찬가지로 1.0에 가까울수록 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-251">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="033cb-252">이러한 두 가지 유형의 정확도를 고려하는 올바른 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-252">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="033cb-253">Micro 정확도: 들어오는 티켓이 올바른 팀으로 분류되는 빈도</span><span class="sxs-lookup"><span data-stu-id="033cb-253">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="033cb-254">Macro 정확도: 평균 팀의 경우 들어오는 티켓이 해당 팀에 올바르게 분류된 빈도</span><span class="sxs-lookup"><span data-stu-id="033cb-254">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="033cb-255">평가 메트릭에 대한 자세한 내용</span><span class="sxs-lookup"><span data-stu-id="033cb-255">More information on evaluation metrics</span></span>

<span data-ttu-id="033cb-256">자세한 내용은 [모델 평가 메트릭](resources/metrics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="033cb-256">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="033cb-257">개선</span><span class="sxs-lookup"><span data-stu-id="033cb-257">Improve</span></span>

<span data-ttu-id="033cb-258">모델 성능 점수가 원하는 만큼 좋지 않은 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-258">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="033cb-259">더 긴 시간 동안 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-259">Train for a longer period of time.</span></span> <span data-ttu-id="033cb-260">시간이 지날수록 자동화된 기계 학습 엔진은 더 많은 알고리즘과 설정으로 실험합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-260">With more time, the automated machine learning engine experiments with more algorithms and settings.</span></span>

- <span data-ttu-id="033cb-261">더 많은 데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-261">Add more data.</span></span> <span data-ttu-id="033cb-262">경우에 따라 데이터의 양이 고품질 기계 학습 모델을 학습시키기에 충분하지 않을 수도 있습니다. 데이터 세트에 예제 수가 적은 경우 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-262">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.This is especially true with datasets that have a small number of examples.</span></span>

- <span data-ttu-id="033cb-263">데이터의 균형을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-263">Balance your data.</span></span> <span data-ttu-id="033cb-264">분류 작업의 경우 학습 집합이 범주 전반에 걸쳐 균형을 유지하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-264">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="033cb-265">예를 들어 100개의 학습 예제에 대한 네 개의 클래스가 있고, 90개의 레코드에 두 개의 첫 번째 클래스(tag1 및 tag2)가 사용되지만 다른 두 개 클래스(tag3 및 tag4)가 나머지 10개의 레코드에만 사용되는 경우 균형 있는 데이터가 부족하여 모델이 tag3 또는 tag4를 올바르게 예측하는 데 어려움을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-265">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="033cb-266">코드</span><span class="sxs-lookup"><span data-stu-id="033cb-266">Code</span></span>

<span data-ttu-id="033cb-267">평가 단계 후 모델 작성기는 모델 파일 및 모델을 애플리케이션에 추가하는 데 사용할 수 있는 코드를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-267">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="033cb-268">ML.NET 모델은 zip 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-268">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="033cb-269">모델을 로드하고 사용하는 코드는 솔루션에는 새 프로젝트로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-269">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="033cb-270">또한 모델 작성기는 실행 중인 모델을 보기 위해 실행할 수 있는 샘플 콘솔 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-270">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="033cb-271">또한 모델 작성기는 모델을 생성하는 데 사용되는 단계를 이해할 수 있도록 모델을 생성하는 코드를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-271">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="033cb-272">모델 학습 코드를 사용하여 새 데이터로 모델을 다시 학습할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="033cb-272">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="033cb-273">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="033cb-273">What's next?</span></span>

<span data-ttu-id="033cb-274">모델 작성기 Visual Studio 확장 [설치](how-to-guides/install-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="033cb-274">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="033cb-275">[가격 예측 또는 모든 회귀 시나리오](tutorials/predict-prices-with-model-builder.md) 시도</span><span class="sxs-lookup"><span data-stu-id="033cb-275">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>

---
title: 모델 작성기란 무엇이며 어떻게 작동하나요?
description: ML.NET 모델 작성기를 사용하여 기계 학습 모델을 자동으로 학습하는 방법
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77fe56dba3532617ad9fb0c89bfaac7c8e031ce7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971520"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="75863-103">모델 작성기란 무엇이며 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="75863-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="75863-104">ML.NET 모델 작성기는 사용자 지정 기계 학습 모델을 빌드, 학습 및 배포하기 위한 직관적인 그래픽 Visual Studio 확장 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="75863-105">모델 작성기는 AutoML(자동 기계 학습)을 사용하여 다양한 기계 학습 알고리즘과 설정을 탐색하여 시나리오에 가장 적합한 것을 찾아냅니다.</span><span class="sxs-lookup"><span data-stu-id="75863-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="75863-106">모델 작성기를 사용하기 위해 기계 학습 전문 지식이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="75863-107">필요한 것은 약간의 데이터와 해결해야 할 문제뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="75863-108">모델 작성기는 .NET 애플리케이션에 모델을 추가하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![모델 작성기 Visual Studio 확장 사용자 인터페이스 애니메이션](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="75863-110">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="75863-111">시나리오</span><span class="sxs-lookup"><span data-stu-id="75863-111">Scenarios</span></span>

<span data-ttu-id="75863-112">애플리케이션에 대한 기계 학습 모델을 생성하기 위해 모델 작성기에 다양한 시나리오를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="75863-113">시나리오는 데이터를 사용하여 수행할 예측 유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="75863-114">예:</span><span class="sxs-lookup"><span data-stu-id="75863-114">For example:</span></span>

- <span data-ttu-id="75863-115">과거 판매 데이터를 기반으로 향후 제품 판매량 예측</span><span class="sxs-lookup"><span data-stu-id="75863-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="75863-116">고객 리뷰에 따라 감정을 긍정 또는 부정으로 분류</span><span class="sxs-lookup"><span data-stu-id="75863-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="75863-117">은행 트랜잭션이 사기인지 여부를 검색</span><span class="sxs-lookup"><span data-stu-id="75863-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="75863-118">고객 피드백 문제를 회사의 올바른 팀에 전달</span><span class="sxs-lookup"><span data-stu-id="75863-118">route customer feedback issues to the correct team in your company</span></span>

## <a name="choose-a-model-type"></a><span data-ttu-id="75863-119">모델 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-119">Choose a model type</span></span>

<span data-ttu-id="75863-120">모델 작성기에서는 기계 학습 모델 형식을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-120">In Model Builder, you need to select a machine learning model type.</span></span> <span data-ttu-id="75863-121">모델 형식은 수행하려는 예측의 정렬에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="75863-121">The type of model depends on what sort of prediction you are trying to make.</span></span>

<span data-ttu-id="75863-122">숫자를 예측하는 시나리오의 경우 기계 학습 모델 형식을 `regression`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-122">For scenarios that predict a number, the machine learning model type is called `regression`.</span></span>

<span data-ttu-id="75863-123">범주를 예측하는 시나리오의 경우 모델 형식은 `classification`입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-123">For scenarios that predict a category, the model type is `classification`.</span></span> <span data-ttu-id="75863-124">두 가지 형식의 분류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-124">There are two types of classification:</span></span>

- <span data-ttu-id="75863-125">두 개의 범주만 있는 경우: `binary classification`.</span><span class="sxs-lookup"><span data-stu-id="75863-125">where there are only 2 categories: `binary classification`.</span></span>
- <span data-ttu-id="75863-126">세 개 이상의 범주가 있는 경우: `multiclass classification`.</span><span class="sxs-lookup"><span data-stu-id="75863-126">where there are three or more categories: `multiclass classification`.</span></span>

### <a name="which-model-type-is-right-for-me"></a><span data-ttu-id="75863-127">내게 적합한 모델 형식은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="75863-127">Which model type is right for me?</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="75863-128">범주 예측(두 개의 범주만 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="75863-128">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="75863-129">이진 분류는 데이터를 두 범주(예/아니요, 통과/실패, 참/거짓 긍정/부정)로 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-129">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![사기 탐지, 위험 완화 및 애플리케이션 심사를 포함한 이진 분류의 예를 보여 주는 다이어그램](media/binary-classification-examples.png)

<span data-ttu-id="75863-131">감정 분석은 고객 피드백에 대한 긍정 또는 부정 감정을 예측하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-131">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="75863-132">이진 분류 모델 형식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-132">It is an example of a binary classification model type.</span></span>

<span data-ttu-id="75863-133">시나리오에서 두 범주로 분류해야 하는 경우, 이 템플릿을 사용자 고유의 데이터 세트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-133">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="75863-134">범주 예측(세 개 이상의 범주가 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="75863-134">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="75863-135">다중 클래스 분류는 데이터를 세 개 이상의 클래스로 분류하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-135">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![문서 및 제품 분류, 지원 티켓 라우팅 및 고객 이슈 우선 순위 지정을 포함한 다중 클래스 분류의 예](media/multiclass-classification-examples.png)

<span data-ttu-id="75863-137">문제 분류는 문제 제목 및 설명을 사용하여 고객 피드백(예: GitHub) 문제를 분류하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-137">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="75863-138">다중 클래스 분류 모델 형식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-138">It is an example of the multi-class classification model type.</span></span>

<span data-ttu-id="75863-139">데이터를 세 가지 이상의 범주로 분류하려는 경우 시나리오에 대한 문제 분류 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-139">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="75863-140">숫자 예측</span><span class="sxs-lookup"><span data-stu-id="75863-140">Predict a number</span></span>

<span data-ttu-id="75863-141">회귀는 숫자를 예측하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-141">Regression is used to predict numbers.</span></span>

![가격 예측, 매출 예측 및 예측 유지 관리와 같은 회귀 예를 보여 주는 다이어그램](media/regression-examples.png)

<span data-ttu-id="75863-143">가격 예측은 집의 위치, 크기 및 기타 특성을 통해 집 가격을 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-143">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="75863-144">회귀 모델 형식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-144">It is an example of a regression model type.</span></span>

<span data-ttu-id="75863-145">사용자 고유의 데이터 세트를 사용하여 숫자 값을 예측하려는 경우 시나리오에 가격 예측 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-145">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-model-type"></a><span data-ttu-id="75863-146">사용자 지정 시나리오(모델 형식 선택)</span><span class="sxs-lookup"><span data-stu-id="75863-146">Custom scenario (choose your model type)</span></span>

<span data-ttu-id="75863-147">사용자 지정 시나리오를 사용하여 모델 형식을 수동으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-147">The custom scenario allows you to manually choose your model type.</span></span>

## <a name="data"></a><span data-ttu-id="75863-148">데이터</span><span class="sxs-lookup"><span data-stu-id="75863-148">Data</span></span>

<span data-ttu-id="75863-149">모델 형식을 선택하면 모델 작성기에서 데이터 세트를 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-149">Once you have chosen your model type, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="75863-150">이 데이터는 시나리오에 가장 적합한 모델을 학습, 평가 및 선택하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-150">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![모델 작성기 단계를 보여 주는 다이어그램](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="75863-152">예측할 출력을 선택합니다(레이블).</span><span class="sxs-lookup"><span data-stu-id="75863-152">Choose the output to predict (label)</span></span>

<span data-ttu-id="75863-153">데이터 세트는 학습 예제의 행과 특성 열을 나열한 표입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-153">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="75863-154">각 행에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-154">Each row has:</span></span>

- <span data-ttu-id="75863-155">**레이블**(예측하려는 특성)</span><span class="sxs-lookup"><span data-stu-id="75863-155">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="75863-156">**기능**(레이블을 예측하기 위한 입력으로 사용되는 특성).</span><span class="sxs-lookup"><span data-stu-id="75863-156">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="75863-157">주택 가격 예측 시나리오의 경우 다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-157">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="75863-158">집의 평방 피트</span><span class="sxs-lookup"><span data-stu-id="75863-158">the square footage of the house</span></span>
- <span data-ttu-id="75863-159">침실과 욕실의 수</span><span class="sxs-lookup"><span data-stu-id="75863-159">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="75863-160">우편 번호</span><span class="sxs-lookup"><span data-stu-id="75863-160">the zip code</span></span>

<span data-ttu-id="75863-161">이 레이블은 평방 피트, 침실, 욕실 값 및 우편 번호 행에 대해 기록한 주택 가격입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-161">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![크기 객실 우편 번호 및 가격 레이블로 구성된 기능을 갖춘 주택 가격 데이터의 행과 열을 보여주는 표](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="75863-163">예제 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="75863-163">Example datasets</span></span>

<span data-ttu-id="75863-164">아직 사용자 고유의 데이터가 없는 경우 다음 데이터 세트 중 하나를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="75863-164">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="75863-165">시나리오</span><span class="sxs-lookup"><span data-stu-id="75863-165">Scenario</span></span>|<span data-ttu-id="75863-166">모델 형식</span><span class="sxs-lookup"><span data-stu-id="75863-166">Model Type</span></span>|<span data-ttu-id="75863-167">데이터</span><span class="sxs-lookup"><span data-stu-id="75863-167">Data</span></span>|<span data-ttu-id="75863-168">레이블</span><span class="sxs-lookup"><span data-stu-id="75863-168">Label</span></span>|<span data-ttu-id="75863-169">기능</span><span class="sxs-lookup"><span data-stu-id="75863-169">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="75863-170">가격 예측</span><span class="sxs-lookup"><span data-stu-id="75863-170">Price prediction</span></span>|<span data-ttu-id="75863-171">회귀</span><span class="sxs-lookup"><span data-stu-id="75863-171">regression</span></span>|[<span data-ttu-id="75863-172">택시 요금 데이터</span><span class="sxs-lookup"><span data-stu-id="75863-172">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="75863-173">요금</span><span class="sxs-lookup"><span data-stu-id="75863-173">Fare</span></span>|<span data-ttu-id="75863-174">운행 시간, 거리</span><span class="sxs-lookup"><span data-stu-id="75863-174">Trip time, distance</span></span>|
|<span data-ttu-id="75863-175">변칙 검색</span><span class="sxs-lookup"><span data-stu-id="75863-175">Anomaly detection</span></span>|<span data-ttu-id="75863-176">이진 분류</span><span class="sxs-lookup"><span data-stu-id="75863-176">binary classification</span></span>|[<span data-ttu-id="75863-177">제품 판매 데이터</span><span class="sxs-lookup"><span data-stu-id="75863-177">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="75863-178">제품 판매</span><span class="sxs-lookup"><span data-stu-id="75863-178">Product Sales</span></span>|<span data-ttu-id="75863-179">월</span><span class="sxs-lookup"><span data-stu-id="75863-179">Month</span></span>|
|<span data-ttu-id="75863-180">감정 분석</span><span class="sxs-lookup"><span data-stu-id="75863-180">Sentiment analysis</span></span>|<span data-ttu-id="75863-181">이진 분류</span><span class="sxs-lookup"><span data-stu-id="75863-181">binary classification</span></span>|[<span data-ttu-id="75863-182">웹 사이트 주석 데이터</span><span class="sxs-lookup"><span data-stu-id="75863-182">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="75863-183">레이블(부정적인 감정인 경우 0, 긍정적인 감정인 경우 1)</span><span class="sxs-lookup"><span data-stu-id="75863-183">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="75863-184">주석, 연도</span><span class="sxs-lookup"><span data-stu-id="75863-184">Comment, Year</span></span>|
|<span data-ttu-id="75863-185">부정 행위 감지</span><span class="sxs-lookup"><span data-stu-id="75863-185">Fraud detection</span></span>|<span data-ttu-id="75863-186">이진 분류</span><span class="sxs-lookup"><span data-stu-id="75863-186">binary classification</span></span>|[<span data-ttu-id="75863-187">신용 카드 데이터</span><span class="sxs-lookup"><span data-stu-id="75863-187">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="75863-188">클래스(사기일 경우 1, 그렇지 않으면 0)</span><span class="sxs-lookup"><span data-stu-id="75863-188">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="75863-189">수량, V1-V28(익명화된 기능)</span><span class="sxs-lookup"><span data-stu-id="75863-189">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="75863-190">텍스트 분류</span><span class="sxs-lookup"><span data-stu-id="75863-190">Text classification</span></span>|<span data-ttu-id="75863-191">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="75863-191">multiclass classification</span></span>|[<span data-ttu-id="75863-192">GitHub 문제 데이터</span><span class="sxs-lookup"><span data-stu-id="75863-192">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="75863-193">영역</span><span class="sxs-lookup"><span data-stu-id="75863-193">Area</span></span>|<span data-ttu-id="75863-194">제목, 설명</span><span class="sxs-lookup"><span data-stu-id="75863-194">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="75863-195">학습</span><span class="sxs-lookup"><span data-stu-id="75863-195">Train</span></span>

<span data-ttu-id="75863-196">시나리오, 데이터 및 레이블을 선택하면 모델 작성기가 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-196">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="75863-197">학습이란?</span><span class="sxs-lookup"><span data-stu-id="75863-197">What is training?</span></span>

<span data-ttu-id="75863-198">학습은 모델 작성기가 시나리오에 대한 질문에 대답하는 방법을 모델에 알려주는 자동 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-198">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="75863-199">학습하면 이전에 없었던 입력 데이터로 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-199">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="75863-200">예를 들어 주택 가격을 예측하고 새 집이 시장에 나온다면 판매 가격을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-200">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="75863-201">모델 작성기는 AutoML(자동 기계학습)을 사용하기 때문에 학습 중에 입력하거나 튜닝할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-201">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

## <a name="evaluate"></a><span data-ttu-id="75863-202">Evaluate</span><span class="sxs-lookup"><span data-stu-id="75863-202">Evaluate</span></span>

<span data-ttu-id="75863-203">평가는 학습된 모델을 통해 새 테스트 데이터를 사용하여 예측한 다음, 예측이 얼마나 올바른지를 측정하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="75863-203">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="75863-204">모델 작성기는 학습 데이터를 학습 집합과 테스트 집합으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-204">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="75863-205">학습 데이터(80%)는 모델을 학습하는 데 사용되며, 테스트 데이터(20%)는 모델을 평가하기 위해 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-205">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> <span data-ttu-id="75863-206">모델 작성기는 메트릭을 사용하여 모델이 얼마나 효과적인지 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-206">Model Builder uses metrics to measure how good the model is.</span></span> <span data-ttu-id="75863-207">사용되는 특정 메트릭은 모델 형식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="75863-207">The specific metrics used are dependent on the type of model.</span></span> <span data-ttu-id="75863-208">자세한 내용은 [모델 평가 메트릭](resources/metrics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75863-208">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="75863-209">개선</span><span class="sxs-lookup"><span data-stu-id="75863-209">Improve</span></span>

<span data-ttu-id="75863-210">모델 성능 점수가 원하는 만큼 좋지 않은 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-210">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="75863-211">더 긴 시간 동안 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-211">Train for a longer period of time.</span></span> <span data-ttu-id="75863-212">시간이 지날수록 자동화된 기계 학습 엔진은 더 많은 알고리즘과 설정을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-212">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="75863-213">더 많은 데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-213">Add more data.</span></span> <span data-ttu-id="75863-214">경우에 따라 데이터의 양이 고품질 기계 학습 모델을 학습하기에 충분하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-214">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="75863-215">데이터의 균형을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-215">Balance your data.</span></span> <span data-ttu-id="75863-216">분류 작업의 경우 학습 집합이 범주 전반에 걸쳐 균형을 유지하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-216">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="75863-217">예를 들어 100개의 학습 예제에 대한 네 개의 클래스가 있고, 90개의 레코드에 두 개의 첫 번째 클래스(tag1 및 tag2)가 사용되지만 다른 두 개 클래스(tag3 및 tag4)가 나머지 10개의 레코드에만 사용되는 경우 균형 있는 데이터가 부족하여 모델이 tag3 또는 tag4를 올바르게 예측하는 데 어려움을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-217">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="75863-218">코드</span><span class="sxs-lookup"><span data-stu-id="75863-218">Code</span></span>

<span data-ttu-id="75863-219">평가 단계 후 모델 작성기는 모델 파일 및 모델을 애플리케이션에 추가하는 데 사용할 수 있는 코드를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-219">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="75863-220">ML.NET 모델은 zip 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-220">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="75863-221">모델을 로드하고 사용하는 코드는 솔루션에는 새 프로젝트로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="75863-221">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="75863-222">또한 모델 작성기는 실행 중인 모델을 보기 위해 실행할 수 있는 샘플 콘솔 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-222">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="75863-223">또한 모델 작성기는 모델을 생성하는 데 사용되는 단계를 이해할 수 있도록 모델을 생성하는 코드를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="75863-223">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="75863-224">모델 학습 코드를 사용하여 새 데이터로 모델을 다시 학습할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75863-224">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="75863-225">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="75863-225">What's next?</span></span>

<span data-ttu-id="75863-226">모델 작성기 Visual Studio 확장 [설치](how-to-guides/install-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="75863-226">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="75863-227">[가격 예측 또는 모든 회귀 시나리오](tutorials/predict-prices-with-model-builder.md) 시도</span><span class="sxs-lookup"><span data-stu-id="75863-227">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>

---
title: 모델 작성기란 무엇이며 어떻게 작동하나요?
description: ML.NET 모델 작성기를 사용하여 기계 학습 모델을 자동으로 학습하는 방법
author: natke
ms.date: 06/26/2019
ms.custom: overview
ms.openlocfilehash: 6f5bbe3c389e3ca42550a48ef3e6edbc963ac2e9
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410591"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="ec968-103">모델 작성기란 무엇이며 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="ec968-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="ec968-104">ML.NET 모델 작성기는 사용자 지정 기계 학습 모델을 빌드, 학습 및 배포하기 위한 이해하기 쉬운 그래픽 Visual Studio 확장 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-104">ML.NET Model Builder is an easy-to-understand graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span> 

<span data-ttu-id="ec968-105">모델 작성기는 AutoML(자동 기계 학습)을 사용하여 다양한 기계 학습 알고리즘과 설정을 탐색하여 시나리오에 가장 적합한 것을 찾아냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="ec968-106">모델 작성기를 사용하기 위해 기계 학습 전문 지식이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="ec968-107">필요한 것은 약간의 데이터와 해결해야 할 문제뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="ec968-108">모델 작성기는 .NET 애플리케이션에 모델을 추가하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![모델 작성기 Visual Studio 확장 사용자 인터페이스 애니메이션](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="ec968-110">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="ec968-111">시나리오</span><span class="sxs-lookup"><span data-stu-id="ec968-111">Scenarios</span></span>

<span data-ttu-id="ec968-112">애플리케이션에 대한 기계 학습 모델을 생성하기 위해 모델 작성기에 다양한 시나리오를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="ec968-113">시나리오는 데이터에서 수행할 예측 유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-113">A scenario is a description of the type of prediction you want to make on your data.</span></span> <span data-ttu-id="ec968-114">예:</span><span class="sxs-lookup"><span data-stu-id="ec968-114">For example:</span></span>
- <span data-ttu-id="ec968-115">과거 판매 데이터를 기반으로 향후 제품 판매량 예측</span><span class="sxs-lookup"><span data-stu-id="ec968-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="ec968-116">고객 리뷰에 따라 감정을 긍정 또는 부정으로 분류</span><span class="sxs-lookup"><span data-stu-id="ec968-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="ec968-117">은행 트랜잭션이 사기인지 여부를 검색</span><span class="sxs-lookup"><span data-stu-id="ec968-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="ec968-118">고객 피드백 문제를 회사의 올바른 팀에 전달</span><span class="sxs-lookup"><span data-stu-id="ec968-118">route customer feedback issues to the correct team in your company</span></span>

<span data-ttu-id="ec968-119">모델 작성기에서 시나리오를 [ML.NET 작업](resources/tasks.md)에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-119">In Model Builder, you need to map your scenario onto an [ML.NET task](resources/tasks.md).</span></span> <span data-ttu-id="ec968-120">모델 작성기를 **회귀**(숫자 예측) 및 **분류**(범주 예측)에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-120">You can use Model Builder for **regression** (predicting numbers) and **classification** (predicting categories).</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="ec968-121">어떤 기계 학습 시나리오가 나에게 적합한가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-121">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="ec968-122">모델 작성기는 감정 분석, 문제 분류, 가격 예측 및 사용자 지정 시나리오를 위한 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-122">Model Builder comes with templates for sentiment analysis, issue classification, price prediction, and custom scenarios.</span></span> <span data-ttu-id="ec968-123">이러한 템플릿은 특정 ML.NET 시나리오의 시작점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-123">These templates can be used as a starting point for your specific ML.NET scenario.</span></span>

#### <a name="sentiment-analysis-binary-classification"></a><span data-ttu-id="ec968-124">감정 분석(이진 분류)</span><span class="sxs-lookup"><span data-stu-id="ec968-124">Sentiment analysis (binary classification)</span></span>

<span data-ttu-id="ec968-125">감정 분석은 고객 피드백에 대한 긍정 또는 부정 감정을 예측하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-125">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="ec968-126">이진 분류 작업의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-126">It is an example of the binary classification task.</span></span>

<span data-ttu-id="ec968-127">이진 분류는 데이터를 두 클래스(예/아니요, 통과/실패, 참/거짓 긍정/부정)로 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-127">Binary classification is used to categorize data into two classes (yes/no; pass/fail; true/false; positive/negative).</span></span> <span data-ttu-id="ec968-128">다음과 같은 질문에 답변하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-128">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="ec968-129">이 이메일은 스팸인가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-129">Is this email spam?</span></span> <span data-ttu-id="ec968-130">(스팸 검색)</span><span class="sxs-lookup"><span data-stu-id="ec968-130">(spam detection)</span></span>
- <span data-ttu-id="ec968-131">어느 지원자가 멤버 자격이 있나요?</span><span class="sxs-lookup"><span data-stu-id="ec968-131">Which applicants may be eligible for membership?</span></span> <span data-ttu-id="ec968-132">(애플리케이션 검사)</span><span class="sxs-lookup"><span data-stu-id="ec968-132">(application screening)</span></span>
- <span data-ttu-id="ec968-133">어느 계정이 제때 청구서를 지불하지 못하나요?</span><span class="sxs-lookup"><span data-stu-id="ec968-133">Which accounts may not pay their invoices on time?</span></span> <span data-ttu-id="ec968-134">(위험 완화)</span><span class="sxs-lookup"><span data-stu-id="ec968-134">(risk mitigation)</span></span>
- <span data-ttu-id="ec968-135">이 신용 카드 거래는 사기인가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-135">Is this credit card transaction fraudulent?</span></span> <span data-ttu-id="ec968-136">(부정 행위 감지)</span><span class="sxs-lookup"><span data-stu-id="ec968-136">(fraud detection)</span></span>

<span data-ttu-id="ec968-137">시나리오에서 두 범주로 분류해야 하는 경우, 이 템플릿을 사용자 고유의 데이터 세트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-137">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>
 
#### <a name="issue-classification-multiclass-classification"></a><span data-ttu-id="ec968-138">문제 분류(다중 클래스 분류)</span><span class="sxs-lookup"><span data-stu-id="ec968-138">Issue classification (multiclass classification)</span></span>

<span data-ttu-id="ec968-139">문제 분류는 문제 제목 및 설명을 사용하여 고객 피드백(예: GitHub) 문제를 분류하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-139">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="ec968-140">다중 클래스 분류 작업의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-140">It is an example of the multi-class classification task.</span></span>

<span data-ttu-id="ec968-141">다중 클래스 분류는 데이터를 세 개 이상의 클래스로 분류하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-141">Multiclass classification can be used to categorize data into three or more classes.</span></span> <span data-ttu-id="ec968-142">다음과 같은 질문에 답변하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-142">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="ec968-143">지원 티켓을 어느 부서에 라우팅해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="ec968-143">To which department should I route a support ticket?</span></span> <span data-ttu-id="ec968-144">(지원 티켓 라우팅)</span><span class="sxs-lookup"><span data-stu-id="ec968-144">(support ticket routing)</span></span>
- <span data-ttu-id="ec968-145">고객 문제의 우선순위는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-145">What is the priority of a customer issue?</span></span> <span data-ttu-id="ec968-146">(고객 문제 우선순위 지정)</span><span class="sxs-lookup"><span data-stu-id="ec968-146">(customer issue prioritization)</span></span>
- <span data-ttu-id="ec968-147">제품은 어떤 범주에 속하나요?</span><span class="sxs-lookup"><span data-stu-id="ec968-147">What category does a product belong to?</span></span> <span data-ttu-id="ec968-148">(제품 분류)</span><span class="sxs-lookup"><span data-stu-id="ec968-148">(product classification)</span></span>
- <span data-ttu-id="ec968-149">어떤 유형의 문서인가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-149">What type of document?</span></span> <span data-ttu-id="ec968-150">(문서/이메일 분류)</span><span class="sxs-lookup"><span data-stu-id="ec968-150">(document/email classification)</span></span>

<span data-ttu-id="ec968-151">데이터를 세 가지 이상의 범주로 분류하려는 경우 시나리오에 대한 문제 분류 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-151">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="price-prediction-regression"></a><span data-ttu-id="ec968-152">가격 예측(회귀)</span><span class="sxs-lookup"><span data-stu-id="ec968-152">Price prediction (regression)</span></span>

<span data-ttu-id="ec968-153">가격 예측은 집의 위치, 크기 및 기타 특성을 통해 집 가격을 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-153">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="ec968-154">회귀 작업의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-154">It is an example of the regression task.</span></span>

<span data-ttu-id="ec968-155">회귀는 숫자를 예측하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-155">Regression is used to predict numbers.</span></span> <span data-ttu-id="ec968-156">다음과 같은 질문에 답변하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-156">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="ec968-157">집의 판매 가격은?</span><span class="sxs-lookup"><span data-stu-id="ec968-157">What price will a house sell for?</span></span> <span data-ttu-id="ec968-158">(가격 예측)</span><span class="sxs-lookup"><span data-stu-id="ec968-158">(price prediction)</span></span>
- <span data-ttu-id="ec968-159">기계 부품에 유지 관리가 필요한 시간은 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-159">After how much time will a mechanical part require maintenance?</span></span> <span data-ttu-id="ec968-160">(예측 유지 관리)</span><span class="sxs-lookup"><span data-stu-id="ec968-160">(predictive maintenance)</span></span>
- <span data-ttu-id="ec968-161">이 건조기의 수분 함량은 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-161">What is the moisture content in this dryer?</span></span> <span data-ttu-id="ec968-162">(머신 모니터링)</span><span class="sxs-lookup"><span data-stu-id="ec968-162">(machine monitoring)</span></span>
- <span data-ttu-id="ec968-163">이 지역의 연간 총 판매량은 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="ec968-163">What will the total annual sales for this region be?</span></span> <span data-ttu-id="ec968-164">(판매 예측)</span><span class="sxs-lookup"><span data-stu-id="ec968-164">(sales forecasting)</span></span>

<span data-ttu-id="ec968-165">사용자 고유의 데이터 세트를 사용하여 숫자 값을 예측하려는 경우 시나리오에 가격 예측 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-165">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-task"></a><span data-ttu-id="ec968-166">사용자 지정 시나리오(작업 선택)</span><span class="sxs-lookup"><span data-stu-id="ec968-166">Custom scenario (choose your task)</span></span>

<span data-ttu-id="ec968-167">사용자 지정 시나리오를 사용하면 자신의 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-167">The custom scenario allows you to choose your own task.</span></span> <span data-ttu-id="ec968-168">문제에 가장 적합한 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-168">Pick the scenario that makes the most sense for your problem.</span></span>

<span data-ttu-id="ec968-169">사용자 지정 시나리오를 통해 자신의 기계 학습 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-169">The custom scenario allows you to choose your own machine learning task.</span></span> <span data-ttu-id="ec968-170">이전 템플릿에서 기계 학습 작업은 이진 분류, 다중 클래스 분류 또는 회귀 시나리오로 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-170">In the previous templates, the machine learning task was fixed to the scenario: binary classification, multi-class classification, or regression.</span></span> <span data-ttu-id="ec968-171">이 템플릿에서 데이터에 사용할 ML 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-171">In this template, you can choose the ML task you want to use on your data.</span></span>

## <a name="data"></a><span data-ttu-id="ec968-172">데이터</span><span class="sxs-lookup"><span data-stu-id="ec968-172">Data</span></span>

<span data-ttu-id="ec968-173">시나리오를 작업에 매핑하면 모델 작성기에서 데이터 세트를 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-173">Once you have mapped your scenario onto a task, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="ec968-174">이 데이터는 시나리오에 가장 적합한 모델을 학습, 평가 및 선택하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-174">The data is used to train, evaluate, and choose the best model for your scenario.</span></span> <span data-ttu-id="ec968-175">예측하려는 출력도 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-175">You also need to choose the output you want to predict.</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="ec968-176">예측할 출력을 선택합니다(레이블).</span><span class="sxs-lookup"><span data-stu-id="ec968-176">Choose the output to predict (label)</span></span>

<span data-ttu-id="ec968-177">데이터 세트는 학습 예제의 행과 특성 열을 나열한 표입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-177">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="ec968-178">각 행에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-178">Each row has:</span></span>
- <span data-ttu-id="ec968-179">**레이블**(예측하려는 특성)</span><span class="sxs-lookup"><span data-stu-id="ec968-179">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="ec968-180">**기능**(레이블을 예측하기 위한 입력으로 사용되는 특성).</span><span class="sxs-lookup"><span data-stu-id="ec968-180">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="ec968-181">주택 가격 예측 시나리오의 경우 다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-181">For the house-price prediction scenario, the features could be:</span></span>
- <span data-ttu-id="ec968-182">집의 평방 피트</span><span class="sxs-lookup"><span data-stu-id="ec968-182">the square footage of the house</span></span>
- <span data-ttu-id="ec968-183">침실과 욕실의 수</span><span class="sxs-lookup"><span data-stu-id="ec968-183">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="ec968-184">우편 번호</span><span class="sxs-lookup"><span data-stu-id="ec968-184">the zip code</span></span>

<span data-ttu-id="ec968-185">이 레이블은 평방 피트, 침실, 욕실 값 및 우편 번호 행에 대해 기록한 주택 가격입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-185">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![크기 객실 우편 번호 및 가격 레이블로 구성된 기능을 갖춘 주택 가격 데이터의 행과 열을 보여주는 표](media/model-builder-data.png)

### <a name="data-formats"></a><span data-ttu-id="ec968-187">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ec968-187">Data formats</span></span>

<span data-ttu-id="ec968-188">모델 작성기는 데이터에 다음과 같은 제한 사항을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-188">Model Builder places the following limitations on the data:</span></span>

- <span data-ttu-id="ec968-189">데이터는 파일(헤더 행이 있는 .csv 또는 .tsv) 또는 SQL 서버 데이터베이스에 저장되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-189">Data must be stored in a file (.csv or .tsv with a header row), or in a SQL server database.</span></span>
- <span data-ttu-id="ec968-190">학습 데이터 세트의 한도는 1GB입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-190">A limit of 1 GB on the training dataset</span></span>
- <span data-ttu-id="ec968-191">SQL 서버에는 학습을 위한 행 수가 100,000개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-191">SQL server has a limit of 100,000 rows for training</span></span>
- <span data-ttu-id="ec968-192">학습하기 전에 SQL 서버의 데이터가 서버에서 로컬 머신으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-192">Data from SQL server is copied from the server to your local machine before training</span></span>

### <a name="example-datasets"></a><span data-ttu-id="ec968-193">예제 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="ec968-193">Example datasets</span></span>

<span data-ttu-id="ec968-194">아직 사용자 고유의 데이터가 없는 경우 다음 데이터 세트 중 하나를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ec968-194">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="ec968-195">시나리오</span><span class="sxs-lookup"><span data-stu-id="ec968-195">Scenario</span></span>|<span data-ttu-id="ec968-196">ML 작업</span><span class="sxs-lookup"><span data-stu-id="ec968-196">ML Task</span></span>|<span data-ttu-id="ec968-197">데이터</span><span class="sxs-lookup"><span data-stu-id="ec968-197">Data</span></span>|<span data-ttu-id="ec968-198">레이블</span><span class="sxs-lookup"><span data-stu-id="ec968-198">Label</span></span>|<span data-ttu-id="ec968-199">기능</span><span class="sxs-lookup"><span data-stu-id="ec968-199">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="ec968-200">가격 예측</span><span class="sxs-lookup"><span data-stu-id="ec968-200">Price prediction</span></span>|<span data-ttu-id="ec968-201">회귀</span><span class="sxs-lookup"><span data-stu-id="ec968-201">regression</span></span>|[<span data-ttu-id="ec968-202">택시 요금 데이터</span><span class="sxs-lookup"><span data-stu-id="ec968-202">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="ec968-203">요금</span><span class="sxs-lookup"><span data-stu-id="ec968-203">Fare</span></span>|<span data-ttu-id="ec968-204">운행 시간, 거리</span><span class="sxs-lookup"><span data-stu-id="ec968-204">Trip time, distance</span></span>|
|<span data-ttu-id="ec968-205">변칙 검색</span><span class="sxs-lookup"><span data-stu-id="ec968-205">Anomaly detection</span></span>|<span data-ttu-id="ec968-206">이진 분류</span><span class="sxs-lookup"><span data-stu-id="ec968-206">binary classification</span></span>|[<span data-ttu-id="ec968-207">제품 판매 데이터</span><span class="sxs-lookup"><span data-stu-id="ec968-207">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="ec968-208">제품 판매</span><span class="sxs-lookup"><span data-stu-id="ec968-208">Product Sales</span></span>|<span data-ttu-id="ec968-209">월</span><span class="sxs-lookup"><span data-stu-id="ec968-209">Month</span></span>|
|<span data-ttu-id="ec968-210">정서 분석</span><span class="sxs-lookup"><span data-stu-id="ec968-210">Sentiment analysis</span></span>|<span data-ttu-id="ec968-211">이진 분류</span><span class="sxs-lookup"><span data-stu-id="ec968-211">binary classification</span></span>|[<span data-ttu-id="ec968-212">웹 사이트 주석 데이터</span><span class="sxs-lookup"><span data-stu-id="ec968-212">website comment data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_SentimentAnalysis/SentimentAnalysis/Data/wikiDetoxAnnotated40kRows.tsv)|<span data-ttu-id="ec968-213">레이블(부정적인 감정인 경우 0, 긍정적인 감정인 경우 1)</span><span class="sxs-lookup"><span data-stu-id="ec968-213">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="ec968-214">주석, 연도</span><span class="sxs-lookup"><span data-stu-id="ec968-214">Comment, Year</span></span>|
|<span data-ttu-id="ec968-215">부정 행위 감지</span><span class="sxs-lookup"><span data-stu-id="ec968-215">Fraud detection</span></span>|<span data-ttu-id="ec968-216">이진 분류</span><span class="sxs-lookup"><span data-stu-id="ec968-216">binary classification</span></span>|[<span data-ttu-id="ec968-217">신용 카드 데이터</span><span class="sxs-lookup"><span data-stu-id="ec968-217">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="ec968-218">클래스(사기일 경우 1, 그렇지 않으면 0)</span><span class="sxs-lookup"><span data-stu-id="ec968-218">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="ec968-219">수량, V1-V28(익명화된 기능)</span><span class="sxs-lookup"><span data-stu-id="ec968-219">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="ec968-220">텍스트 분류</span><span class="sxs-lookup"><span data-stu-id="ec968-220">Text classification</span></span>|<span data-ttu-id="ec968-221">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="ec968-221">multiclass classification</span></span>|[<span data-ttu-id="ec968-222">GitHub 문제 데이터</span><span class="sxs-lookup"><span data-stu-id="ec968-222">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="ec968-223">영역</span><span class="sxs-lookup"><span data-stu-id="ec968-223">Area</span></span>|<span data-ttu-id="ec968-224">제목, 설명</span><span class="sxs-lookup"><span data-stu-id="ec968-224">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="ec968-225">학습</span><span class="sxs-lookup"><span data-stu-id="ec968-225">Train</span></span>

<span data-ttu-id="ec968-226">시나리오, 데이터 및 레이블을 선택하면 모델 작성기가 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-226">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="ec968-227">학습이란?</span><span class="sxs-lookup"><span data-stu-id="ec968-227">What is training?</span></span>

<span data-ttu-id="ec968-228">학습은 모델 작성기가 시나리오에 대한 질문에 대답하는 방법을 모델에 알려주는 자동 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-228">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="ec968-229">학습하면 이전에 없었던 입력 데이터로 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-229">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="ec968-230">예를 들어 주택 가격을 예측하고 새 집이 시장에 나온다면 판매 가격을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-230">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="ec968-231">모델 작성기는 AutoML(자동 기계학습)을 사용하기 때문에 학습 중에 입력하거나 튜닝할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-231">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="ec968-232">얼마나 학습해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="ec968-232">How long should I train for?</span></span>

<span data-ttu-id="ec968-233">학습 시간을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-233">You can provide a training time.</span></span> <span data-ttu-id="ec968-234">일반적으로 더 긴 시간 동안 학습하면 더 정확한 모델을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-234">In general, training for a longer time produces a more accurate model.</span></span> <span data-ttu-id="ec968-235">또한 학습 데이터 세트의 크기가 증가함에 따라 더 많은 학습 시간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-235">More training time is also required as the size of the training dataset increases.</span></span> <span data-ttu-id="ec968-236">다음 표는 크기가 증가하는 데이터 세트에 대한 학습 시간 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-236">The following table gives some training time guidelines for datasets of increasing size.</span></span>

<span data-ttu-id="ec968-237">데이터 세트 크기</span><span class="sxs-lookup"><span data-stu-id="ec968-237">Dataset Size</span></span>  | <span data-ttu-id="ec968-238">데이터 세트 형식</span><span class="sxs-lookup"><span data-stu-id="ec968-238">Dataset Type</span></span>       | <span data-ttu-id="ec968-239">평균 학습 시간</span><span class="sxs-lookup"><span data-stu-id="ec968-239">Avg. Time to train</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="ec968-240">0 - 10Mb</span><span class="sxs-lookup"><span data-stu-id="ec968-240">0 - 10 Mb</span></span>     | <span data-ttu-id="ec968-241">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="ec968-241">Numeric and Text</span></span>   | <span data-ttu-id="ec968-242">10초</span><span class="sxs-lookup"><span data-stu-id="ec968-242">10 sec</span></span>
<span data-ttu-id="ec968-243">10 - 100Mb</span><span class="sxs-lookup"><span data-stu-id="ec968-243">10 - 100 Mb</span></span>   | <span data-ttu-id="ec968-244">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="ec968-244">Numeric and Text</span></span>   | <span data-ttu-id="ec968-245">10분</span><span class="sxs-lookup"><span data-stu-id="ec968-245">10 min</span></span> 
<span data-ttu-id="ec968-246">100 - 500Mb</span><span class="sxs-lookup"><span data-stu-id="ec968-246">100 - 500 Mb</span></span>  | <span data-ttu-id="ec968-247">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="ec968-247">Numeric and Text</span></span>   | <span data-ttu-id="ec968-248">30분</span><span class="sxs-lookup"><span data-stu-id="ec968-248">30 min</span></span> 
<span data-ttu-id="ec968-249">500 - 1Gb</span><span class="sxs-lookup"><span data-stu-id="ec968-249">500 - 1 Gb</span></span>    | <span data-ttu-id="ec968-250">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="ec968-250">Numeric and Text</span></span>   | <span data-ttu-id="ec968-251">60분</span><span class="sxs-lookup"><span data-stu-id="ec968-251">60 min</span></span> 
<span data-ttu-id="ec968-252">1Gb+</span><span class="sxs-lookup"><span data-stu-id="ec968-252">1 Gb+</span></span>         | <span data-ttu-id="ec968-253">숫자 및 텍스트</span><span class="sxs-lookup"><span data-stu-id="ec968-253">Numeric and Text</span></span>   | <span data-ttu-id="ec968-254">3시간+</span><span class="sxs-lookup"><span data-stu-id="ec968-254">3 hour+</span></span> 

<span data-ttu-id="ec968-255">또한 정확한 학습 시간은 다음에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-255">The exact time to train also depends on:</span></span>

- <span data-ttu-id="ec968-256">열의 형식, 즉 텍스트 및 숫자</span><span class="sxs-lookup"><span data-stu-id="ec968-256">the type of columns that is, text vs numeric</span></span>
- <span data-ttu-id="ec968-257">기계 학습 작업 형식(회귀 또는 분류)</span><span class="sxs-lookup"><span data-stu-id="ec968-257">the type of machine learning task (regression or classification)</span></span>
- <span data-ttu-id="ec968-258">학습에 사용되는 행 수</span><span class="sxs-lookup"><span data-stu-id="ec968-258">the number of rows used for training</span></span>
- <span data-ttu-id="ec968-259">학습에 사용되는 기능 열의 수</span><span class="sxs-lookup"><span data-stu-id="ec968-259">the number of feature columns used for training</span></span>

<span data-ttu-id="ec968-260">모델 작성기는 1TB 데이터 세트로 확장에 대한 테스트를 받았지만, 데이터 세트 크기에 맞는 고품질 모델을 빌드하는 데 최대 4일이 걸릴 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="ec968-260">Model Builder has been tested for scale with a 1-TB dataset, but building a high-quality model for that size of dataset can take up to four days!</span></span>

## <a name="evaluate"></a><span data-ttu-id="ec968-261">Evaluate</span><span class="sxs-lookup"><span data-stu-id="ec968-261">Evaluate</span></span>

<span data-ttu-id="ec968-262">평가는 학습된 모델을 통해 새 테스트 데이터를 사용하여 예측한 다음, 예측이 얼마나 올바른지를 측정하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-262">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="ec968-263">모델 작성기는 학습 데이터를 학습 집합과 테스트 집합으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-263">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="ec968-264">학습 데이터(80%)는 모델을 학습하는 데 사용되며, 테스트 데이터(20%)는 모델을 평가하기 위해 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-264">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>  <span data-ttu-id="ec968-265">평가에 사용되는 메트릭은 ML 작업에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-265">The metrics used for evaluation depend on the ML task.</span></span> <span data-ttu-id="ec968-266">자세한 내용은 [모델 평가 메트릭](resources/metrics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec968-266">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>  

### <a name="sentiment-analysis-binary-classification"></a><span data-ttu-id="ec968-267">감정 분석(이진 분류)</span><span class="sxs-lookup"><span data-stu-id="ec968-267">Sentiment analysis (binary classification)</span></span>

<span data-ttu-id="ec968-268">이진 분류 문제에 대한 기본 메트릭은 **정확도**입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-268">The default metric for binary classification problems is **accuracy**.</span></span> <span data-ttu-id="ec968-269">정확도는 모델이 테스트 데이터 세트에 대해 내리는 정확한 예측 비율을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-269">Accuracy defines the proportion of correct predictions your model makes over the test dataset.</span></span> <span data-ttu-id="ec968-270">**100%에 가까울 수록 좋습니다**.</span><span class="sxs-lookup"><span data-stu-id="ec968-270">The **closer to 100%, the better it is**.</span></span>

<span data-ttu-id="ec968-271">참 긍정 비율과 거짓 긍정 비율을 측정하는 AUC(곡선 아래의 영역)와 같은 보고된 기타 메트릭은 허용 가능한 모델에 대해 0.50보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-271">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate, should be greater than 0.50 for models to be acceptable.</span></span> 

<span data-ttu-id="ec968-272">F1 점수와 같은 추가 메트릭을 사용하여 정밀도(해당 클래스의 총 예측에 대한 올바른 예측 비율)와 회수(해당 클래스의 총 실제 멤버에 대한 올바른 예측 비율) 간의 균형을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-272">Additional metrics such as F1 score can be used to control the balance between precision (ratio of correct predictions to the total predictions of that class) and recall (proportion of correct predictions to the total actual members of that class).</span></span>

### <a name="issue-classification-multiclass-classification"></a><span data-ttu-id="ec968-273">문제 분류(다중 클래스 분류)</span><span class="sxs-lookup"><span data-stu-id="ec968-273">Issue classification (multiclass classification)</span></span>

<span data-ttu-id="ec968-274">다중 클래스 분류 문제에 대한 기본 메트릭은 **마이크로 정확도**입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-274">The default metric for multiclass classification problems is **micro accuracy**.</span></span> <span data-ttu-id="ec968-275">**100%에 가까울 수록 좋습니다**.</span><span class="sxs-lookup"><span data-stu-id="ec968-275">The **closer to 100%, the better it is**.</span></span>

<span data-ttu-id="ec968-276">데이터가 여러 클래스로 분류되는 문제의 경우 두 가지 유형의 정확도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-276">For problems where data is categorized into multiple classes there are two types of accuracy:</span></span>

- <span data-ttu-id="ec968-277">Micro 정확도: 모든 인스턴스에서 올바른 예측의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-277">Micro-accuracy: the fraction of predictions that are correct across all instances.</span></span> <span data-ttu-id="ec968-278">문제 분류 시나리오에서 마이크로 정확도는 올바른 범주에 할당되는 들어오는 문제의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-278">In the issue classification scenario, micro-accuracy is the proportion of incoming issues that get assigned to the correct category.</span></span> 
- <span data-ttu-id="ec968-279">Macro 정확도: 클래스 수준의 평균 정확도입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-279">Macro-accuracy: the average accuracy at the class level.</span></span> <span data-ttu-id="ec968-280">문제 분류 시나리오에서는 각 범주에 대해 정확도를 측정한 다음, 범주 정확도가 평균화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-280">In the issue classification scenario, the accuracy is measured for each category, and then the category accuracies are averaged.</span></span> <span data-ttu-id="ec968-281">이 메트릭의 경우 모든 클래스에 동일한 가중치가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-281">For this metric, all classes are given equal weight.</span></span> <span data-ttu-id="ec968-282">완벽하게 분산된 데이터 세트(각 범주의 동일한 수의 예제가 있는 경우)의 경우 마이크로 정확도와 매크로 정확도는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-282">For perfectly balanced datasets (where there are an equal number of examples of each category), micro-accuracy and macro-accuracy are the same.</span></span>


### <a name="price-prediction-regression"></a><span data-ttu-id="ec968-283">가격 예측(회귀)</span><span class="sxs-lookup"><span data-stu-id="ec968-283">Price prediction (regression)</span></span>

<span data-ttu-id="ec968-284">회귀 문제에 대한 기본 메트릭은 **RSquared**입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-284">The default metric for regression problems is **RSquared**.</span></span> <span data-ttu-id="ec968-285">1은 가능한 최선의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-285">1 is the best possible value.</span></span> <span data-ttu-id="ec968-286">RSquared가 1에 가까울수록 모델이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-286">The closer RSquared is to 1, the better your model is.</span></span>

<span data-ttu-id="ec968-287">절대 손실, 제곱 손실 및 RMS 손실과 같은 보고된 다른 메트릭을 사용하여 모델을 이해하고 다른 회귀 모델과 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-287">Other metrics reported, such as absolute-loss, squared-loss, and RMS loss can be used to understand your model, and compare it with other regression models.</span></span> 

## <a name="improve"></a><span data-ttu-id="ec968-288">개선</span><span class="sxs-lookup"><span data-stu-id="ec968-288">Improve</span></span>

<span data-ttu-id="ec968-289">모델 성능 점수가 원하는 만큼 좋지 않은 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-289">If your model performance score is not as good as you want it to be, you can:</span></span>

* <span data-ttu-id="ec968-290">더 긴 시간 동안 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-290">Train for a longer period of time.</span></span> <span data-ttu-id="ec968-291">시간이 지날수록 자동화된 기계 학습 엔진은 더 많은 알고리즘과 설정을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-291">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

* <span data-ttu-id="ec968-292">더 많은 데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-292">Add more data.</span></span> <span data-ttu-id="ec968-293">경우에 따라 데이터의 양이 고품질 기계 학습 모델을 학습하기에 충분하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-293">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span> 

* <span data-ttu-id="ec968-294">데이터의 균형을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-294">Balance your data.</span></span> <span data-ttu-id="ec968-295">분류 작업의 경우 학습 집합이 범주 전반에 걸쳐 균형을 유지하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-295">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="ec968-296">예를 들어 100개의 학습 예제에 대한 네 개의 클래스가 있고, 90개의 레코드에 두 개의 첫 번째 클래스(tag1 및 tag2)가 사용되지만 다른 두 개 클래스(tag3 및 tag4)가 나머지 10개의 레코드에만 사용되는 경우 균형 있는 데이터가 부족하여 모델이 tag3 또는 tag4를 올바르게 예측하는 데 어려움을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-296">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="ec968-297">코드</span><span class="sxs-lookup"><span data-stu-id="ec968-297">Code</span></span>

<span data-ttu-id="ec968-298">평가 단계 후 모델 작성기는 모델 파일 및 모델을 애플리케이션에 추가하는 데 사용할 수 있는 코드를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-298">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="ec968-299">ML.NET 모델은 zip 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-299">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="ec968-300">모델을 로드하고 사용하는 코드는 솔루션에는 새 프로젝트로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-300">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="ec968-301">또한 모델 작성기는 실행 중인 모델을 보기 위해 실행할 수 있는 샘플 콘솔 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-301">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="ec968-302">또한 모델 작성기는 모델을 생성하는 데 사용되는 단계를 이해할 수 있도록 모델을 생성하는 코드를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-302">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="ec968-303">모델 학습 코드를 사용하여 새 데이터로 모델을 다시 학습할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec968-303">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="ec968-304">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="ec968-304">What's next?</span></span>

<span data-ttu-id="ec968-305">[가격 예측 또는 모든 회귀 시나리오](tutorials/predict-prices-with-model-builder.md) 시도</span><span class="sxs-lookup"><span data-stu-id="ec968-305">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>

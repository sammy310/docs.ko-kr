---
title: 기계 학습 작업
description: ML.NET에서 지원되는 다양한 기계 학습 작업 및 관련 작업을 살펴봅니다.
ms.custom: seodec18
ms.date: 04/23/2019
author: natke
ms.openlocfilehash: d0634ce8a0559ab3cdb5bf27fc5406ab02af8df6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977251"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="63898-103">ML.NET의 기계 학습 작업</span><span class="sxs-lookup"><span data-stu-id="63898-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="63898-104">기계 학습 모델을 빌드할 때 먼저 데이터로 무엇을 달성하려고 하는지 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="63898-105">그러면 상황에 맞는 올바른 기계 학습 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="63898-106">다음 목록은 사용자가 선택할 수 있는 다양한 기계 학습 작업과 몇 가지 일반적인 사용 사례에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span> <span data-ttu-id="63898-107">시나리오에 적합한 작업을 선택하는 방법에 대한 자세한 내용은 [알고리즘](../how-to-choose-an-ml-net-algorithm.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63898-107">For more information about choosing the task that is appropriate for your scenario, see [Algorithms](../how-to-choose-an-ml-net-algorithm.md).</span></span>

<span data-ttu-id="63898-108">시나리오에 적합한 작업을 선택했으면 모델을 학습할 최상의 알고리즘을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-108">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="63898-109">사용 가능한 알고리즘은 각 작업의 섹션에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-109">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="63898-110">이진 분류</span><span class="sxs-lookup"><span data-stu-id="63898-110">Binary classification</span></span>

<span data-ttu-id="63898-111">두 클래스(범주) 중에 데이터의 인스턴스가 속한 클래스를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-111">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="63898-112">분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다. 여기서 각 레이블은 0 또는 1의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-112">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="63898-113">이진 분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-113">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="63898-114">이진 분류 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-114">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="63898-115">“긍정적” 또는 “부정적”으로 [Twitter 댓글의 감정 이해](../tutorials/sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="63898-115">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="63898-116">환자에게 특정 질병이 있는지 여부 진단.</span><span class="sxs-lookup"><span data-stu-id="63898-116">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="63898-117">전자 메일을 “스팸”으로 표시할지 여부 결정.</span><span class="sxs-lookup"><span data-stu-id="63898-117">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="63898-118">사진이 특정 항목을 포함하는지 여부 확인(예: 개 또는 과일).</span><span class="sxs-lookup"><span data-stu-id="63898-118">Determining if a photo contains a particular item or not, such as a dog or fruit.</span></span>

<span data-ttu-id="63898-119">자세한 내용은 Wikipedia에서 [Binary classification](https://en.wikipedia.org/wiki/Binary_classification)(이진 분류) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63898-119">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="63898-120">이진 분류 트레이너</span><span class="sxs-lookup"><span data-stu-id="63898-120">Binary classification trainers</span></span>

<span data-ttu-id="63898-121">다음 알고리즘을 사용하여 이진 분류 모델을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-121">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="63898-122">이진 분류 입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="63898-122">Binary classification inputs and outputs</span></span>

<span data-ttu-id="63898-123">이진 분류에서 최상의 결과를 내려면 학습 데이터의 균형이 이루어져야 합니다(즉 긍정 및 부정 학습 데이터 수 일치).</span><span class="sxs-lookup"><span data-stu-id="63898-123">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="63898-124">누락 값은 학습 전에 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-124">Missing values should be handled before training.</span></span>

<span data-ttu-id="63898-125">입력 레이블 열 데이터는 <xref:System.Boolean>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-125">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="63898-126">입력 기능 열 데이터는 고정 크기의 <xref:System.Single> 벡터여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-126">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="63898-127">이러한 트레이너는 다음 열을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-127">These trainers output the following columns:</span></span>

| <span data-ttu-id="63898-128">출력 열 이름</span><span class="sxs-lookup"><span data-stu-id="63898-128">Output Column Name</span></span> | <span data-ttu-id="63898-129">열 유형</span><span class="sxs-lookup"><span data-stu-id="63898-129">Column Type</span></span> | <span data-ttu-id="63898-130">설명</span><span class="sxs-lookup"><span data-stu-id="63898-130">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="63898-131">모델에서 계산된 원시 점수</span><span class="sxs-lookup"><span data-stu-id="63898-131">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="63898-132">점수 부호에 따라 예측된 레이블</span><span class="sxs-lookup"><span data-stu-id="63898-132">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="63898-133">음수 점수는 `false`에 양수 점수는 `true`에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-133">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="63898-134">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="63898-134">Multiclass classification</span></span>

<span data-ttu-id="63898-135">데이터 인스턴스의 클래스(범주)를 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-135">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="63898-136">분류 알고리즘의 입력은 레이블이 지정된 예제 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-136">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="63898-137">각 레이블은 일반적으로 텍스트로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-137">Each label normally starts as text.</span></span> <span data-ttu-id="63898-138">그런 다음, TermTransform을 통해 실행되어 키(숫자) 유형으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-138">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="63898-139">분류 알고리즘의 출력은 분류자로, 레이블이 없는 새 인스턴스의 클래스를 예측하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-139">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="63898-140">다중 클래스 분류 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-140">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="63898-141">개의 품종을 “시베리안 허스키”, “골든 리트리버”, “푸들” 등으로 결정.</span><span class="sxs-lookup"><span data-stu-id="63898-141">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="63898-142">동영상 리뷰를 “긍정적”, “중립” 또는 “부정적”으로 이해.</span><span class="sxs-lookup"><span data-stu-id="63898-142">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="63898-143">호텔 리뷰를 “위치”, “가격”, “청결도” 등으로 범주화.</span><span class="sxs-lookup"><span data-stu-id="63898-143">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="63898-144">자세한 내용은 Wikipedia에서 [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification)(다중 클래스 분류) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63898-144">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="63898-145">일 대 다(One vs all)는 모든 [이진 분류 학습자](#binary-classification)를 다중 클래스 데이터 세트에서 작동하도록 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-145">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="63898-146">자세한 내용은 [Wikipedia](https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest) )를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63898-146">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="63898-147">다중 클래스 분류 트레이너</span><span class="sxs-lookup"><span data-stu-id="63898-147">Multiclass classification trainers</span></span>

<span data-ttu-id="63898-148">다음 학습 알고리즘을 사용하여 다중 클래스 분류 모델을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-148">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="63898-149">다중 클래스 분류 입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="63898-149">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="63898-150">입력 레이블 열 데이터는 [키](xref:Microsoft.ML.Data.KeyDataViewType) 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-150">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="63898-151">기능 열은 고정된 크기의 <xref:System.Single> 벡터여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-151">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="63898-152">이 트레이너는 다음을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-152">This trainer outputs the following:</span></span>

| <span data-ttu-id="63898-153">출력 이름</span><span class="sxs-lookup"><span data-stu-id="63898-153">Output Name</span></span> | <span data-ttu-id="63898-154">형식</span><span class="sxs-lookup"><span data-stu-id="63898-154">Type</span></span> | <span data-ttu-id="63898-155">설명</span><span class="sxs-lookup"><span data-stu-id="63898-155">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="63898-156"><xref:System.Single> 벡터</span><span class="sxs-lookup"><span data-stu-id="63898-156">Vector of <xref:System.Single></span></span> | <span data-ttu-id="63898-157">모든 클래스의 점수.</span><span class="sxs-lookup"><span data-stu-id="63898-157">The scores of all classes.</span></span> <span data-ttu-id="63898-158">값이 높을수록 연결된 클래스에 해당할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-158">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="63898-159">i번째 요소의 값이 가장 크다면 예측된 레이블 인덱스는 i가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-159">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="63898-160">i는 0부터 시작하는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-160">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="63898-161">[키](xref:Microsoft.ML.Data.KeyDataViewType) 형식</span><span class="sxs-lookup"><span data-stu-id="63898-161">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="63898-162">예측된 레이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-162">The predicted label's index.</span></span> <span data-ttu-id="63898-163">값이 i라면 실제 레이블은 키 값 입력 레이블 형식에서 i번째 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-163">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="63898-164">재발</span><span class="sxs-lookup"><span data-stu-id="63898-164">Regression</span></span>

<span data-ttu-id="63898-165">관련 기능 집합에서 레이블 값을 예측하는 데 사용되는 [감독된 기계 학습](glossary.md#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-165">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="63898-166">레이블은 실제 값일 수 있고, 분류 작업과 같이 한정된 값 집합에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-166">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="63898-167">회귀 알고리즘 모델은 기능 값이 달라질 때 레이블이 변경되는 방식을 결정하기 위한 관련 기능에 대한 레이블의 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-167">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="63898-168">회귀 알고리즘의 입력은 알려진 값의 레이블이 포함된 예제 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-168">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="63898-169">회귀 알고리즘의 출력은 새 입력 기능 집합의 레이블 값을 예측하는 데 사용할 수 있는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-169">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="63898-170">회귀 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-170">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="63898-171">침실 수, 위치 또는 규모와 같은 주택 특성을 기반으로 주택 가격 예측.</span><span class="sxs-lookup"><span data-stu-id="63898-171">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="63898-172">과거 데이터 및 현재 시장 추세를 기반으로 미래 재고 가격 예측.</span><span class="sxs-lookup"><span data-stu-id="63898-172">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="63898-173">광고 예산을 기반으로 제품 판매 예측.</span><span class="sxs-lookup"><span data-stu-id="63898-173">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="63898-174">회귀 트레이너</span><span class="sxs-lookup"><span data-stu-id="63898-174">Regression trainers</span></span>

<span data-ttu-id="63898-175">다음 알고리즘을 사용하여 회귀 모델을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-175">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="63898-176">회귀 입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="63898-176">Regression inputs and outputs</span></span>

<span data-ttu-id="63898-177">입력 레이블 열 데이터는 <xref:System.Single>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-177">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="63898-178">이 작업에 대한 트레이너는 다음을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-178">The trainers for this task output the following:</span></span>

| <span data-ttu-id="63898-179">출력 이름</span><span class="sxs-lookup"><span data-stu-id="63898-179">Output Name</span></span> | <span data-ttu-id="63898-180">형식</span><span class="sxs-lookup"><span data-stu-id="63898-180">Type</span></span> | <span data-ttu-id="63898-181">설명</span><span class="sxs-lookup"><span data-stu-id="63898-181">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="63898-182">모델에서 예측된 원시 점수</span><span class="sxs-lookup"><span data-stu-id="63898-182">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="63898-183">Clustering</span><span class="sxs-lookup"><span data-stu-id="63898-183">Clustering</span></span>

<span data-ttu-id="63898-184">데이터 인스턴스를 비슷한 특성을 포함하는 클러스터로 그룹화하는 데 사용되는 [감독되지 않는 기계 학습](glossary.md#unsupervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-184">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="63898-185">클러스터링을 사용하여 검색 또는 단순 관찰을 통해 논리적으로 파생될 수 없는 데이터 세트의 관계를 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-185">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="63898-186">클러스터링 알고리즘의 입력 및 출력은 선택한 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="63898-186">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="63898-187">분산, 중심, 연결 또는 밀도 기반 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-187">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="63898-188">현재 ML.NET은 K-평균 클러스터링을 사용하는 중심 기반 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-188">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="63898-189">클러스터링 시나리오의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-189">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="63898-190">호텔 선택의 습관과 특성을 기반으로 호텔 투숙객 세그먼트 이해.</span><span class="sxs-lookup"><span data-stu-id="63898-190">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="63898-191">대상 광고 캠페인을 구축하는 데 도움이 되는 고객 세그먼트 및 인구 통계 식별.</span><span class="sxs-lookup"><span data-stu-id="63898-191">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="63898-192">제조 메트릭을 기반으로 인벤토리 범주화.</span><span class="sxs-lookup"><span data-stu-id="63898-192">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="63898-193">클러스터 트레이너</span><span class="sxs-lookup"><span data-stu-id="63898-193">Clustering trainer</span></span>

<span data-ttu-id="63898-194">다음 알고리즘을 사용하여 클러스터링 모델을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-194">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="63898-195">클러스터 입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="63898-195">Clustering inputs and outputs</span></span>

<span data-ttu-id="63898-196">입력 기능 데이터는 <xref:System.Single>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-196">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="63898-197">레이블이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-197">No labels are needed.</span></span>

<span data-ttu-id="63898-198">이 트레이너는 다음을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-198">This trainer outputs the following:</span></span>

| <span data-ttu-id="63898-199">출력 이름</span><span class="sxs-lookup"><span data-stu-id="63898-199">Output Name</span></span> | <span data-ttu-id="63898-200">형식</span><span class="sxs-lookup"><span data-stu-id="63898-200">Type</span></span> | <span data-ttu-id="63898-201">설명</span><span class="sxs-lookup"><span data-stu-id="63898-201">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="63898-202"><xref:System.Single> 벡터</span><span class="sxs-lookup"><span data-stu-id="63898-202">vector of <xref:System.Single></span></span> | <span data-ttu-id="63898-203">모든 클러스터의 중심에서 특정 데이터 지점까지의 거리</span><span class="sxs-lookup"><span data-stu-id="63898-203">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="63898-204">[키](xref:Microsoft.ML.Data.KeyDataViewType) 형식</span><span class="sxs-lookup"><span data-stu-id="63898-204">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="63898-205">모델에서 예측한 가장 가까운 클러스터의 인덱스</span><span class="sxs-lookup"><span data-stu-id="63898-205">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="63898-206">변칙 검색</span><span class="sxs-lookup"><span data-stu-id="63898-206">Anomaly detection</span></span>

<span data-ttu-id="63898-207">이 작업은 PCA(보안 주체 구성 요소 분석)를 사용하여 변칙 검색 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63898-207">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="63898-208">PCA 기반 변칙 검색은 유효한 트랜잭션과 같은, 한 클래스의 학습 데이터를 얻기는 쉽지만 대상 변칙의 충분한 샘플을 얻기는 어려운 시나리오에서 모델을 빌드하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-208">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="63898-209">기계 학습의 검증된 기술인 PCA는 데이터의 내부 구조를 나타내고 데이터 차이를 설명하기 때문에 탐색적 데이터 분석에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-209">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="63898-210">PCA는 여러 변수를 포함하는 데이터를 분석하여 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-210">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="63898-211">변수 간의 상관 관계를 찾고 결과에서 차이점을 가장 잘 캡처하는 값의 조합을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-211">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="63898-212">이러한 조합된 기능 값이 보안 주체 구성 요소라는 보다 간결한 기능 공간을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-212">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="63898-213">변칙 검색은 다음과 같은 기계 학습의 여러 중요한 작업을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-213">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="63898-214">잠재적으로 사기성이 있는 트랜잭션 식별.</span><span class="sxs-lookup"><span data-stu-id="63898-214">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="63898-215">네트워크 침입이 발생했음을 나타내는 학습 패턴.</span><span class="sxs-lookup"><span data-stu-id="63898-215">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="63898-216">비정상적인 환자 클러스터 찾기.</span><span class="sxs-lookup"><span data-stu-id="63898-216">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="63898-217">시스템에 입력된 값 확인.</span><span class="sxs-lookup"><span data-stu-id="63898-217">Checking values entered into a system.</span></span>

<span data-ttu-id="63898-218">변칙은 정의상 거의 발생하지 않으므로 모델링에 사용할 데이터의 대표 샘플을 수집하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-218">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="63898-219">이 범주에 포함된 알고리즘은 특히 불균형 데이터 세트를 사용하여 모델을 빌드하고 학습시키는 핵심 과제를 해결하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-219">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="63898-220">변칙 검색 트레이너</span><span class="sxs-lookup"><span data-stu-id="63898-220">Anomaly detection trainer</span></span>

<span data-ttu-id="63898-221">다음 알고리즘을 사용하여 변칙 검색 모델을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-221">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="63898-222">변칙 검색 입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="63898-222">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="63898-223">입력 기능은 고정 크기의 <xref:System.Single> 벡터여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-223">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="63898-224">이 트레이너는 다음을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-224">This trainer outputs the following:</span></span>

| <span data-ttu-id="63898-225">출력 이름</span><span class="sxs-lookup"><span data-stu-id="63898-225">Output Name</span></span> | <span data-ttu-id="63898-226">형식</span><span class="sxs-lookup"><span data-stu-id="63898-226">Type</span></span> | <span data-ttu-id="63898-227">설명</span><span class="sxs-lookup"><span data-stu-id="63898-227">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="63898-228">변칙 검색 모델에서 계산된 음수가 아니며 바인딩되지 않은 점수</span><span class="sxs-lookup"><span data-stu-id="63898-228">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |

## <a name="ranking"></a><span data-ttu-id="63898-229">순위 지정</span><span class="sxs-lookup"><span data-stu-id="63898-229">Ranking</span></span>

<span data-ttu-id="63898-230">순위 지정 작업은 레이블이 지정된 예제 세트에서 순위매기기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-230">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="63898-231">이 예제 세트는 지정된 기준에 따라 점수가 매겨질 수 있는 인스턴스 그룹으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-231">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="63898-232">순위 레이블은 각 인스턴스마다 {0, 1, 2, 3, 4}입니다.</span><span class="sxs-lookup"><span data-stu-id="63898-232">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="63898-233">순위매기기는 각 인스턴스마다 점수를 알 수 없는 새 인스턴스 그룹의 순위를 지정하도록 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="63898-233">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="63898-234">ML.NET 순위 지정 학습자는 [기계 학습 순위 지정](https://en.wikipedia.org/wiki/Learning_to_rank)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-234">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="63898-235">순위 지정 학습 알고리즘</span><span class="sxs-lookup"><span data-stu-id="63898-235">Ranking training algorithms</span></span>

<span data-ttu-id="63898-236">다음 알고리즘을 사용하여 순위 지정 모델을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-236">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="63898-237">순위 지정 입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="63898-237">Ranking input and outputs</span></span>

<span data-ttu-id="63898-238">입력 레이블 데이터 형식은 [키](xref:Microsoft.ML.Data.KeyDataViewType) 형식 또는 <xref:System.Single>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-238">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="63898-239">레이블의 값은 관련성을 결정하며 값이 클수록 관련성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-239">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="63898-240">레이블인 [키](xref:Microsoft.ML.Data.KeyDataViewType) 형식이면 키 인덱스가 관련성 값이며 가장 작은 인덱스가 가장 관련도가 적습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-240">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="63898-241">레이블이 <xref:System.Single>이면 값이 클수록 관련도가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-241">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="63898-242">기능 데이터는 고정 크기의 <xref:System.Single> 벡터여야 하며 입력 행 그룹 열은 [키](xref:Microsoft.ML.Data.KeyDataViewType) 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-242">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="63898-243">이 트레이너는 다음을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-243">This trainer outputs the following:</span></span>

| <span data-ttu-id="63898-244">출력 이름</span><span class="sxs-lookup"><span data-stu-id="63898-244">Output Name</span></span> | <span data-ttu-id="63898-245">형식</span><span class="sxs-lookup"><span data-stu-id="63898-245">Type</span></span> | <span data-ttu-id="63898-246">설명</span><span class="sxs-lookup"><span data-stu-id="63898-246">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="63898-247">모델이 예측을 판단하기 위해 계산한 바인딩되지 않은 점수</span><span class="sxs-lookup"><span data-stu-id="63898-247">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="63898-248">권장</span><span class="sxs-lookup"><span data-stu-id="63898-248">Recommendation</span></span>

<span data-ttu-id="63898-249">권장 사항 작업을 통해 권장 제품 또는 서비스 목록을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-249">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="63898-250">ML.NET은 카탈로그에 기록 제품 등급 데이터가 있는 경우 [공동 작업 필터링](https://en.wikipedia.org/wiki/Collaborative_filtering) 알고리즘인 [MF(행렬 인수)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29)를 권장 사항에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-250">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="63898-251">예를 들어 사용자에 대한 기록 영화 등급 데이터가 있고, 사용자가 다음에 시청할 가능성이 큰 다른 영화를 추천하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="63898-251">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="63898-252">권장 사항 학습 알고리즘</span><span class="sxs-lookup"><span data-stu-id="63898-252">Recommendation training algorithms</span></span>

<span data-ttu-id="63898-253">다음 알고리즘을 사용하여 권장 사항 모델을 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63898-253">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>

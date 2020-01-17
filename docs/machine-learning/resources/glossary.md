---
title: 기계 학습 용어집
description: ML.NET에서 사용자 지정 모델을 빌드할 때 유용한 중요한 기계 학습 용어 모음입니다.
ms.topic: reference
ms.date: 07/31/2019
ms.openlocfilehash: 32ccb6df1cb08db45ebd25a0d1c0ea4396a6c50b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739879"
---
# <a name="machine-learning-glossary-of-important-terms"></a><span data-ttu-id="41d9e-103">중요한 용어가 포함된 기계 학습 용어집</span><span class="sxs-lookup"><span data-stu-id="41d9e-103">Machine learning glossary of important terms</span></span>

<span data-ttu-id="41d9e-104">다음 목록은 ML.NET에서 사용자 지정 모델을 빌드할 때 유용한 중요한 기계 학습 용어 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-104">The following list is a compilation of important machine learning terms that are useful as you build your custom models in ML.NET.</span></span>

## <a name="accuracy"></a><span data-ttu-id="41d9e-105">정확도</span><span class="sxs-lookup"><span data-stu-id="41d9e-105">Accuracy</span></span>

<span data-ttu-id="41d9e-106">[분류](#classification)에서 정확도는 올바르게 분류된 항목 수를 테스트 집합의 총 항목 수로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-106">In [classification](#classification), accuracy is the number of correctly classified items divided by the total number of items in the test set.</span></span> <span data-ttu-id="41d9e-107">범위는 0(가장 덜 정확함)에서 -1(가장 정확함)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-107">Ranges from 0 (least accurate) to 1 (most accurate).</span></span> <span data-ttu-id="41d9e-108">정확도는 모델 성능에 대한 평가 메트릭 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-108">Accuracy is one of evaluation metrics of the model performance.</span></span> <span data-ttu-id="41d9e-109">[정밀도](#precision), [재현율](#recall) 및 [F 점수](#f-score)와 함께 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-109">Consider it in conjunction with [precision](#precision), [recall](#recall), and [F-score](#f-score).</span></span>

## <a name="area-under-the-curve-auc"></a><span data-ttu-id="41d9e-110">AUC(Area Under the Curve)</span><span class="sxs-lookup"><span data-stu-id="41d9e-110">Area under the curve (AUC)</span></span>

<span data-ttu-id="41d9e-111">[이진 분류](#binary-classification)에서 거짓 긍정 비율(x축)을 기준으로 참 긍정 비율(y축)을 표시하는 곡선 아래의 영역 값을 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-111">In [binary classification](#binary-classification), an evaluation metric that is the value of the area under the curve that plots the true positives rate (on the y-axis) against the false positives rate (on the x-axis).</span></span> <span data-ttu-id="41d9e-112">범위는 0.5(최악)에서 1(최상)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-112">Ranges from 0.5 (worst) to 1 (best).</span></span> <span data-ttu-id="41d9e-113">ROC 곡선(수신기 운용 특성 곡선) 아래 영역이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-113">Also known as the area under the ROC curve, i.e., receiver operating characteristic curve.</span></span> <span data-ttu-id="41d9e-114">자세한 내용은 Wikipedia에서 [Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic)(수신기 운영 특성) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-114">For more information, see the [Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) article on Wikipedia.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="41d9e-115">이진 분류</span><span class="sxs-lookup"><span data-stu-id="41d9e-115">Binary classification</span></span>

<span data-ttu-id="41d9e-116">[레이블](#label)이 두 클래스 중 하나에만 해당하는 [분류](#classification) 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-116">A [classification](#classification) case where the [label](#label) is only one out of two classes.</span></span> <span data-ttu-id="41d9e-117">자세한 내용은 [기계 학습 작업](tasks.md) 항목의 [이진 분류](tasks.md#binary-classification) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-117">For more information, see the [Binary classification](tasks.md#binary-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="calibration"></a><span data-ttu-id="41d9e-118">보정</span><span class="sxs-lookup"><span data-stu-id="41d9e-118">Calibration</span></span>

<span data-ttu-id="41d9e-119">보정은 이진 및 다중 클래스 분류를 위해 클래스 멤버 자격에 원시 점수를 매핑하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-119">Calibration is the process of mapping a raw score onto a class membership, for binary and multiclass classification.</span></span> <span data-ttu-id="41d9e-120">일부 ML.NET 트레이너에는 `NonCalibrated` 접미사가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-120">Some ML.NET trainers have a `NonCalibrated` suffix.</span></span> <span data-ttu-id="41d9e-121">이러한 알고리즘은 클래스 확률에 매핑되어야 하는 원시 점수를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-121">These algorithms produce a raw score that then must be mapped to a class probability.</span></span>

## <a name="catalog"></a><span data-ttu-id="41d9e-122">Catalog</span><span class="sxs-lookup"><span data-stu-id="41d9e-122">Catalog</span></span>

<span data-ttu-id="41d9e-123">ML.NET에서 카탈로그는 공통 목적에 따라 그룹화된 확장 함수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-123">In ML.NET, a catalog is a collection of extension functions, grouped by a common purpose.</span></span>

<span data-ttu-id="41d9e-124">예를 들어, 각 기계 학습 작업(이진 분류, 회귀, 순위 지정 등)에는 사용 가능한 기계 학습 알고리즘(트레이너)의 카탈로그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-124">For example, each machine learning task (binary classification, regression, ranking etc) has a catalog of available machine learning algorithms (trainers).</span></span> <span data-ttu-id="41d9e-125">이진 분류 트레이너의 카탈로그는 <xref:Microsoft.ML.BinaryClassificationCatalog.BinaryClassificationTrainers>입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-125">The catalog for the binary classification trainers is: <xref:Microsoft.ML.BinaryClassificationCatalog.BinaryClassificationTrainers>.</span></span>

## <a name="classification"></a><span data-ttu-id="41d9e-126">분류</span><span class="sxs-lookup"><span data-stu-id="41d9e-126">Classification</span></span>

<span data-ttu-id="41d9e-127">데이터가 범주를 예측하는 데 사용되는 경우 [감독된 기계 학습](#supervised-machine-learning) 작업을 분류라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-127">When the data is used to predict a category, [supervised machine learning](#supervised-machine-learning) task is called classification.</span></span> <span data-ttu-id="41d9e-128">[이진 분류](#binary-classification)는 두 개의 범주만 예측하는 것을 나타냅니다(예: 이미지를 ‘고양이’ 또는 ‘개’의 그림으로 분류).</span><span class="sxs-lookup"><span data-stu-id="41d9e-128">[Binary classification](#binary-classification) refers to predicting only two categories (for example, classifying an image as a picture of either a 'cat' or a 'dog').</span></span> <span data-ttu-id="41d9e-129">[다중 클래스 분류](#multiclass-classification)는 여러 범주를 예측하는 것을 나타냅니다(예: 이미지를 개의 특정 품종 그림으로 분류하는 경우).</span><span class="sxs-lookup"><span data-stu-id="41d9e-129">[Multiclass classification](#multiclass-classification) refers to predicting multiple categories (for example, when classifying an image as a picture of a specific breed of dog).</span></span>

## <a name="coefficient-of-determination"></a><span data-ttu-id="41d9e-130">결정 계수</span><span class="sxs-lookup"><span data-stu-id="41d9e-130">Coefficient of determination</span></span>

<span data-ttu-id="41d9e-131">[회귀](#regression)에서 데이터가 모델에 얼마나 잘 맞는지를 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-131">In [regression](#regression), an evaluation metric that indicates how well data fits a model.</span></span> <span data-ttu-id="41d9e-132">범위는 0에서 1까지입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-132">Ranges from 0 to 1.</span></span> <span data-ttu-id="41d9e-133">값 0은 데이터가 무작위이거나 모델에 맞지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-133">A value of 0 means that the data is random or otherwise cannot be fit to the model.</span></span> <span data-ttu-id="41d9e-134">값 1은 모델이 데이터와 정확히 일치함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-134">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="41d9e-135">이를 r<sup>2</sup>, R<sup> 2</sup> 또는 r 제곱이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-135">This is often referred to as r<sup>2</sup>, R<sup>2</sup>, or r-squared.</span></span>

## <a name="data"></a><span data-ttu-id="41d9e-136">데이터</span><span class="sxs-lookup"><span data-stu-id="41d9e-136">Data</span></span>

<span data-ttu-id="41d9e-137">데이터는 모든 기계 애플리케이션의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-137">Data is central to any machine learning application.</span></span> <span data-ttu-id="41d9e-138">ML.NET에서 데이터는 <xref:Microsoft.ML.IDataView> 개체로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-138">In ML.NET data is represented by <xref:Microsoft.ML.IDataView> objects.</span></span> <span data-ttu-id="41d9e-139">데이터 뷰 개체:</span><span class="sxs-lookup"><span data-stu-id="41d9e-139">Data view objects:</span></span>

- <span data-ttu-id="41d9e-140">열 및 행으로 구성</span><span class="sxs-lookup"><span data-stu-id="41d9e-140">are made up of columns and rows</span></span>
- <span data-ttu-id="41d9e-141">지연 평가, 자신에 대한 작업이 호출될 때만 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="41d9e-141">are lazily evaluated, that is they only load data when an operation calls for it</span></span>
- <span data-ttu-id="41d9e-142">각 열의 유형, 형식, 길이를 정의하는 스키마 포함</span><span class="sxs-lookup"><span data-stu-id="41d9e-142">contain a schema that defines the type, format and length of each column</span></span>

## <a name="estimator"></a><span data-ttu-id="41d9e-143">평가자</span><span class="sxs-lookup"><span data-stu-id="41d9e-143">Estimator</span></span>

<span data-ttu-id="41d9e-144"><xref:Microsoft.ML.IEstimator%601> 인터페이스를 구현하는 ML.NET의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-144">A class in ML.NET that implements the <xref:Microsoft.ML.IEstimator%601> interface.</span></span>

<span data-ttu-id="41d9e-145">평가자는 변환의 사양입니다(데이터 준비 변환 및 기계 학습 모델 교육 변환 모두).</span><span class="sxs-lookup"><span data-stu-id="41d9e-145">An estimator is a specification of a transformation (both data preparation transformation and machine learning model training transformation).</span></span> <span data-ttu-id="41d9e-146">평가자는 하나의 변환 파이프라인으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-146">Estimators can be chained together into a pipeline of transformations.</span></span> <span data-ttu-id="41d9e-147">평가자의 매개 변수 또는 파이프라인은 <xref:Microsoft.ML.IEstimator%601.Fit%2A> 호출 시 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-147">The parameters of an estimator or pipeline of estimators are learned when <xref:Microsoft.ML.IEstimator%601.Fit%2A> is called.</span></span> <span data-ttu-id="41d9e-148"><xref:Microsoft.ML.IEstimator%601.Fit%2A>의 결과는 [변환기](#transformer)입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-148">The result of <xref:Microsoft.ML.IEstimator%601.Fit%2A> is a [Transformer](#transformer).</span></span>

## <a name="extension-method"></a><span data-ttu-id="41d9e-149">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="41d9e-149">Extension method</span></span>

<span data-ttu-id="41d9e-150">클래스의 일부이나 클래스 외부에서 정의되는 .NET 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-150">A .NET method that is part of a class but is defined outside of the class.</span></span> <span data-ttu-id="41d9e-151">확장 메서드의 첫 번째 매개 변수는 확장 메서드가 속한 클래스에 대한 정적 `this` 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-151">The first parameter of an extension method is a static `this` reference to the class to which the extension method belongs.</span></span>

<span data-ttu-id="41d9e-152">확장 메서드는 [평가자](#estimator)의 인스턴스를 구성하기 위해 ML.NET에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-152">Extension methods are used extensively in ML.NET to construct instances of [estimators](#estimator).</span></span>

## <a name="feature"></a><span data-ttu-id="41d9e-153">기능</span><span class="sxs-lookup"><span data-stu-id="41d9e-153">Feature</span></span>

<span data-ttu-id="41d9e-154">측정 중인 현상의 측정 가능한 속성입니다(일반적으로 숫자(double) 값).</span><span class="sxs-lookup"><span data-stu-id="41d9e-154">A measurable property of the phenomenon being measured, typically a numeric (double) value.</span></span> <span data-ttu-id="41d9e-155">다양한 기능을 **기능 벡터**라고 하며 일반적으로 `double[]`로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-155">Multiple features are referred to as a **Feature vector** and typically stored as `double[]`.</span></span> <span data-ttu-id="41d9e-156">기능은 측정 중인 현상의 중요한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-156">Features define the important characteristics of the phenomenon being measured.</span></span> <span data-ttu-id="41d9e-157">자세한 내용은 Wikipedia에서 [Feature](https://en.wikipedia.org/wiki/Feature_(machine_learning))(기능) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-157">For more information, see the [Feature](https://en.wikipedia.org/wiki/Feature_(machine_learning)) article on Wikipedia.</span></span>

## <a name="feature-engineering"></a><span data-ttu-id="41d9e-158">기능 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="41d9e-158">Feature engineering</span></span>

<span data-ttu-id="41d9e-159">기능 엔지니어링은 [기능](#feature) 집합을 정의하고 사용 가능한 현상 데이터에서 기능 벡터를 생성하는(기능 추출) 소프트웨어를 개발하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-159">Feature engineering is the process that involves defining a set of [features](#feature) and developing software that produces feature vectors from available phenomenon data, i.e., feature extraction.</span></span> <span data-ttu-id="41d9e-160">자세한 내용은 Wikipedia에서 [Feature engineering](https://en.wikipedia.org/wiki/Feature_engineering)(기능 엔지니어링) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-160">For more information, see the [Feature engineering](https://en.wikipedia.org/wiki/Feature_engineering) article on Wikipedia.</span></span>

## <a name="f-score"></a><span data-ttu-id="41d9e-161">F 점수</span><span class="sxs-lookup"><span data-stu-id="41d9e-161">F-score</span></span>

<span data-ttu-id="41d9e-162">[분류](#classification)에서 [정밀도](#precision) 및 [재현율](#recall)을 균형을 맞추는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-162">In [classification](#classification), an evaluation metric that balances [precision](#precision) and [recall](#recall).</span></span>

## <a name="hyperparameter"></a><span data-ttu-id="41d9e-163">하이퍼 매개 변수</span><span class="sxs-lookup"><span data-stu-id="41d9e-163">Hyperparameter</span></span>

<span data-ttu-id="41d9e-164">기계 학습 알고리즘의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-164">A parameter of a machine learning algorithm.</span></span> <span data-ttu-id="41d9e-165">예로는 의사 결정 포리스트에서 학습할 트리 수 또는 그라데이션 하강 알고리즘의 단계 크기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-165">Examples include the number of trees to learn in a decision forest or the step size in a gradient descent algorithm.</span></span> <span data-ttu-id="41d9e-166">‘하이퍼 매개 변수’의 값은 모델 학습 전에 설정되고 예측 함수의 매개 변수(예: 의사 결정 트리의 비교 지점 또는 선형 회귀 모델의 가중치)를 찾는 프로세스를 관리합니다. </span><span class="sxs-lookup"><span data-stu-id="41d9e-166">Values of *Hyperparameters* are set before training the model and govern the process of finding the parameters of the prediction function, for example, the comparison points in a decision tree or the weights in a linear regression model.</span></span> <span data-ttu-id="41d9e-167">자세한 내용은 Wikipedia에서 [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning))(하이퍼 매개 변수) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-167">For more information, see the [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) article on Wikipedia.</span></span>

## <a name="label"></a><span data-ttu-id="41d9e-168">레이블</span><span class="sxs-lookup"><span data-stu-id="41d9e-168">Label</span></span>

<span data-ttu-id="41d9e-169">기계 학습 모델로 예측되는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-169">The element to be predicted with the machine learning model.</span></span> <span data-ttu-id="41d9e-170">예를 들어 개의 품종 또는 미래 재고 가격이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-170">For example, the breed of dog or a future stock price.</span></span>

## <a name="log-loss"></a><span data-ttu-id="41d9e-171">로그 손실</span><span class="sxs-lookup"><span data-stu-id="41d9e-171">Log loss</span></span>

<span data-ttu-id="41d9e-172">[분류](#classification)에서 분류자의 정확도를 분류하는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-172">In [classification](#classification), an evaluation metric that characterizes the accuracy of a classifier.</span></span> <span data-ttu-id="41d9e-173">로그 손실이 작을수록 분류자의 정확도가 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-173">The smaller log loss is, the more accurate a classifier is.</span></span>

## <a name="loss-function"></a><span data-ttu-id="41d9e-174">손실 함수</span><span class="sxs-lookup"><span data-stu-id="41d9e-174">Loss function</span></span>

<span data-ttu-id="41d9e-175">손실 함수는 학습 레이블 값과 모델에 의한 예측 사이의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-175">A loss function is the difference between the training label values and the prediction made by the model.</span></span> <span data-ttu-id="41d9e-176">손실 함수를 최소화하여 모델의 매개 변수를 추정합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-176">The parameters of the model are estimated by minimizing the loss function.</span></span>

<span data-ttu-id="41d9e-177">다양한 함수에 서로 다른 트레이너를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-177">Different trainers can be configured with different loss functions.</span></span>

## <a name="mean-absolute-error-mae"></a><span data-ttu-id="41d9e-178">MAE(절대 평균 오차)</span><span class="sxs-lookup"><span data-stu-id="41d9e-178">Mean absolute error (MAE)</span></span>

<span data-ttu-id="41d9e-179">[회귀](#regression)에서 모든 모델 오차의 평균을 나타내는 평가 메트릭입니다. 여기서 모델 오차는 예측된 [레이블](#label) 값과 올바른 레이블 값 사이의 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-179">In [regression](#regression), an evaluation metric that is the average of all the model errors, where model error is the distance between the predicted [label](#label) value and the correct label value.</span></span>

## <a name="model"></a><span data-ttu-id="41d9e-180">모델</span><span class="sxs-lookup"><span data-stu-id="41d9e-180">Model</span></span>

<span data-ttu-id="41d9e-181">일반적으로 예측 함수에 대한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-181">Traditionally, the parameters for the prediction function.</span></span> <span data-ttu-id="41d9e-182">예를 들어 선형 회귀 모델의 가중치 또는 의사 결정 트리의 분할 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-182">For example, the weights in a linear regression model or the split points in a decision tree.</span></span> <span data-ttu-id="41d9e-183">ML.NET에서 모델에는 도메인 개체의 [레이블](#label)을 예측하는 데 필요한 모든 정보가 포함됩니다(예: 이미지 또는 텍스트).</span><span class="sxs-lookup"><span data-stu-id="41d9e-183">In ML.NET, a model contains all the information necessary to predict the [label](#label) of a domain object (for example, image or text).</span></span> <span data-ttu-id="41d9e-184">이는 ML.NET 모델에 예측 함수의 매개 변수뿐만 아니라 필요한 기능화 단계가 포함됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-184">This means that ML.NET models include the featurization steps necessary as well as the parameters for the prediction function.</span></span>

## <a name="multiclass-classification"></a><span data-ttu-id="41d9e-185">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="41d9e-185">Multiclass classification</span></span>

<span data-ttu-id="41d9e-186">[레이블](#label)이 세 개 이상의 클래스 중 하나인 [분류](#classification) 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-186">A [classification](#classification) case where the [label](#label) is one out of three or more classes.</span></span> <span data-ttu-id="41d9e-187">자세한 내용은 [다중 클래스 작업](tasks.md) 항목의 [이진 분류](tasks.md#multiclass-classification) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-187">For more information, see the [Multiclass classification](tasks.md#multiclass-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="n-gram"></a><span data-ttu-id="41d9e-188">N-gram</span><span class="sxs-lookup"><span data-stu-id="41d9e-188">N-gram</span></span>

<span data-ttu-id="41d9e-189">텍스트 데이터에 대한 기능 추출 체계: N 단어 시퀀스가 [기능](#feature) 값으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-189">A feature extraction scheme for text data: any sequence of N words turns into a [feature](#feature) value.</span></span>

## <a name="normalization"></a><span data-ttu-id="41d9e-190">표준화</span><span class="sxs-lookup"><span data-stu-id="41d9e-190">Normalization</span></span>

<span data-ttu-id="41d9e-191">표준화는 부동 소수점 데이터를 0에서 1 사이의 값으로 조정하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-191">Normalization is the process of scaling floating point data to values between 0 and 1.</span></span> <span data-ttu-id="41d9e-192">ML.NET에서 사용되는 대부분의 학습 알고리즘은 입력 기능 데이터를 표준화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-192">Many of the training algorithms used in ML.NET require input feature data to be normalized.</span></span> <span data-ttu-id="41d9e-193">ML.NET에서 일련의 [표준화 변환](transforms.md#normalization-and-scaling)을 제공</span><span class="sxs-lookup"><span data-stu-id="41d9e-193">ML.NET provides a series of [transforms for normalization](transforms.md#normalization-and-scaling)</span></span>

## <a name="numerical-feature-vector"></a><span data-ttu-id="41d9e-194">숫자 기능 벡터</span><span class="sxs-lookup"><span data-stu-id="41d9e-194">Numerical feature vector</span></span>

<span data-ttu-id="41d9e-195">숫자 값만으로 구성된 [기능](#feature) 벡터입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-195">A [feature](#feature) vector consisting only of numerical values.</span></span> <span data-ttu-id="41d9e-196">이는 `double[]`과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-196">This is similar to `double[]`.</span></span>

## <a name="pipeline"></a><span data-ttu-id="41d9e-197">파이프라인</span><span class="sxs-lookup"><span data-stu-id="41d9e-197">Pipeline</span></span>

<span data-ttu-id="41d9e-198">데이터 집합에 모델을 맞추는 데 필요한 모든 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-198">All of the operations needed to fit a model to a data set.</span></span> <span data-ttu-id="41d9e-199">파이프라인은 데이터 가져오기, 변환, 기능화 및 학습 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-199">A pipeline consists of data import, transformation, featurization, and learning steps.</span></span> <span data-ttu-id="41d9e-200">파이프라인은 학습된 후 모델로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-200">Once a pipeline is trained, it turns into a model.</span></span>

## <a name="precision"></a><span data-ttu-id="41d9e-201">전체 자릿수</span><span class="sxs-lookup"><span data-stu-id="41d9e-201">Precision</span></span>

<span data-ttu-id="41d9e-202">[분류](#classification)에서 클래스의 정밀도는 해당 클래스에 속하는 것으로 올바르게 예측된 항목 수를 클래스에 속하는 것으로 예측된 총 항목 수로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-202">In [classification](#classification), the precision for a class is the number of items correctly predicted as belonging to that class divided by the total number of items predicted as belonging to the class.</span></span>

## <a name="recall"></a><span data-ttu-id="41d9e-203">재현율</span><span class="sxs-lookup"><span data-stu-id="41d9e-203">Recall</span></span>

<span data-ttu-id="41d9e-204">[분류](#classification)에서 클래스의 재현율은 해당 클래스에 속하는 것으로 올바르게 예측된 항목 수를 실제로 클래스에 속하는 총 항목 수로 나눈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-204">In [classification](#classification), the recall for a class is the number of items correctly predicted as belonging to that class divided by the total number of items that actually belong to the class.</span></span>

## <a name="regularization"></a><span data-ttu-id="41d9e-205">정규화</span><span class="sxs-lookup"><span data-stu-id="41d9e-205">Regularization</span></span>

 <span data-ttu-id="41d9e-206">정규화는 너무 복잡한 선형 모델에 벌점을 부과합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-206">Regularization penalizes a linear model for being too complicated.</span></span> <span data-ttu-id="41d9e-207">정규화는 두 가지 종류로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-207">There are two types of regularization:</span></span>

- <span data-ttu-id="41d9e-208">$L_1$ 정규화는 불충분한 기능에 대해 0 가중치를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-208">$L_1$ regularization zeros weights for insignificant features.</span></span> <span data-ttu-id="41d9e-209">이런 정규화 후에는 저장된 모델의 크기가 더 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-209">The size of the saved model may become smaller after this type of regularization.</span></span>
- <span data-ttu-id="41d9e-210">$L _2 $ 정규화는 의미 없는 기능에 대한 가중치 범위를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-210">$L_2$ regularization minimizes weight range for insignificant features.</span></span> <span data-ttu-id="41d9e-211">이는 보다 일반적인 프로세스이며 이상값에 덜 민감합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-211">This is a more general process and is less sensitive to outliers.</span></span>

## <a name="regression"></a><span data-ttu-id="41d9e-212">재발</span><span class="sxs-lookup"><span data-stu-id="41d9e-212">Regression</span></span>

<span data-ttu-id="41d9e-213">출력이 실제 값(예: double)인 [감독된 기계 학습](#supervised-machine-learning) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-213">A [supervised machine learning](#supervised-machine-learning) task where the output is a real value, for example, double.</span></span> <span data-ttu-id="41d9e-214">예로는 재고 가격 예측이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-214">Examples include predicting stock prices.</span></span> <span data-ttu-id="41d9e-215">자세한 내용은 [다중 클래스 작업](tasks.md) 항목의 [회귀](tasks.md#regression) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-215">For more information, see the [Regression](tasks.md#regression) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="relative-absolute-error"></a><span data-ttu-id="41d9e-216">상대 절대 오차</span><span class="sxs-lookup"><span data-stu-id="41d9e-216">Relative absolute error</span></span>

<span data-ttu-id="41d9e-217">[회귀](#regression)에서 모든 절대 오차의 합계를 올바른 [레이블](#label) 값과 모든 올바른 레이블 값의 평균 간 거리의 합계로 나눈 값을 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-217">In [regression](#regression), an evaluation metric that is the sum of all absolute errors divided by the sum of distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="relative-squared-error"></a><span data-ttu-id="41d9e-218">상대 제곱 오차</span><span class="sxs-lookup"><span data-stu-id="41d9e-218">Relative squared error</span></span>

<span data-ttu-id="41d9e-219">[회귀](#regression)에서 모든 절대 제곱 오차의 합계를 올바른 [레이블](#label) 값과 모든 올바른 레이블 값의 평균 간 거리 제곱의 합계로 나눈 값을 나타내는 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-219">In [regression](#regression), an evaluation metric that is the sum of all squared absolute errors divided by the sum of squared distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="root-of-mean-squared-error-rmse"></a><span data-ttu-id="41d9e-220">RMSE(평균 제곱 오차의 제곱근)</span><span class="sxs-lookup"><span data-stu-id="41d9e-220">Root of mean squared error (RMSE)</span></span>

<span data-ttu-id="41d9e-221">[회귀](#regression)에서 오차 제곱 평균의 제곱근인 평가 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-221">In [regression](#regression), an evaluation metric that is the square root of the average of the squares of the errors.</span></span>

## <a name="scoring"></a><span data-ttu-id="41d9e-222">채점</span><span class="sxs-lookup"><span data-stu-id="41d9e-222">Scoring</span></span>

<span data-ttu-id="41d9e-223">채점은 학습된 기계 학습 모델에 새 데이터를 적용하고 예측을 생성하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-223">Scoring is the process of applying new data to a trained machine learning model, and generating predictions.</span></span> <span data-ttu-id="41d9e-224">채점은 추론이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-224">Scoring is also known as inferencing.</span></span> <span data-ttu-id="41d9e-225">모델 유형에 따라 점수는 원시 값, 확률 또는 범주가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-225">Depending on the type of model, the score may be a raw value, a probability, or a category.</span></span>

## <a name="supervised-machine-learning"></a><span data-ttu-id="41d9e-226">감독된 기계 학습</span><span class="sxs-lookup"><span data-stu-id="41d9e-226">Supervised machine learning</span></span>

<span data-ttu-id="41d9e-227">원하는 모델이 아직 확인되지 않은 데이터에 대한 레이블을 예측하는 기계 학습의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-227">A subclass of machine learning in which a desired model predicts the label for yet-unseen data.</span></span> <span data-ttu-id="41d9e-228">예로는 분류, 회귀 및 구조화된 예측이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-228">Examples include classification, regression, and structured prediction.</span></span> <span data-ttu-id="41d9e-229">자세한 내용은 Wikipedia에서 [Supervised learning](https://en.wikipedia.org/wiki/Supervised_learning)(감독된 학습) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-229">For more information, see the  [Supervised learning](https://en.wikipedia.org/wiki/Supervised_learning) article on Wikipedia.</span></span>

## <a name="training"></a><span data-ttu-id="41d9e-230">교육</span><span class="sxs-lookup"><span data-stu-id="41d9e-230">Training</span></span>

<span data-ttu-id="41d9e-231">지정된 학습 데이터 집합에 대한 [모델](#model)을 식별하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-231">The process of identifying a [model](#model) for a given training data set.</span></span> <span data-ttu-id="41d9e-232">선형 모델의 경우 가중치를 찾는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-232">For a linear model, this means finding the weights.</span></span> <span data-ttu-id="41d9e-233">트리의 경우 분할 지점을 식별하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-233">For a tree, it involves identifying the split points.</span></span>

## <a name="transformer"></a><span data-ttu-id="41d9e-234">변환기</span><span class="sxs-lookup"><span data-stu-id="41d9e-234">Transformer</span></span>

<span data-ttu-id="41d9e-235"><xref:Microsoft.ML.ITransformer> 인터페이스를 구현하는 ML.NET 클래스</span><span class="sxs-lookup"><span data-stu-id="41d9e-235">An ML.NET class that implements the <xref:Microsoft.ML.ITransformer> interface.</span></span>

<span data-ttu-id="41d9e-236">변환기는 한 <xref:Microsoft.ML.IDataView>를 다른 항목으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-236">A transformer transforms one <xref:Microsoft.ML.IDataView> into another.</span></span> <span data-ttu-id="41d9e-237">변환기는 [추정기](#estimator) 또는 추정기 파이프라인 학습을 통해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-237">A transformer is created by training an [estimator](#estimator), or an estimator pipeline.</span></span>

## <a name="unsupervised-machine-learning"></a><span data-ttu-id="41d9e-238">감독되지 않는 기계 학습</span><span class="sxs-lookup"><span data-stu-id="41d9e-238">Unsupervised machine learning</span></span>

<span data-ttu-id="41d9e-239">원하는 모델이 데이터에서 숨겨진(또는 잠재적) 구조를 찾는 기계 학습의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-239">A subclass of machine learning in which a desired model finds hidden (or latent) structure in data.</span></span> <span data-ttu-id="41d9e-240">예로는 클러스터링, 항목 모델링 및 차원 감소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d9e-240">Examples include clustering, topic modeling, and dimensionality reduction.</span></span> <span data-ttu-id="41d9e-241">자세한 내용은 Wikipedia에서 [Unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning)(감독되지 않는 학습) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41d9e-241">For more information, see the [Unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning) article on Wikipedia.</span></span>

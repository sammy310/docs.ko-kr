---
title: ML.NET 방법 가이드
description: 사용자 지정 AI 솔루션 생성 및 .NET 애플리케이션에 Machine Learning 통합을 지원하는 특정 작업을 수행하는 방법에 대해 알아보세요.
ms.custom: seodec18
ms.date: 03/01/2019
ms.openlocfilehash: c16adf6bf85aec1aef51751c6d4fe8c7f0f3c9f4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645039"
---
# <a name="net-machine-learning-how-to-guides"></a><span data-ttu-id="717b6-103">.NET 기계 학습 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="717b6-103">.NET Machine learning how-to guides</span></span> 

<span data-ttu-id="717b6-104">ML.NET 가이드의 방법 섹션에서 일반적인 질문에 대한 빠른 답변을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="717b6-105">경우에 따라 문서를 쉽게 찾을 수 있도록 여러 섹션에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="717b6-106">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="717b6-106">Load the data</span></span>

* [<span data-ttu-id="717b6-107">기계 학습 처리를 위해 CSV 파일에서 많은 열을 포함하는 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-107">Load data with many columns from a CSV file for machine learning processing.</span></span>](load-data-from-mult-column-csv-ml-net.md)

* [<span data-ttu-id="717b6-108">기계 학습 처리를 위해 여러 파일에서 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-108">Load data from multiple files for machine learning processing.</span></span>](load-data-from-multiple-files-ml-net.md)

* [<span data-ttu-id="717b6-109">기계 학습 처리를 위해 텍스트 파일에서 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-109">Load data from a text file for machine learning processing.</span></span>](load-data-from-text-file-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="717b6-110">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="717b6-110">Prepare the data</span></span>

* [<span data-ttu-id="717b6-111">데이터 처리에 사용할 학습 데이터를 노멀라이저로 전처리합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-111">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="717b6-112">모델 학습</span><span class="sxs-lookup"><span data-stu-id="717b6-112">Train the model</span></span>

* [<span data-ttu-id="717b6-113">텍스트 파일에 포함되지 않은 데이터를 사용하여 기계 학습 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-113">Train a machine learning model with data that's not in a text file.</span></span>](load-non-file-training-data-ml-net.md)

* [<span data-ttu-id="717b6-114">교차 유효성 검사를 사용하여 기계 학습 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-114">Train a machine learning model using cross-validation.</span></span>](train-cross-validation-ml-net.md)

* [<span data-ttu-id="717b6-115">ML.NET을 사용해서 회귀 모델을 학습하여 값을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-115">Train a regression model to predict a value using ML.NET.</span></span>](train-regression-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="717b6-116">모델 품질 평가</span><span class="sxs-lookup"><span data-stu-id="717b6-116">Evaluate the model quality</span></span>

* [<span data-ttu-id="717b6-117">메트릭을 계산하여 모델 품질을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-117">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="717b6-118">모델 설명 가능성</span><span class="sxs-lookup"><span data-stu-id="717b6-118">Model explainability</span></span>

* [<span data-ttu-id="717b6-119">순열 기능 중요도를 사용하여 모델의 기능 중요도를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-119">Determine the feature importance of models with Permutation Feature Importance.</span></span>](determine-global-feature-importance-in-model.md)

* [<span data-ttu-id="717b6-120">모델 설명을 위해 일반화된 추가 모델 및 도형 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-120">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

### <a name="feature-engineering"></a><span data-ttu-id="717b6-121">기능 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="717b6-121">Feature engineering</span></span>

* [<span data-ttu-id="717b6-122">범주 데이터에 모델 학습용 기능 엔지니어링을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-122">Apply feature engineering for model training on categorical data.</span></span>](train-model-categorical-ml-net.md)

* [<span data-ttu-id="717b6-123">ML.NET을 사용하여 텍스트 데이터에 모델 학습용 기능 엔지니어링을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-123">Apply feature engineering for model training on textual data with ML.NET.</span></span>](train-model-textual-ml-net.md)

## <a name="run"></a><span data-ttu-id="717b6-124">실행</span><span class="sxs-lookup"><span data-stu-id="717b6-124">Run</span></span>

* [<span data-ttu-id="717b6-125">ML.NET 파이프라인을 처리하는 동안 중간 데이터 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-125">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="717b6-126">앱에서 학습된 기계 학습 모델을 운용합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-126">Operationalize a trained machine learning model in apps.</span></span>](consuming-model-ml-net.md)

* [<span data-ttu-id="717b6-127">PredictionFunction을 사용하여 한 번에 하나씩 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-127">Use the PredictionFunction to make one prediction at a time.</span></span>](single-predict-model-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="717b6-128">확률(Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="717b6-128">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="717b6-129">Infer.NET 및 확률적 프로그래밍을 사용하여 게임 대전 목록 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="717b6-129">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)

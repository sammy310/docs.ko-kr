---
title: ML.NET 방법 가이드
description: 사용자 지정 AI 솔루션 생성 및 .NET 애플리케이션에 Machine Learning 통합을 지원하는 특정 작업을 수행하는 방법에 대해 알아보세요.
ms.date: 03/01/2019
ms.openlocfilehash: 4ce2de77c35062aa19449e3ba6bb3d5abd003d60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715661"
---
# <a name="net-machine-learning-how-to-guides"></a><span data-ttu-id="4fac4-103">.NET 기계 학습 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="4fac4-103">.NET Machine learning how-to guides</span></span>

<span data-ttu-id="4fac4-104">ML.NET 가이드의 방법 섹션에서 일반적인 질문에 대한 빠른 답변을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="4fac4-105">경우에 따라 문서를 쉽게 찾을 수 있도록 여러 섹션에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-data"></a><span data-ttu-id="4fac4-106">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="4fac4-106">Load data</span></span>

* [<span data-ttu-id="4fac4-107">파일 및 SQL 데이터베이스에서 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-107">Load data from files and SQL databases.</span></span>](load-data-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="4fac4-108">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="4fac4-108">Prepare the data</span></span>

* [<span data-ttu-id="4fac4-109">데이터 처리에 사용할 학습 데이터를 노멀라이저로 전처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-109">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="4fac4-110">모델 학습</span><span class="sxs-lookup"><span data-stu-id="4fac4-110">Train the model</span></span>

* [<span data-ttu-id="4fac4-111">교차 유효성 검사를 사용하여 기계 학습 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-111">Train a machine learning model using cross-validation.</span></span>](train-machine-learning-model-cross-validation-ml-net.md)

* [<span data-ttu-id="4fac4-112">ML.NET을 사용해서 회귀 모델을 학습하여 값을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-112">Train a regression model to predict a value using ML.NET.</span></span>](train-machine-learning-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="4fac4-113">모델 품질 평가</span><span class="sxs-lookup"><span data-stu-id="4fac4-113">Evaluate the model quality</span></span>

* [<span data-ttu-id="4fac4-114">메트릭을 계산하여 모델 품질을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-114">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="4fac4-115">모델 설명 가능성</span><span class="sxs-lookup"><span data-stu-id="4fac4-115">Model explainability</span></span>

* [<span data-ttu-id="4fac4-116">순열 기능 중요도를 사용하여 모델의 기능 중요도를 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-116">Determine the feature importance of models with Permutation Feature Importance.</span></span>](explain-machine-learning-model-permutation-feature-importance-ml-net.md)

* [<span data-ttu-id="4fac4-117">모델 설명을 위해 일반화된 추가 모델 및 도형 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-117">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

## <a name="run"></a><span data-ttu-id="4fac4-118">다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-118">Run</span></span>

* [<span data-ttu-id="4fac4-119">ML.NET 파이프라인을 처리하는 동안 중간 데이터 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-119">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="4fac4-120">학습된 기계 학습 모델을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-120">Load a trained machine learning model.</span></span>](save-load-machine-learning-models-ml-net.md)

* [<span data-ttu-id="4fac4-121">학습된 모델로 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-121">Make predictions with a trained model.</span></span>](machine-learning-model-predictions-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="4fac4-122">확률(Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="4fac4-122">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="4fac4-123">Infer.NET 및 확률적 프로그래밍을 사용하여 게임 대전 목록 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4fac4-123">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)

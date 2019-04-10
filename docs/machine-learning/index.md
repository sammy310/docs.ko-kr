---
title: ML.NET 콘텐츠 가이드
description: ML.NET를 사용하여 사용자 지정 AI 솔루션을 빌드하고 .NET 애플리케이션에 통합하는 방법을 알아봅니다.
ms.date: 04/05/2019
ms.custom: seodec18
ms.openlocfilehash: de681daea5a29a121d350271ced4ccc2c0b1b533
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231333"
---
# <a name="mlnet-content-guide"></a><span data-ttu-id="a7c93-103">ML.NET 콘텐츠 가이드</span><span class="sxs-lookup"><span data-stu-id="a7c93-103">ML.NET Content Guide</span></span>

<span data-ttu-id="a7c93-104">이 가이드에서는 기본 개념을 설명하고 ML.NET 작업에 대한 자습서 및 API 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-104">This guide explains basic concepts and provides tutorials and an API reference for working with ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="a7c93-105">이 문서는 현재 미리 보기로 제공되고 있는 ML.NET을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="a7c93-106">자료가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-106">Material may be subject to change.</span></span> <span data-ttu-id="a7c93-107">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7c93-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="get-started"></a><span data-ttu-id="a7c93-108">시작</span><span class="sxs-lookup"><span data-stu-id="a7c93-108">Get started</span></span>

<span data-ttu-id="a7c93-109">ML.NET을 설치하고 빌드를 시작하려면 [시작 자습서](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial)를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a7c93-109">To install and start building in ML.NET, follow the [Get started tutorial](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span></span>

<span data-ttu-id="a7c93-110">ML.NET에 대해 알아보려면 [ML.NET이란?](what-is-mldotnet.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7c93-110">To learn about ML.NET, see [What is ML.NET?](what-is-mldotnet.md)</span></span>

<span data-ttu-id="a7c93-111">기본 사항을 이해하려면 [ML.NET의 모델 학습에 대한 기본 개념](basic-concepts-model-training-in-mldotnet.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7c93-111">To understand basics, see [Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span></span>

## <a name="tutorials"></a><span data-ttu-id="a7c93-112">자습서</span><span class="sxs-lookup"><span data-stu-id="a7c93-112">Tutorials</span></span>

<span data-ttu-id="a7c93-113">[이진 분류 모델을 사용하여 감정 분석](./tutorials/sentiment-analysis.md)에서는 감정이 긍정적인지 부정적인지를 판별하는 앱을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-113">[Analyze sentiment using a binary classification model](./tutorials/sentiment-analysis.md) shows you how to build an app that determines whether sentiment is positive or negative.</span></span>

<span data-ttu-id="a7c93-114">[다중 클래스 분류 모델을 사용하여 GitHub 문제 분류](./tutorials/github-issue-classification.md)에서는 GitHub 문제의 영역 레이블을 결정하는 앱을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-114">[Classify GitHub issues using a multiclass classification model](./tutorials/github-issue-classification.md) shows you how to build an app that determines the Area label for a GitHub issue.</span></span>

<span data-ttu-id="a7c93-115">[회귀 모델을 사용하여 가격 예측](./tutorials/taxi-fare.md)에서는 기록 데이터의 여러 요소를 사용하여 응답을 판별하는 예측 앱을 빌드하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-115">[Predict prices using a regression model](./tutorials/taxi-fare.md) shows you how to build a predictive app that uses many factors from historical data to determine the answer.</span></span>

<span data-ttu-id="a7c93-116">[기능으로 아이리스 꽃 분류](./tutorials/iris-clustering.md)에서는 클러스터링 모델을 사용하여 아이리스 데이터 세트를 분석하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-116">[Classify iris flowers by features](./tutorials/iris-clustering.md) shows you how to use a clustering model to analyze the iris data set.</span></span>

<span data-ttu-id="a7c93-117">[ML.NET을 사용하여 영화 추천 앱 만들기](./tutorials/movie-recommmendation.md)에서는 사용자의 기록을 바탕으로 사용자에게 영화를 추천하는 추천 앱을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-117">[Create a Movie Recommender with ML.NET](./tutorials/movie-recommmendation.md) shows you how to build a recommendation app to recommend movies to users based on their history.</span></span>

<span data-ttu-id="a7c93-118">[TensorFlow를 사용하여 ML.NET 사용자 지정 이미지 분류자 빌드](./tutorials/image-classification.md): ML.NET을 사용하여 사용자 지정 이미지 분류자를 만들기 위해 기존 Tensorflow 모델을 재학습하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-118">[Build an ML.NET custom image classifier with TensorFlow](./tutorials/image-classification.md): demonstrates how to retrain an existing Tensorflow model to create a custom image classifier using ML.NET.</span></span>

## <a name="how-to-guide"></a><span data-ttu-id="a7c93-119">방법 가이드</span><span class="sxs-lookup"><span data-stu-id="a7c93-119">How to guide</span></span>

<span data-ttu-id="a7c93-120">[Infer.NET 및 확률 프로그래밍을 사용하여 게임 대전 목록 앱 빌드](./how-to-guides/matchup-app-infer-net.md)에서는 Xbox 게임에서 보는 것과 같은 간단한 버전의 대전 앱을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-120">[Build a game match-up list app with Infer.NET and probabilistic programming](./how-to-guides/matchup-app-infer-net.md) shows you how to build a simplified version of a match-up app like you'd see in an Xbox game.</span></span>

## <a name="resources"></a><span data-ttu-id="a7c93-121">자료</span><span class="sxs-lookup"><span data-stu-id="a7c93-121">Resources</span></span>

<span data-ttu-id="a7c93-122">[기계 학습 용어집](./resources/glossary.md)에서는 주요 용어를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-122">[Machine learning glossary](./resources/glossary.md) defines key terminology.</span></span>

<span data-ttu-id="a7c93-123">[기계 학습 작업](./resources/tasks.md)에서는 분류 및 변칙 검색과 같은 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-123">[Machine learning tasks](./resources/tasks.md) describes tasks, such as classification and anomaly detection.</span></span> 

<span data-ttu-id="a7c93-124">[데이터 변환](./resources/transforms.md)에서는 ML.NET의 데이터 준비 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-124">[Data transforms](./resources/transforms.md) describes data preparation capabilities in ML.NET.</span></span>

## <a name="api-reference"></a><span data-ttu-id="a7c93-125">API 참조</span><span class="sxs-lookup"><span data-stu-id="a7c93-125">API reference</span></span>

<span data-ttu-id="a7c93-126">[ML.NET API 참조](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)에서는 사용 가능한 API 범위를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c93-126">[ML.NET API Reference](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) describes the breadth of APIs available.</span></span>

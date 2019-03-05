---
title: ML.NET의 정의 및 Machine Learning 기본 사항을 이해하는 방법은 무엇인가요?
description: 사용자 지정 AI 솔루션을 빌드하고 .NET 애플리케이션에 통합할 수 있도록 하는 무료 오픈 소스 플랫폼 간 기계 학습 프레임워크인 ML.NET에 대해 알아봅니다.
author: cjgronlund
ms.custom: seodec18
ms.topic: overview
ms.date: 03/01/2019
ms.openlocfilehash: 08e5f31502555ed1a04a6a4afa70bc98e8fd015a
ms.sourcegitcommit: a532e8314c3a4b5b039656567fedff9787a31957
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57250964"
---
# <a name="what-is-mlnet-and-how-do-i-understand-machine-learning-basics"></a><span data-ttu-id="458ab-103">ML.NET의 정의 및 Machine Learning 기본 사항을 이해하는 방법은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="458ab-103">What is ML.NET and how do I understand Machine Learning basics?</span></span>

<span data-ttu-id="458ab-104">ML.NET은 사용자 지정 기계 학습 솔루션을 빌드하고 .NET 애플리케이션에 통합할 수 있도록 하는 무료 오픈 소스 플랫폼 간 기계 학습 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-104">ML.NET is a free, open-source, and cross-platform machine learning framework that enables you to build custom machine learning solutions and integrate them into your .NET applications.</span></span> <span data-ttu-id="458ab-105">ML.NET API를 사용하면 .NET을 종료하지 않고 이미 보유한 .NET 기술을 사용하여 앱에 AI를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-105">With the ML.NET APIs, you can incorporate AI into your apps using the .NET skills you already have and without leaving .NET.</span></span>

## <a name="what-is-machine-learning"></a><span data-ttu-id="458ab-106">기계 학습이란?</span><span class="sxs-lookup"><span data-stu-id="458ab-106">What is machine learning?</span></span>

<span data-ttu-id="458ab-107">기계 학습은 컴퓨터가 기존 데이터를 사용하여 향후 동작, 결과 및 추세를 예측할 수 있게 해주는 데이터 과학 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-107">Machine learning is a data science technique that allows computers to use existing data to forecast future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="458ab-108">기계 학습을 사용하는 컴퓨터는 명시적으로 프로그래밍되지 않고 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-108">Using machine learning, computers learn without being explicitly programmed.</span></span>

<span data-ttu-id="458ab-109">기계 학습의 예상이나 예측을 통해 앱과 디바이스를 더 효율적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-109">Forecasts or predictions from machine learning can make apps and devices smarter.</span></span> <span data-ttu-id="458ab-110">온라인 쇼핑 시 기계 학습을 통해 구입한 제품을 기반으로 사용자가 좋아할 만한 다른 제품을 추천할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-110">When you shop online, machine learning helps recommend other products you might like based on what you've purchased.</span></span> <span data-ttu-id="458ab-111">신용 카드를 판독기에 대면 기계 학습이 트랜잭션 데이터베이스와 트랜잭션을 비교하여 사기 행위를 탐지하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-111">When your credit card is swiped, machine learning compares the transaction to a database of transactions and helps detect fraud.</span></span> <span data-ttu-id="458ab-112">로봇 진공 청소기가 방을 청소할 때 기계 학습은 로봇이 작업 완료 여부를 결정하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-112">When your robot vacuum cleaner vacuums a room, machine learning helps it decide whether the job is done.</span></span>


## <a name="short-videos-on-data-science"></a><span data-ttu-id="458ab-113">데이터 과학에 대한 짧은 비디오</span><span class="sxs-lookup"><span data-stu-id="458ab-113">Short videos on data science</span></span> 

<span data-ttu-id="458ab-114">최고 데이터 과학자의 짧은 비디오 5개로 구성된 *초보자를 위한 데이터 과학*에서 기계 학습 및 데이터 과학의 기본 사항을 간단히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-114">Get a quick introduction to the basics of machine learning and data science from *Data Science for Beginners* in five short videos from a top data scientist.</span></span> <span data-ttu-id="458ab-115">이러한 비디오는 기본적인 내용을 다루지만 데이터 과학에 관심이 있든, 데이터 과학자와 함께 작업하든 상관없이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="458ab-115">These videos are basic but useful, whether you're interested in doing data science or you work with data scientists.</span></span>

* <span data-ttu-id="458ab-116">비디오 1: [데이터 과학으로 답변할 수 있는 5가지 질문](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-the-5-questions-data-science-answers) *(5분 14초)*</span><span class="sxs-lookup"><span data-stu-id="458ab-116">Video 1: [The 5 questions data science answers](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-the-5-questions-data-science-answers) *(5 min 14 sec)*.</span></span>

* <span data-ttu-id="458ab-117">비디오 2: [데이터 과학에 사용할 수 있게 데이터가 준비되었나요?](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-is-your-data-ready-for-data-science)</span><span class="sxs-lookup"><span data-stu-id="458ab-117">Video 2: [Is your data ready for data science?](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-is-your-data-ready-for-data-science)</span></span> <span data-ttu-id="458ab-118">*(4분 56초)*</span><span class="sxs-lookup"><span data-stu-id="458ab-118">*(4 min 56 sec)*</span></span>

* <span data-ttu-id="458ab-119">비디오 3: [데이터로 대답할 수 있는 질문하기](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-ask-a-question-you-can-answer-with-data) *(4분 17초)*</span><span class="sxs-lookup"><span data-stu-id="458ab-119">Video 3: [Ask a question you can answer with data](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-ask-a-question-you-can-answer-with-data) *(4 min 17 sec)*</span></span>

* <span data-ttu-id="458ab-120">비디오 4: [단순 모델을 사용하여 답변 예측](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-predict-an-answer-with-a-simple-model) *(7분 42초)*</span><span class="sxs-lookup"><span data-stu-id="458ab-120">Video 4: [Predict an answer with a simple model](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-predict-an-answer-with-a-simple-model) *(7 min 42 sec)*</span></span>

* <span data-ttu-id="458ab-121">비디오 5: [데이터 과학을 수행하기 위해 다른 사람의 작품 복사](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-copy-other-peoples-work-to-do-data-science) *(3분 18초)*</span><span class="sxs-lookup"><span data-stu-id="458ab-121">Video 5: [Copy other people's work to do data science](https://docs.microsoft.com/azure/machine-learning/studio/data-science-for-beginners-copy-other-peoples-work-to-do-data-science) *(3 min 18 sec)*</span></span>

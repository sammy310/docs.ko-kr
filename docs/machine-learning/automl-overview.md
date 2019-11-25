---
title: ML.NET을 통해 자동화된 기계 학습
description: 자동 모델 선택 및 학습에 대한 개요
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: 263004e67bf88af4182788e8c74cb410460e9201
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971410"
---
# <a name="automated-machine-learning-with-mlnet"></a><span data-ttu-id="94667-103">ML.NET을 통해 자동화된 기계 학습</span><span class="sxs-lookup"><span data-stu-id="94667-103">Automated machine learning with ML.NET</span></span>

<span data-ttu-id="94667-104">자동화된 기계 학습은 자동 모델 선택과 학습을 수행하는 ML.NET 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="94667-104">Automated machine learning is a feature of ML.NET that performs automatic model selection and training.</span></span> <span data-ttu-id="94667-105">기계 학습 작업을 지정하고 데이터 세트를 제공하면 자동 ML이 최적의 메트릭이 있는 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94667-105">You specify the machine learning task and supply a dataset, and automated ML chooses the model with the best metrics.</span></span> <span data-ttu-id="94667-106">다음을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="94667-106">It outputs:</span></span>

- <span data-ttu-id="94667-107">예측 애플리케이션에 로드할 수 있는 모델 파일</span><span class="sxs-lookup"><span data-stu-id="94667-107">a model file that can be loaded into your prediction application</span></span>
- <span data-ttu-id="94667-108">예측을 수행하는 애플리케이션 코드</span><span class="sxs-lookup"><span data-stu-id="94667-108">application code to make predictions</span></span>
- <span data-ttu-id="94667-109">기능 선택 및 모델 학습(모델 이해를 위해)에 사용되는 소스 코드</span><span class="sxs-lookup"><span data-stu-id="94667-109">the source code used for feature selection and model training (to understand the model)</span></span>

> [!NOTE]
> <span data-ttu-id="94667-110">이 기능은 현재 미리 보기로 제공되며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94667-110">This feature is currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="94667-111">자동화된 ML은 현재 이진 분류, 다중 클래스 분류, 회귀의 기게 학습 [작업](resources/tasks.md)으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="94667-111">Automated ML is currently limited to the machine learning [tasks](resources/tasks.md) of binary classification, multiclass classification, and regression.</span></span> <span data-ttu-id="94667-112">다른 기계 학습 작업은 향후 릴리스에서 지원될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94667-112">The other machine learning tasks will be supported in future releases.</span></span>

<span data-ttu-id="94667-113">세 가지 방법으로 자동화된 ML을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94667-113">There are three ways to use automated ML:</span></span>

1. <span data-ttu-id="94667-114">그래픽 사용자 인터페이스에서 [ML.NET 모델 작성기](automate-training-with-model-builder.md) 사용</span><span class="sxs-lookup"><span data-stu-id="94667-114">With a graphical user interface, with the [ML.NET Model Builder](automate-training-with-model-builder.md)</span></span>
1. <span data-ttu-id="94667-115">명령줄에서 [ML.NET CLI](automate-training-with-cli.md) 사용</span><span class="sxs-lookup"><span data-stu-id="94667-115">On the command line, with the [ML.NET CLI](automate-training-with-cli.md)</span></span>
1. <span data-ttu-id="94667-116">애플리케이션에서 [자동화된 ML API](how-to-guides/how-to-use-the-automl-api.md) 사용</span><span class="sxs-lookup"><span data-stu-id="94667-116">Via an application, with the [automated ML API](how-to-guides/how-to-use-the-automl-api.md)</span></span>

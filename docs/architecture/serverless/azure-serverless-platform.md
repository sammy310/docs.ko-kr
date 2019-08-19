---
title: Azure 서버를 사용 하지 않는 플랫폼-서버 리스 앱
description: Azure 서버를 사용 하지 않는 플랫폼은 이벤트 트리거된 인스턴트 확장 코드, 클라우드 기반 pub/sub, 워크플로 오케스트레이션 등을 비롯 한 기능을 제공 합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 43646db564ae31d26fe59e1ad7392e51d2d4e953
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577596"
---
# <a name="azure-serverless-platform"></a><span data-ttu-id="531f5-103">Azure 서버를 사용 하지 않는 플랫폼</span><span class="sxs-lookup"><span data-stu-id="531f5-103">Azure serverless platform</span></span>

<span data-ttu-id="531f5-104">Azure 서버 리스 플랫폼은 Azure Functions, Logic Apps 및 Event Grid를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="531f5-104">The Azure serverless platform includes Azure Functions, Logic Apps, and Event Grid.</span></span> <span data-ttu-id="531f5-105">이러한 서비스는 함께 작동 하며 수많은 다른 리소스와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="531f5-105">These services work together and connect with myriad other resources.</span></span> <span data-ttu-id="531f5-106">서버를 사용 하지 않는 플랫폼은 데이터베이스 및 저장소에서 분석 및 기계 학습/인공 지능에 이르기까지 모든 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="531f5-106">The serverless platform works with everything from databases and storage to analytics and machine learning/artificial intelligence.</span></span>

<span data-ttu-id="531f5-107">진단 추적 및 원격 분석을 캡처하기 위해 서버 리스 플랫폼 Application Insights 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="531f5-107">You can also use Application Insights, a serverless platform for capturing diagnostic traces and telemetry.</span></span> <span data-ttu-id="531f5-108">Application Insights는 서버 리스 구현 뿐만 아니라 모든 유형의 응용 프로그램 (데스크톱, 모바일 또는 웹)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="531f5-108">Application Insights are available to applications of all types (desktop, mobile, or web) as well as serverless implementations.</span></span> <span data-ttu-id="531f5-109">플랫폼은 다음 다이어그램에서 시각화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="531f5-109">The platform is visualized in the following diagram:</span></span>

![Azure 서버를 사용 하지 않는 플랫폼](./media/azure-serverless-platform.png)

<span data-ttu-id="531f5-111">이 장에서는 각 구성 요소의 기본 사항을 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="531f5-111">This chapter breaks down the fundamentals of each component.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="531f5-112">[이전](serverless-design-examples.md)
>[다음](azure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="531f5-112">[Previous](serverless-design-examples.md)
[Next](azure-functions.md)</span></span>

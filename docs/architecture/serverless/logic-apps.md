---
title: Azure Logic Apps 서버 리스 앱
description: Azure Logic Apps 클라우드 서비스 및 온-프레미스 시스템에서 앱과 데이터를 통합 하는 자동화 된 확장 가능 워크플로를 구축할 수 있습니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577456"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="7e9ca-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="7e9ca-103">Azure Logic Apps</span></span>

<span data-ttu-id="7e9ca-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) 은 클라우드 서비스와 온-프레미스 시스템 간에 앱과 데이터를 통합 하는 자동화 된 워크플로를 빌드하기 위한 서버 리스 엔진을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="7e9ca-105">비주얼 디자이너를 사용 하 여 워크플로를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="7e9ca-106">이벤트 또는 타이머에 따라 워크플로를 트리거하고 통합 응용 프로그램에 대 한 커넥터를 활용 하 여 B2B (기업 간) 통신을 용이 하 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="7e9ca-107">Logic Apps는 Azure Functions와 긴밀 하 게 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic Apps 로고](./media/logic-apps-logo.png)

<span data-ttu-id="7e9ca-109">클라우드 서비스 (예: 함수)를 클라우드 리소스 (예: 큐 및 데이터베이스)와 연결 하는 것 이상의 작업을 수행할 수 Logic Apps.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="7e9ca-110">온-프레미스 게이트웨이를 사용 하 여 온-프레미스 워크플로를 오케스트레이션 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="7e9ca-111">예를 들어 논리 앱을 사용 하 여 워크플로의 클라우드 기반 이벤트 또는 조건부 논리에 대 한 응답으로 온-프레미스 SQL 저장 프로시저를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="7e9ca-112">[Azure 온-프레미스 데이터 게이트웨이를 사용 하 여 온-프레미스 데이터 원본에 연결 하는](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![Logic Apps 아키텍처](./media/logic-apps-architecture.png)

<span data-ttu-id="7e9ca-114">Azure Functions와 마찬가지로 트리거를 사용 하 여 논리 앱 워크플로를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="7e9ca-115">선택할 수 있는 여러 트리거가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="7e9ca-116">다음 캡처는 사용 가능한 수백 개의 인기 있는 것 중 몇 가지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Logic Apps 트리거](./media/logic-app-triggers.png)

<span data-ttu-id="7e9ca-118">앱이 트리거된 후에는 비주얼 디자이너를 사용 하 여 단계, 루프, 조건 및 작업을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="7e9ca-119">이전 단계의 모든 데이터 수집 이후 단계에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="7e9ca-120">다음 워크플로는 CosmosDB 데이터베이스에서 Url을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="7e9ca-121">의 `t.co` 호스트를 사용 하 여 해당 항목을 찾은 다음 Twitter에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="7e9ca-122">해당 트 윗를 찾으면 함수를 호출 하 여 관련 트 윗 문서를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![논리 앱 워크플로](./media/logic-app-workflow.png)

<span data-ttu-id="7e9ca-124">Logic Apps 대시보드는 워크플로를 실행 하는 기록과 각 실행이 성공적으로 완료 되었는지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="7e9ca-125">지정 된 실행으로 이동 하 고 각 단계에서 문제 해결을 위해 사용 하는 데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="7e9ca-126">Logic Apps는 편집할 수 있는 기존 템플릿도 제공할 뿐만 아니라 복잡 한 엔터프라이즈 워크플로에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="7e9ca-127">자세한 내용은 [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7e9ca-128">[이전](application-insights.md)
>[다음](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>

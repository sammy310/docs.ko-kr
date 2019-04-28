---
title: Azure Logic Apps-서버 리스 앱
description: Azure Logic Apps를 사용 하도록 앱을 통합 하는 확장성 있는 워크플로 자동화 된 빌드 설정 및 클라우드 데이터 서비스 및 온-프레미스 시스템입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 14670a8459db3b80b8fbe3139c2675321cf9592c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61712805"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="d1eff-103">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="d1eff-103">Azure Logic Apps</span></span>

<span data-ttu-id="d1eff-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) 온-프레미스 시스템 및 앱 및 클라우드 서비스 간에 데이터를 통합 하는 자동화 된 워크플로 구축 하는 서버 리스 엔진을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="d1eff-105">비주얼 디자이너를 사용 하 여 워크플로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="d1eff-106">이벤트 나 타이머 및 통합 응용 프로그램을 활용 하 여 커넥터를 기반으로 워크플로 트리거할 수 있으며 비즈니스 B2B 통신을 용이 하 게 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="d1eff-107">Logic Apps는 Azure Functions를 사용 하 여 원활 하 게 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic Apps 로고](./media/logic-apps-logo.png)

<span data-ttu-id="d1eff-109">클라우드 리소스 (예: 큐 및 데이터베이스)를 사용 하 여 논리 앱에 클라우드 서비스 (예: 함수)를 연결 하기만 이상 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="d1eff-110">온-프레미스 게이트웨이 사용 하 여 온-프레미스 워크플로 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="d1eff-111">예를 들어, 온-프레미스 SQL 저장 프로시저를 사용 하 여 클라우드 기반 이벤트에 대 한 응답에서 또는 워크플로에 조건부 논리를 트리거하는 논리 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="d1eff-112">에 대해 자세히 알아보세요 [Azure 온-프레미스 데이터 게이트웨이 사용 하 여 온-프레미스 데이터 원본에 연결할](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![논리 앱 아키텍처](./media/logic-apps-architecture.png)

<span data-ttu-id="d1eff-114">Azure Functions와 같은 트리거를 사용 하 여 논리 앱 워크플로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="d1eff-115">많은 트리거가에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="d1eff-116">다음 캡처에는 몇 가지 더 인기 있는 항목의 수백 사용할 수 있는 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![논리 앱 트리거](./media/logic-app-triggers.png)

<span data-ttu-id="d1eff-118">앱 트리거되면 단계, 루프, 조건 및 작업을 구축 하는 비주얼 디자이너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="d1eff-119">이전 단계에서 수집한 모든 데이터는 이후 단계에서 사용 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="d1eff-120">다음 워크플로에서 CosmosDB 데이터베이스에서 Url을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="d1eff-121">호스트를 사용 하 여 항목을 찾으면 `t.co` twitter에 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="d1eff-122">해당 트 윗을 찾으면 업데이트 문서는 관련된 트 윗을 사용 하 여 함수를 호출 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![논리 앱 워크플로](./media/logic-app-workflow.png)

<span data-ttu-id="d1eff-124">Logic Apps 대시보드 워크플로 및 각 실행 여부 완료 성공적으로 실행 기록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="d1eff-125">지정된 된 실행에 탐색 및 문제 해결을 위한 각 단계에서 사용 된 데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="d1eff-126">Logic Apps는 기존 템플릿을 편집할 수 있으며 복잡 한 엔터프라이즈 워크플로에 대 한 적합도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="d1eff-127">자세한 내용은 참조 하세요 [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1eff-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d1eff-128">[이전](application-insights.md)
>[다음](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="d1eff-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>
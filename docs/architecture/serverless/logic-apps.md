---
title: Azure Logic Apps - 서버리스 앱
description: Azure Logic Apps를 사용하여 클라우드 서비스와 온-프레미스 시스템 전반에서 앱과 데이터를 통합하는 자동화된 확장성 있는 워크플로를 작성할 수 있습니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577456"
---
# <a name="azure-logic-apps"></a>Azure Logic Apps

[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)는 클라우드 서비스와 온-프레미스 시스템 간에 앱과 데이터를 통합하는 자동화된 워크플로를 빌드하기 위한 서버리스 엔진을 제공합니다. 비주얼 디자이너를 사용하여 워크플로를 빌드합니다. 이벤트 또는 타이머에 따라 워크플로를 트리거하고 통합 애플리케이션에 대한 커넥터를 활용하여 B2B(기업 간) 통신을 용이하게 할 수 있습니다. Logic Apps는 Azure Functions와 긴밀하게 통합됩니다.

![Azure Logic Apps 로고](./media/logic-apps-logo.png)

Logic Apps는 단순히 클라우드 서비스(예: 함수)를 클라우드 리소스(예: 큐 및 데이터베이스)와 연결하는 것 이상의 역할을 수행할 수 있습니다. 온-프레미스 게이트웨이를 사용하여 온-프레미스 워크플로를 오케스트레이션할 수도 있습니다. 예를 들어 논리 앱을 사용하여 워크플로의 클라우드 기반 이벤트 또는 조건부 논리에 대한 응답으로 온-프레미스 SQL 저장 프로시저를 트리거할 수 있습니다. [Azure 온-프레미스 데이터 게이트웨이를 사용하여 온-프레미스 데이터 원본에 연결](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)을 자세히 알아보세요.

![Logic Apps 아키텍처](./media/logic-apps-architecture.png)

Azure Functions와 마찬가지로 트리거를 사용하여 논리 앱 워크플로를 시작합니다. 다양한 트리거 중에서 선택할 수 있습니다. 다음 캡처에는 사용 가능한 수백 개의 인기 있는 트리거 중 몇 개만 나와 있습니다.

![Logic Apps 트리거](./media/logic-app-triggers.png)

앱이 트리거된 후에는 비주얼 디자이너를 사용하여 단계, 루프, 조건 및 작업을 빌드할 수 있습니다. 이전 단계에서 수집된 모든 데이터를 이후 단계에서 사용할 수 있습니다. 다음 워크플로는 CosmosDB 데이터베이스에서 URL을 로드합니다. 호스트가 `t.co`인 항목을 찾은 다음 Twitter에서 검색합니다. 해당 트윗를 찾으면 함수를 호출하여 관련 트윗으로 문서를 업데이트합니다.

![논리 앱 워크플로](./media/logic-app-workflow.png)

Logic Apps 대시보드에는 워크플로 실행 기록과 각 실행이 성공적으로 완료되었는지 여부가 표시됩니다. 문제 해결을 위해 특정 실행으로 이동하고 각 단계에서 사용된 데이터를 검사할 수 있습니다. 또한 Logic Apps는 편집할 수 있고 복잡한 엔터프라이즈 워크플로에 매우 적합한 기존 템플릿도 제공합니다.

자세한 내용을 알아보려면 [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)를 참조하세요.

>[!div class="step-by-step"]
>[이전](application-insights.md)
>[다음](event-grid.md)

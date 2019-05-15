---
title: Azure Logic Apps-서버 리스 앱
description: Azure Logic Apps를 사용 하도록 앱을 통합 하는 확장성 있는 워크플로 자동화 된 빌드 설정 및 클라우드 데이터 서비스 및 온-프레미스 시스템입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638792"
---
# <a name="azure-logic-apps"></a>Azure Logic Apps

[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) 온-프레미스 시스템 및 앱 및 클라우드 서비스 간에 데이터를 통합 하는 자동화 된 워크플로 구축 하는 서버 리스 엔진을 제공 합니다. 비주얼 디자이너를 사용 하 여 워크플로 빌드합니다. 이벤트 나 타이머 및 통합 응용 프로그램을 활용 하 여 커넥터를 기반으로 워크플로 트리거할 수 있으며 비즈니스 B2B 통신을 용이 하 게 수 있습니다. Logic Apps는 Azure Functions를 사용 하 여 원활 하 게 통합 됩니다.

![Azure Logic Apps 로고](./media/logic-apps-logo.png)

클라우드 리소스 (예: 큐 및 데이터베이스)를 사용 하 여 논리 앱에 클라우드 서비스 (예: 함수)를 연결 하기만 이상 가능 합니다. 온-프레미스 게이트웨이 사용 하 여 온-프레미스 워크플로 조정할 수도 있습니다. 예를 들어, 온-프레미스 SQL 저장 프로시저를 사용 하 여 클라우드 기반 이벤트에 대 한 응답에서 또는 워크플로에 조건부 논리를 트리거하는 논리 앱을 사용할 수 있습니다. 에 대해 자세히 알아보세요 [Azure 온-프레미스 데이터 게이트웨이 사용 하 여 온-프레미스 데이터 원본에 연결할](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)합니다.

![논리 앱 아키텍처](./media/logic-apps-architecture.png)

Azure Functions와 같은 트리거를 사용 하 여 논리 앱 워크플로 시작 합니다. 많은 트리거가에서 선택할 수 있습니다. 다음 캡처에는 몇 가지 더 인기 있는 항목의 수백 사용할 수 있는 보여 줍니다.

![논리 앱 트리거](./media/logic-app-triggers.png)

앱 트리거되면 단계, 루프, 조건 및 작업을 구축 하는 비주얼 디자이너를 사용할 수 있습니다. 이전 단계에서 수집한 모든 데이터는 이후 단계에서 사용 하 여 사용할 수 있습니다. 다음 워크플로에서 CosmosDB 데이터베이스에서 Url을 로드합니다. 호스트를 사용 하 여 항목을 찾으면 `t.co` twitter에 검색 합니다. 해당 트 윗을 찾으면 업데이트 문서는 관련된 트 윗을 사용 하 여 함수를 호출 하 여 합니다.

![논리 앱 워크플로](./media/logic-app-workflow.png)

Logic Apps 대시보드 워크플로 및 각 실행 여부 완료 성공적으로 실행 기록을 보여 줍니다. 지정된 된 실행에 탐색 및 문제 해결을 위한 각 단계에서 사용 된 데이터를 검사할 수 있습니다. Logic Apps는 기존 템플릿을 편집할 수 있으며 복잡 한 엔터프라이즈 워크플로에 대 한 적합도 제공 합니다.

자세한 내용은 참조 하세요 [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)합니다.

>[!div class="step-by-step"]
>[이전](application-insights.md)
>[다음](event-grid.md)

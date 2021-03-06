---
title: 요약
description: ASP.NET MVC 및 Web API 2 앱을 ASP.NET Core로 이식 하기 위한 요약 및 주요 내용 집합입니다.
author: ardalis
ms.date: 12/16/2020
ms.openlocfilehash: 596ab8621008d1cdc16d841e8faede5f4a1fdd16
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401276"
---
# <a name="summary"></a>요약

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

이 책에는 ASP.NET Core .NET Framework에서 실행 되는 조직의 기존 ASP.NET 앱을 이식 하는 데 적합 한지 여부를 결정 하는 데 필요한 리소스가 제공 됩니다. .NET Core로 마이그레이션하는 것이 적합 한 경우와 앱을 .NET Framework에 보관 하는 것이 적합할 수 있는 경우를 선택 하기 위한 [중요 한 고려 사항](migration-considerations.md) 에 대해 알아보았습니다. .NET Core 버전과 해당 기능 및 호환성를 .NET Framework 사용 하는 경우의 차이가 있으며, [앱에 대 한 .Net core의 올바른 버전을 선택 하는 방법을](choose-net-core-version.md)배웠습니다.

큰 앱을 이식 하는 경우에는 상당한 위험 및 노력이 수반 될 수도 있습니다. 프로덕션 환경에서 실행 되는 부분적으로 마이그레이션된 앱을 유지 하기 위한 몇 가지 [배포 전략과](deployment-strategies.md) 함께 하나 이상의 [증분 마이그레이션 전략](incremental-migration-strategies.md) 을 사용 하 여이 위험을 완화 하는 방법을 배웠습니다.

[ASP.NET와 ASP.NET Core 간에는 많은 아키텍처 차이가](architectural-differences.md)있습니다. 2 장에서는 이러한 차이점 중 상당수와 앱의 마이그레이션과 어떻게 관련 되는지에 대해 알아보았습니다. 이 장에서는 [앱 시작](app-startup-differences.md) 및 하위 수준 [미들웨어](middleware-modules-handlers.md) 부터 상위 수준 [컨트롤러](controller-differences.md) 및 [Web API의 차이점과](webapi-differences.md) 새로운 기능에 이르기까지 모든 항목을 [자세히](testing-differences.md)설명 합니다.

대형 앱은 종종 많은 프로젝트와 패키지로 구성 되며 종속성은 쉽게 마이그레이션할 수 있는 방법을 결정 하는 데 중요 한 역할을 할 수 있습니다. [3 장에서](migrate-large-solutions.md) 는 [프로젝트를 마이그레이션할 순서](identify-migration-sequence.md) 와 [앱의 종속성을 이해 하 고 업데이트 하는 방법을](understand-update-dependencies.md)식별 하는 데 도움을 주었습니다. 또한 [프로덕션 환경에서 실행 되는 동안 앱을 마이그레이션하기 위한 추가 전략에 대해](strategies-migrating-in-production.md)자세히 설명 합니다.

[4 장에서는 실제 ASP.NET MVC 참조 앱이 ASP.NET Core로 마이그레이션된 방법을 살펴보았습니다](example-migration-eshop.md). 이 장에서는 기존 앱을 사용 하는 데 필요한 모든 변경 내용에 대 한 자세한 분석을 포함 하 여 ASP.NET Core에서 실행 되도록 합니다. 포팅 프로세스와 그에 대 한 구체적인 정보 중 일부에 대 한 구체적인 질문이 있는 경우 다시 참조 하세요.

마지막으로 [IIS에 초점을 맞춘 5 장 특정 배포 시나리오를 설명](deployment-scenarios.md)합니다. 기존 IIS 웹 서버를 사용 하 여 앱의 공용 Url을 일관성 있게 유지 하면서 ASP.NET Core 하도록 이식 된 앱의 일부를 호스트 하는 방법을 살펴보았습니다. IIS에는 응용 프로그램에서 공개 하는 Url을 변경 하지 않고 여러 버전의 사이트를 side-by-side로 또는 다른 서버에도 호스트할 수 있도록 하는 URL 재작성 및 요청 라우팅에 대 한 뛰어난 지원이 포함 되어 있습니다.

>[!div class="step-by-step"]
>[이전](deployment-scenarios.md)

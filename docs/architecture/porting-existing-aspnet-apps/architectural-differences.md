---
title: ASP.NET MVC와 ASP.NET Core의 아키텍처 차이점
description: ASP.NET와 ASP.NET Core 간의 아키텍처 차이를 검토 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 96477f2393482380eee9891e9b2dbbb6445e15bd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401820"
---
# <a name="architectural-differences-between-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC와 ASP.NET Core의 아키텍처 차이점

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

.NET Framework와 ASP.NET Core ASP.NET MVC 간에는 많은 아키텍처 차이가 있습니다. 팀에서 ASP.NET MVC 앱을 ASP.NET Core로 이식 하는 데 관련 된 작업을 평가할 때 이러한 차이를 광범위 하 게 이해 하는 것이 중요 합니다. 이 장에서는 ASP.NET Core ASP.NET MVC와 크게 다른 방법에 대해 살펴봅니다.

## <a name="breaking-changes"></a>주요 변경 내용

.NET Core는 .NET Framework의 플랫폼 간 재작성입니다. [두 프레임 워크 사이에는 몇 가지 주요 변경 사항이](../../core/compatibility/fx-core.md)있습니다. 다음 섹션에서는 ASP.NET MVC와 ASP.NET Core 앱이 설계 및 개발 되는 방식 간의 구체적인 차이점을 식별 합니다. 또한 설명서를 검토 하 여 변경 해야 할 수 있는 사용 중인 프레임 워크 라이브러리를 확인 합니다. 대부분의 경우 .NET Framework와 .NET Core 사이에서 남은 간격을 채우도록 대체 NuGet 패키지가 존재 합니다. 드문 경우 지만 타사 솔루션을 찾거나 새로운 사용자 지정 코드를 구현 하 여 비 호환성 문제를 해결 해야 할 수 있습니다.

>[!div class="step-by-step"]
>[이전](additional-migration-resources.md)
>[다음](app-startup-differences.md)

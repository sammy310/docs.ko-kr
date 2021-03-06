---
title: .NET Core로 앱 포팅 소개
description: 이 장에서는 기존 ASP.NET apps를 .NET Core로 마이그레이션하기를 고려 하는 팀에 대 한 고려 사항 목록을 다룹니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: a346d1c693389cc4ca682b41a3b7fc094cfa5482
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401232"
---
# <a name="introduction-to-porting-apps-to-net-core"></a>.NET Core로 앱 포팅 소개

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

.NET Core는 .NET Framework에서 혁신 단계로 진행 됩니다. 플랫폼 간 지원에서 개발자 만족도까지 보드 전체에서 생산성까지 .NET Framework에 비해 이점을 제공 합니다. ASP.NET Core는 [2020 Stack Overflow 개발자 설문 조사](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks)에서 좋아했던 웹 프레임 워크에도 투표 했습니다. 마이그레이션을 고려해 야 하는 강력한 이유가 분명히 있습니다.

.Net [Core가 .net의 미래](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/)임을 명심 해야 합니다. 이 문서를 인용 하려면:

> 새 앱은 .NET Core를 기반으로 빌드해야 합니다. .NET Core는 .NET에 대 한 향후 투자를 발생 시킬 수 있습니다. 기존 앱은 지원 되는 .NET Framework에 유지 해도 됩니다. .NET의 새로운 기능을 활용 하려는 기존 앱은 .NET Core로 이동 하는 것이 좋습니다. 앞으로 계획할 때 플랫폼에 훨씬 더 많은 기능을 제공 하 게 될 예정입니다.

그러나 앱을 ASP.NET Core로 업그레이드 하는 데는 몇 가지 노력이 필요 합니다. 이러한 작업은 비즈니스 가치 및 목표에 따라 균형을 맞춰야 합니다. .NET Framework 앱은 곧 Windows에 기본적으로 제공 되는 기능을 제공 합니다. .NET Core로의 마이그레이션을 결정 하기 전에 고려해 야 할 몇 가지 질문은 무엇 인가요? 예상 이점은 무엇 인가요? 절충은 무엇 인가요? 얼마나 많은 노력이 필요 한가요? 이러한 명백한 질문은 단지 시작 이지만 팀에서 현재 및 내일 앱에 대 한 고객의 요구를 지 원하는 방법을 고려 하는 것이 좋습니다.

- .NET Core로의 마이그레이션이 적절 합니까?
- .NET Framework를 그대로 유지 하는 것이 적합 한가요?
- 앱이 ASP.NET Core 2.1를 스테핑 돌로 대상으로 지정 해야 하나요?
- 팀에서 대상으로 적합 한 .NET Core 버전을 어떻게 선택 하나요?
- 대량 앱의 증분 마이그레이션에 권장 되는 전략은 무엇 인가요?
- .NET Core로 이식할 때 고려해 야 할 배포 전략은 무엇 인가요?
- 추가 리소스는 어디에서 찾을 수 있나요?

이 소개 장에서는 이후 챕터에서 보다 구체적인 기술 고려 사항으로 이동 하기 전에 이러한 모든 질문과 대답을 다룹니다.

## <a name="references"></a>참조

- [2020 Stack Overflow 개발자 설문 조사 가장 좋아했던 웹 프레임 워크](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks)
- [.Net Core는 .NET의 미래입니다.](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/)

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](migration-considerations.md)

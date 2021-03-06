---
title: 미들웨어를 모듈 및 처리기와 비교
description: 이 섹션에서는 요청 처리 파이프라인에 대 한 미들웨어를 정의 하는 ASP.NET Core 앱에서 처리기 및 모듈을 사용 하는 ASP.NET apps에 대 한 구조의 차이점을 살펴봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 040ae49d1307ef4dcc9dbf49b20544e9cd2bc913
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401735"
---
# <a name="compare-middleware-to-modules-and-handlers"></a>미들웨어를 모듈 및 처리기와 비교

기존 ASP.NET MVC 또는 Web API 앱에서 OWIN/Katana를 사용 하는 경우 미들웨어의 개념에 이미 익숙하고 ASP.NET Core로 이식 하는 것이 매우 간단 합니다. 그러나 대부분의 ASP.NET 앱은 미들웨어 대신 HTTP 모듈 및 HTTP 처리기를 사용 합니다. 이러한 작업을 ASP.NET Core로 마이그레이션하려면 추가 작업이 필요 합니다.

## <a name="aspnet-modules-and-handlers"></a>ASP.NET 모듈 및 처리기

[Http 모듈 및 http 처리기](/troubleshoot/aspnet/http-modules-handlers) 는 ASP.NET 아키텍처의 필수적인 부분입니다. 요청을 처리 하는 동안 각 요청은 여러 HTTP 모듈 (예: 인증 모듈 및 세션 모듈)에 의해 처리 된 다음 단일 HTTP 처리기에 의해 처리 됩니다. 처리기가 요청을 처리 한 후 요청은 HTTP 모듈을 통해 다시 흐릅니다.

앱에서 사용자 지정 HTTP 모듈 또는 HTTP 처리기를 사용 하는 경우 ASP.NET Core로 마이그레이션하기 위한 계획이 필요 합니다. 가장 가능성이 높은 ASP.NET Core는 미들웨어입니다.

## <a name="aspnet-core-middleware"></a>ASP.NET Core 미들웨어

ASP.NET Core는 각 앱의 메서드에서 요청 파이프라인을 정의 `Configure` 합니다. 이 요청 파이프라인은 응용 프로그램에서 들어오는 요청을 처리 하는 방법을 정의 하 고, 궁극적으로 메서드가 종료 될 때까지 다음 메서드를 호출 하는 파이프라인의 각 메서드를 사용 하 여, *미들웨어* 의 체인이 종료 되 고 반환 됩니다. 미들웨어는 모든 요청을 대상으로 하거나 요청 된 경로 또는 다른 요인을 기반으로 특정 요청에만 매핑되도록 구성할 수 있습니다. `Configure`응용 프로그램의 메서드에서 완전히 구성 하거나 별도의 클래스에서 구현할 수 있습니다.

HTTP 모듈을 사용 하는 ASP.NET MVC 앱의 동작은 [사용자 지정 미들웨어](/aspnet/core/fundamentals/middleware/?preserve-view=true&view=aspnetcore-3.1)에 가장 적합할 수 있습니다. 사용자 지정 HTTP 처리기는 동일한 경로에 응답 하는 사용자 지정 경로 또는 끝점으로 바꿀 수 있습니다.

## <a name="references"></a>참조

- [ASP.NET HTTP 모듈 및 HTTP 처리기](/troubleshoot/aspnet/http-modules-handlers)
- [ASP.NET Core 미들웨어](/aspnet/core/fundamentals/middleware/?preserve-view=true&view=aspnetcore-3.1)

>[!div class="step-by-step"]
>[이전](dependency-injection-differences.md)
>[다음](configuration-differences.md)

---
title: ASP.NET Web Forms 앱 마이그레이션 전략
description: 팀에서 ASP.NET Web Forms 앱을 .NET Core로 마이그레이션하는 데 사용할 수 있는 전략은 무엇 인가요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 0b37a37f047de50c347313be14a2228838da6995
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401281"
---
# <a name="strategies-for-migrating-aspnet-web-forms-apps"></a>ASP.NET Web Forms 앱 마이그레이션 전략

이 책에서는 large ASP.NET MVC 및 Web API apps를 .NET Core로 마이그레이션하기 위한 지침을 제공 합니다. 이러한 ASP.NET 앱 중 일부에는 해결 해야 하는 Web Forms (*.aspx*) 페이지도 포함 될 수 있습니다. ASP.NET Web Forms는 .NET Core에서 지원 되지 않으며 ASP.NET 웹 페이지 되지 않습니다. 일반적으로 ASP.NET Core로 이식할 때 이러한 페이지의 기능을 다시 작성 해야 합니다. 그러나 전체 작업을 줄일 수 있도록 이러한 마이그레이션 전후에 적용할 수 있는 몇 가지 전략이 있습니다.

Web Forms는 상당한 시간 동안 계속 지원 됩니다. 한 가지 옵션은이 기능을 ASP.NET 4.x 앱에 보관 하는 것입니다.

## <a name="separate-business-logic-and-other-concerns"></a>별도의 비즈니스 논리 및 기타 고려 사항

ASP.NET Web Forms 페이지의 코드는 더 효율적입니다. 가능 하면 별도 클래스 라이브러리에서 가장 적합 한 별도의 클래스에서 데이터 액세스와 같은 비즈니스 논리 및 기타 문제를 유지 합니다. 이러한 클래스 라이브러리는 .NET Standard 하 고 ASP.NET Core 앱에서 사용 하도록 이식할 수 있습니다.

## <a name="implement-client-behavior-and-web-apis"></a>클라이언트 동작 및 웹 Api 구현

API 호출을 통해 Web Forms 또는 브라우저에서 논리를 구현 하는 중에서 선택 하는 것이 좋습니다. 후자를 선호 합니다. ASP.NET Core에 대 한 Api 마이그레이션은 지원 됩니다. 클라이언트 쪽 동작은 앱에서 사용 하는 서버 쪽 스택과는 독립적 이어야 합니다. 이 접근 방식을 사용 하면 더 응답성이 뛰어난 사용자 환경을 제공 하는 추가 이점을 누릴 수 있습니다.

## <a name="consider-blazor"></a>Blazor 고려

Blazor를 사용 하면 JavaScript 대신 c #을 사용 하 여 대화형 웹 Ui를 빌드할 수 있습니다. 이 서버는 weasembmbommbmbmbomommbmbomomomomomomomomomomom ASP.NET Web Forms apps는 Blazor 앱에 대해 페이지 단위로 이식할 수 있습니다. Blazor에 Web Forms apps를 이식 하는 방법에 대 한 자세한 내용은 [Blazor for ASP.NET Web Forms 개발자](https://devblogs.microsoft.com/aspnet/blazor-aspnet-webforms-ebook/)를 참조 하세요. 또한 많은 Web Forms 컨트롤이 오픈 소스 커뮤니티 프로젝트인 [Blazor Web Forms 구성 요소의](https://fritzandfriends.github.io/BlazorWebFormsComponents/)일부로 Blazor으로 이식 되었습니다. 이러한 구성 요소를 사용 하면 기본 제공 Web Forms 컨트롤을 사용 하는 경우에도 Web Forms 페이지를 Blazor에 더 쉽게 이식할 수 있습니다.

## <a name="summary"></a>요약

ASP.NET Web Forms에서 ASP.NET Core로 직접 마이그레이션하는 것은 지원 되지 않습니다. 그러나 ASP.NET Core를 쉽게 이동할 수 있는 전략이 있습니다. 다음을 수행 하 여 Web Forms 기능을 ASP.NET Core 성공적으로 마이그레이션할 수 있습니다.

* 비 웹 기능을 프로젝트에서 제외 합니다.
* 가능 하면 web Api를 사용 합니다.
* 최신 UI를 위한 옵션으로 Blazor를 고려 합니다.

## <a name="references"></a>참조

- [무료 e-learning: Blazor for ASP.NET Web Forms 개발자](https://devblogs.microsoft.com/aspnet/blazor-aspnet-webforms-ebook/)
- [Blazor Web Forms 구성 요소 (커뮤니티 프로젝트)](https://fritzandfriends.github.io/BlazorWebFormsComponents/)

>[!div class="step-by-step"]
>[이전](incremental-migration-strategies.md)
>[다음](deployment-strategies.md)

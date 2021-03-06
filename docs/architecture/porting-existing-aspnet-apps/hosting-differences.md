---
title: ASP.NET MVC와 ASP.NET Core 간의 호스팅 차이점
description: ASP.NET MVC 앱을 호스트 하는 방법 및 ASP.NET Core 앱 간의 차이점에 대 한 개요입니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 402dd5782cb215545ff2ef13f97ec269b8a2540b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401766"
---
# <a name="hosting-differences-between-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC와 ASP.NET Core 간의 호스팅 차이점

ASP.NET MVC 앱은 IIS에서 호스팅되며 IIS 구성을 사용 하 여 해당 동작을 할 수 있습니다. 여기에는 종종 [IIS 모듈이](/iis/get-started/introduction-to-iis/iis-modules-overview)포함 됩니다. 앱을 검토 하 여 ASP.NET MVC에서 ASP.NET Core로 이식할 수 있도록 준비 하는 과정에서 팀은 해당 서버에 설치 된 IIS 모듈 목록에서 사용 중인 모듈 (있는 경우)을 확인 해야 합니다.

[ASP.NET Core 앱은 다양 한 서버에서 실행할 수 있습니다](/aspnet/core/fundamentals/servers/). 기본 플랫폼 간 서버 Kestrel을 선택 하는 것이 좋습니다. Kestrel에서 실행 되는 앱은 별도의 프로세스로 실행 되는 IIS에서 호스팅될 수 있습니다. Windows에서 응용 프로그램은 IIS에서 또는 HTTP.sys를 사용 하 여 실행할 수도 있습니다. 최상의 성능을 위해 일반적으로 Kestrel을 사용하는 것이 좋습니다. 앱이 인터넷에 노출되고 필수 기능이 Kestrel이 아닌 HTTP.sys에서 지원되는 시나리오에서 HTTP.sys를 사용할 수 있습니다.

Kestrel에는 iis 모듈에 해당 하는 기능이 없습니다. IIS에서 호스팅되는 앱은 IIS 모듈을 계속 사용할 수 있습니다. 동일한 동작을 수행 하기 위해 ASP.NET Core 앱 자체에서 구성 된 미들웨어가 일반적으로 사용 됩니다.

## <a name="references"></a>참조

- [IIS 모듈](/iis/get-started/introduction-to-iis/iis-modules-overview)
- [ASP.NET Core 서버](/aspnet/core/fundamentals/servers/)

>[!div class="step-by-step"]
>[이전](app-startup-differences.md)
>[다음](serving-static-files.md)

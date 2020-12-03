---
title: '호환성이 손상되는 변경: Blazor: ProtectedBrowserStorage 기능을 공유 프레임워크로 이동함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: ProtectedBrowserStorage 기능을 공유 프레임워크로 이동함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759731"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a>Blazor: ProtectedBrowserStorage 기능을 공유 프레임워크로 이동함

ASP.NET Core 5.0 RC2 릴리스의 일부로 `ProtectedBrowserStorage` 기능을 ASP.NET Core 공유 프레임워크로 이동했습니다.

## <a name="version-introduced"></a>도입된 버전

5.0 RC2

## <a name="old-behavior"></a>이전 동작

ASP.NET Core 5.0 Preview 8에서 이 기능은 [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) 패키지의 일부로 사용할 수 있지만 Blazor WebAssembly에서만 사용할 수 있었습니다.

ASP.NET Core 5.0 RC1에서는 이 기능을 `Microsoft.AspNetCore.App` 공유 프레임워크를 참조하는 [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) 패키지의 일부로 사용할 수 있게 되었습니다.

## <a name="new-behavior"></a>새 동작

ASP.NET Core 5.0 RC2에서는 이 기능을 참조하고 사용하는 데 NuGet 패키지 참조가 더 이상 필요하지 않습니다.

## <a name="reason-for-change"></a>변경 이유

고객에게 공유 프레임워크로의 이동이 필요한 사용자 환경에 더욱 적합합니다.

## <a name="recommended-action"></a>권장 조치

ASP.NET Core 5.0 RC1에서 업그레이드하는 경우 다음 단계를 완료하세요.

1. 프로젝트에서 `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` 패키지 참조를 제거합니다.
1. `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;`을 `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`로 바꿉니다.
1. `Startup` 클래스에서 `AddProtectedBrowserStorage`에 대한 호출을 제거합니다.

ASP.NET Core 5.0 Preview 8에서 업그레이드하는 경우 다음 단계를 완료하세요.

1. 프로젝트에서 `Microsoft.AspNetCore.Components.Web.Extensions` 패키지 참조를 제거합니다.
1. `using Microsoft.AspNetCore.Components.Web.Extensions;`을 `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`로 바꿉니다.
1. `Startup` 클래스에서 `AddProtectedBrowserStorage`에 대한 호출을 제거합니다.

## <a name="affected-apis"></a>영향을 받는 API

없음

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->

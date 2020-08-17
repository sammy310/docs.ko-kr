---
title: 상태 관리
description: ASP.NET Web Forms 및 Blazor에서 상태를 관리 하는 다양 한 방법을 알아봅니다.
author: csharpfritz
ms.author: jefritz
ms.date: 05/15/2020
ms.openlocfilehash: 2ca811f886c6a245ac16c2bd66a68ff16e5bfc44
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267726"
---
# <a name="state-management"></a>상태 관리

상태 관리는 Web Forms 응용 프로그램의 주요 개념으로, 뷰 상태, 세션 상태, 응용 프로그램 상태 및 포스트백 기능을 통해 쉽게 활용할 수 있습니다. 프레임 워크의 이러한 상태 저장 기능은 응용 프로그램에 필요한 상태 관리를 숨기고 응용 프로그램 개발자가 해당 기능을 제공 하는 데 집중할 수 있도록 합니다. ASP.NET Core 및 Blazor를 사용 하는 경우 이러한 기능 중 일부는 재배치 되 고 일부는 완전히 제거 되었습니다. 이 장에서는 상태를 유지 관리 하 고 Blazor의 새로운 기능을 사용 하 여 동일한 기능을 제공 하는 방법을 검토 합니다.

## <a name="request-state-management-with-viewstate"></a>ViewState를 사용 하 여 상태 관리 요청

Web Forms 응용 프로그램에서 상태 관리를 논의할 때 많은 개발자가 ViewState를 즉시 생각해 보겠습니다. Web Forms에서 ViewState는 인코딩된 텍스트 블록을 브라우저에 앞뒤로 전송 하 여 HTTP 요청 간의 콘텐츠 상태를 관리 합니다. ViewState 필드는 많은 요소가 포함 된 페이지의 콘텐츠로 인해 잠재적으로 크기가 몇 메가바이트까지 확장 될 수 있습니다.

Blazor 서버를 사용 하면 앱에서 서버와 지속적으로 연결을 유지 합니다. *회로*라고 하는 앱의 상태는 연결이 활성 상태인 것으로 간주 되는 동안 서버 메모리에 보관 됩니다. 상태는 사용자가 앱 또는 앱의 특정 페이지에서 벗어날 때만 삭제 됩니다. 활성 구성 요소의 모든 멤버는 서버와의 상호 작용 간에 사용할 수 있습니다.

이 기능에는 다음과 같은 몇 가지 이점이 있습니다.

- 구성 요소 상태는 쉽게 사용할 수 있으며 상호 작용 간에 다시 작성 되지 않습니다.
- 상태는 브라우저에 전송 되지 않습니다.

그러나 메모리 내 구성 요소 상태 지 속성에는 다음과 같은 몇 가지 단점이 있습니다.

- 요청 간에 서버가 다시 시작 되 면 상태가 손실 됩니다.
- 응용 프로그램 웹 서버 부하 분산 솔루션은 동일한 브라우저의 모든 요청이 동일한 서버로 반환 되도록 고정 세션을 포함 해야 합니다. 요청이 다른 서버로 이동 하면 상태가 손실 됩니다.
- 서버에서 구성 요소 상태를 지 속성은 웹 서버에서 메모리가 부족 해질 수 있습니다.

위의 이유로 인해 구성 요소의 상태를 사용 하 여 서버에 메모리 내에 상주 하지 마십시오. 응용 프로그램에는 요청 간 데이터를 위한 일부 지원 데이터 저장소도 포함 되어야 합니다. 이 전략의 몇 가지 간단한 예는 다음과 같습니다.

- 쇼핑 카트 응용 프로그램에서 카트에 추가 된 새 항목의 콘텐츠를 데이터베이스 레코드에 보관 합니다. 서버의 상태가 손실 된 경우 데이터베이스 레코드에서 다시 구성할 수 있습니다.
- 다중 파트 웹 양식에서 사용자는 응용 프로그램이 각 요청 간에 값을 기억할 것으로 간주 합니다. 여러 부분으로 구성 된 폼이 완료 될 때 최종 폼 응답 구조에 데이터를 인출 하 고 어셈블할 수 있도록 각 사용자의 게시물 간에 데이터를 데이터 저장소에 기록 합니다.

Blazor apps에서 상태를 관리 하는 방법에 대 한 자세한 내용은 [ASP.NET Core Blazor state management](/aspnet/core/blazor/state-management)를 참조 하세요.

## <a name="maintain-state-with-session"></a>세션을 사용 하 여 상태 유지

Web Forms 개발자는 사전 개체를 사용 하 여 현재 작동 중인 사용자에 대 한 정보를 유지할 수 있습니다 <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> . 문자열 키가 있는 개체를에 추가 하는 것은 쉽지만 `Session` 사용자가 응용 프로그램과 상호 작용 하는 동안 나중에 해당 개체를 사용할 수 있습니다. HTTP와 상호 작용 하는 관리를 제거 하려고 하면 개체를 사용 하 여 `Session` 상태를 쉽게 유지할 수 있습니다.

.NET Framework 개체의 서명이 `Session` ASP.NET Core 개체와 다릅니다 `Session` . 새 세션 상태 기능을 마이그레이션하고 사용 하도록 결정 하기 전에 [새 ASP.NET Core 세션에 대 한 설명서를](/dotnet/api/microsoft.aspnetcore.http.isession) 참조 하십시오.

세션은 ASP.NET Core 및 Blazor 서버에서 사용할 수 있지만 데이터 리포지토리의 데이터를 적절 하 게 저장 하는 데 사용 하지 않는 것이 좋습니다. 방문자가 개인 정보 문제로 인해 응용 프로그램에서 HTTP 쿠키 사용을 거부 하는 경우에도 세션 상태가 작동 하지 않습니다.

ASP.NET Core 및 세션 상태 구성은 [ASP.NET Core 문서의 세션 및 상태 관리](/aspnet/core/fundamentals/app-state#session-state)에서 사용할 수 있습니다.

## <a name="application-state"></a>애플리케이션 상태

`Application`Web Forms 프레임 워크의 개체는 응용 프로그램 범위 구성과 상태를 상호 작용 하기 위한 대규모의 다중 요청 리포지토리를 제공 합니다. 응용 프로그램 상태는 요청 하는 사용자에 관계 없이 모든 요청에서 참조 되는 다양 한 응용 프로그램 구성 속성을 저장 하는 데 적합 한 위치 였습니다. 개체의 문제는 `Application` 데이터가 여러 서버에 유지 되지 않았기 때문입니다. 응용 프로그램 개체의 상태가 다시 시작 사이에서 손실 되었습니다.

와 마찬가지로 `Session` 여러 서버 인스턴스에서 액세스할 수 있는 영구 백업 저장소로 데이터를 이동 하는 것이 좋습니다. 요청 및 사용자 간에 액세스할 수 있는 휘발성 데이터가 있는 경우이 정보나 상호 작용이 필요한 구성 요소에 삽입할 수 있는 단일 서비스에 해당 데이터를 쉽게 저장할 수 있습니다.

응용 프로그램 상태를 유지 관리 하는 개체를 생성 하는 것은 다음 구현과 유사할 수 있습니다.

```csharp
public class MyApplicationState
{
    public int VisitorCounter { get; private set; } = 0;

    public void IncrementCounter() => VisitorCounter += 1;
}
```

```csharp
app.AddSingleton<MyApplicationState>();
```

```razor
@inject MyApplicationState AppState

<label>Total Visitors: @AppState.VisitorCounter</label>
```

`MyApplicationState`개체는 서버에서 한 번만 만들어지므로 값은 `VisitorCounter` 인출 되 고 구성 요소의 레이블에서 출력 됩니다. 지 속성 `VisitorCounter` 및 확장성을 위해 지원 되는 데이터 저장소에서 값을 유지 하 고 검색 해야 합니다.

## <a name="in-the-browser"></a>브라우저에서

응용 프로그램 데이터는 나중에 사용할 수 있도록 사용자의 장치에 클라이언트 쪽으로 저장 될 수도 있습니다. 사용자 브라우저의 여러 범위에 있는 데이터의 지 속성을 허용 하는 두 가지 브라우저 기능이 있습니다.

- `localStorage` -사용자의 전체 브라우저로 범위가 한정 됩니다. 페이지를 다시 로드 하는 경우 브라우저를 닫았다가 다시 열거나 동일한 URL을 사용 하 여 다른 탭을 열면 브라우저에서 동일 하 게 제공 됩니다. `localStorage`
- `sessionStorage` -사용자의 현재 브라우저 탭으로 범위가 지정 됩니다. 탭이 다시 로드 되 면 상태는 지속 됩니다. 그러나 사용자가 응용 프로그램에 다른 탭을 열거나 브라우저를 닫고 다시 열면 상태가 손실 됩니다.

이러한 기능과 상호 작용 하는 사용자 지정 JavaScript 코드를 작성 하거나이 기능을 제공 하는 데 사용할 수 있는 여러 NuGet 패키지를 만들 수 있습니다. 이러한 패키지 중 하나는 [AspNetCore. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage)입니다.

이 패키지를 활용 하 여 및와 상호 작용 하는 방법에 대 한 지침은 `localStorage` `sessionStorage` [Blazor State Management](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) 문서를 참조 하세요.

>[!div class="step-by-step"]
>[이전](pages-routing-layouts.md)
>[다음](forms-validation.md)

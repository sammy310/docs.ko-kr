---
title: '호환성이 손상되는 변경: Blazor: WebEventDescriptor.EventArgsType 속성이 대체됨'
description: WebEventDescriptor EventArgsType 속성이 EventName 속성으로 바뀌는 ASP.NET Core 6.0의 호환성이 손상되는 변경에 대해 알아봅니다.
author: scottaddie
ms.author: scaddie
ms.date: 02/24/2021
no-loc:
- Blazor
ms.openlocfilehash: 6df086ed234c0071ede83e9fe9d1710f011a2039
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260020"
---
# <a name="blazor-no-loc-textwebeventdescriptoreventargstype-property-replaced"></a>Blazor: :::no-loc text="WebEventDescriptor.EventArgsType"::: 속성이 대체됨

<xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor>클래스는 JavaScript에서 .NET으로 이벤트를 전달하기 위한 Blazor 내부 프로토콜의 일부입니다. 이 클래스는 일반적으로 애플리케이션 코드에서 사용되는 것이 아니라 플랫폼 작성자가 사용합니다.

ASP.NET Core 6.0부터 `WebEventDescriptor`의 <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A> 속성이 새로운 `EventName` 속성으로 바뀝니다. 이 변경은 하위 수준의 플랫폼 구현 세부 정보이므로 앱 코드에 영향을 줄 가능성은 없습니다.

## <a name="version-introduced"></a>도입된 버전

6.0

## <a name="old-behavior"></a>이전 동작

ASP.NET Core 5.0 및 이전 버전에서 `EventArgsType` 속성은 DOM 이벤트 유형 그룹의 비표준 Blazor 특정 범주 이름을 설명합니다. 예를 들어 `click` 및 `mousedown` 이벤트는 모두 `mouse`의 `EventArgsType` 값에 매핑됩니다. 마찬가지로, `cut`, `copy` 및 `paste` 이벤트는 `clipboard`의 `EventArgsType` 값에 매핑됩니다. 이러한 범주 이름은 들어오는 이벤트 인수 데이터를 역직렬화하는 데 사용할 .NET 형식을 결정하는 데 사용됩니다.

## <a name="new-behavior"></a>새 동작

ASP.NET Core 6.0부터 새 속성은 `EventName`은 원래 이벤트의 이름만 지정합니다. 예를 들어 `click`, `mousedown`, `cut`, `copy` 또는 `paste`입니다. 더 이상 Blazor 특정 범주 이름을 제공할 필요가 없습니다. 이러한 이유로 이전 속성 `EventArgsType`은 제거됩니다.

## <a name="reason-for-change"></a>변경 이유

끌어오기 요청 [dotnet/aspnetcore#29993](https://github.com/dotnet/aspnetcore/pull/29993)에서 사용자 지정 이벤트 인수 클래스에 대한 지원이 도입되었습니다. 이 지원의 일부로 프레임워크는 더 이상 미리 정의된 범주 집합에 맞는 모든 이벤트를 사용하지 않습니다. 이제 프레임워크에서 원래 이벤트 이름을 알아야 합니다.

## <a name="recommended-action"></a>권장 조치

앱 코드는 영향을 받지 않으며 변경할 필요가 없습니다.

사용자 지정 Blazor 렌더링 플랫폼을 빌드하는 경우 이벤트를 `Renderer`로 디스패치하는 메커니즘을 업데이트해야 할 수 있습니다. 이벤트 범주에 대한 하드 코딩된 규칙을 원래 원시 이벤트 이름을 제공하는 간단한 논리로 바꿉니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`P:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType`

-->

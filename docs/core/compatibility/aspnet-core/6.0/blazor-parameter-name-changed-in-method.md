---
title: '호환성이 손상되는 변경: Blazor: RequestImageFileAsync 메서드에서 매개 변수 이름이 변경됨'
description: 'ASP.NET Core 6.0의 호환성이 손상되는 변경에 관해 알아보기. Blazor: RequestImageFileAsync 메서드에서 매개 변수 이름이 변경됨'
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: bfaaa6bfe94c32fbc1a5b5b70db863d105d389b5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488243"
---
# <a name="blazor-parameter-name-changed-in-requestimagefileasync-method"></a>Blazor: RequestImageFileAsync 메서드에서 매개 변수 이름이 변경됨

`RequestImageFileAsync` 메서드의 `maxWith` 매개 변수 이름이 `maxWith`에서 `maxWidth`로 바뀌었습니다.

## <a name="version-introduced"></a>도입된 버전

6.0 미리 보기 1

## <a name="old-behavior"></a>이전 동작

매개 변수 이름의 철자는 `maxWith`입니다.

## <a name="new-behavior"></a>새 동작

매개 변수 이름의 철자는 `maxWidth`입니다.

## <a name="reason-for-change"></a>변경 이유

원래 매개 변수 이름이 철자 오류였습니다.

## <a name="recommended-action"></a>권장 조치

`RequestImageFile` API에서 명명된 매개 변수를 사용하는 경우 `maxWith` 매개 변수 이름을 `maxWidth`로 업데이트합니다. 그러지 않으면 변경이 필요하지 않습니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync`

-->

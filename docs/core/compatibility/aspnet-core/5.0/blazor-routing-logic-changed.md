---
title: '호환성이 손상되는 변경: Blazor: Blazor 앱의 라우팅 논리 변경 내용'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: Blazor 앱의 라우팅 논리 변경 내용'
author: scottaddie
ms.author: scaddie
ms.date: 12/14/2020
ms.openlocfilehash: 4ab8289565c88b17eb204a11724bb12a09b033c2
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513510"
---
# <a name="blazor-route-precedence-logic-changed-in-blazor-apps"></a>Blazor: Blazor 앱에서 경로 우선 순위 논리가 변경됨

Blazor 라우팅 구현의 버그로 경로의 우선 순위를 결정하는 방법이 영향을 받았습니다. 이 버그는 Blazor 앱 내에서 catch-all 경로나 선택적 매개 변수를 사용하는 경로에 영향을 줍니다.

## <a name="version-introduced"></a>도입된 버전

5.0.1

## <a name="old-behavior"></a>이전 동작

잘못된 동작으로 우선 순위가 낮은 경로가 우선 순위가 높은 경로보다 우선 고려되고 일치됩니다. 예를 들어 `{*slug}` 경로가 `/customer/{id}`보다 먼저 일치됩니다.

## <a name="new-behavior"></a>새 동작

현재 동작은 ASP.NET Core 앱에 정의된 라우팅 동작과 더 가깝게 일치합니다. 먼저 프레임워크에 따라 각 세그먼트의 경로 우선 순위가 결정됩니다. 경로의 길이는 동률을 깨기 위한 두 번째 기준으로만 사용됩니다.

## <a name="reason-for-change"></a>변경 이유

원래 동작은 구현에서 버그로 간주됩니다. 목표는 Blazor 앱의 라우팅 시스템이 나머지 ASP.NET Core의 라우팅 시스템과 동일한 방식으로 동작하도록 하는 것입니다.

## <a name="recommended-action"></a>권장 조치

5\.x 이전의 Blazor 버전에서 업그레이드하는 경우 `Router` 구성 요소에서 `PreferExactMatches` 특성을 사용합니다. 이 특성을 사용하여 올바른 동작을 옵트인할 수 있습니다. 예를 들면 다음과 같습니다.

```razor
<Router AppAssembly="@typeof(Program).Assembly" PreferExactMatches="true">
```

`PreferExactMatches`을 `true`로 설정하면 경로 일치에서 와일드카드보다 정확한 일치를 사용합니다.

## <a name="affected-apis"></a>영향을 받는 API

없음

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->

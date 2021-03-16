---
title: '호환성이 손상되는 변경: LINQ OrderBy.First{OrDefault}의 복잡성이 증가함'
description: OrderBy.First의 구현이 변경된 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 4cd2dda5f60976f935505d6a6cb1e4c23d150d09
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257273"
---
# <a name="complexity-of-linq-orderbyfirstordefault-increased"></a>LINQ OrderBy.First{OrDefault}의 복잡성이 증가함

<xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 및 <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>의 구현이 변경되어 연산의 복잡성이 증가했습니다.

## <a name="change-description"></a>변경 내용 설명

.NET Core 1.x~3.x에서 <xref:System.Linq.Enumerable.OrderBy%2A> 또는 <xref:System.Linq.Enumerable.OrderByDescending%2A> 뒤에 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>을 호출하면 `O(N)` 복잡도로 연산됩니다. 첫 번째(또는 기본) 요소만 필요하므로 이를 찾는 데는 하나의 열거형만 하나만 필요합니다. 그러나 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>에 제공된 조건자가 정확히 `N`번 호출됩니다. 여기서 `N`은 시퀀스의 길이입니다.

.NET 5 이상 버전에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 또는 <xref:System.Linq.Enumerable.OrderByDescending%2A> 뒤에 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>을 호출하면 `O(N)`의 복잡도 대신 `O(N log N)`의 복잡도로 연산되도록 [변경이 적용](https://github.com/dotnet/runtime/pull/36643)되었습니다. 그러나 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>에 제공된 조건자가 `N`번보다 적게 호출될 수 있는데, 이는 전체 성능에 더 중요한 영향을 줍니다.

> [!NOTE]
> 이 변경 사항은 .NET Framework의 연산의 구현 및 복잡도와 일치합니다.

## <a name="reason-for-change"></a>변경 이유

조건자를 보다 적게 호출하는 것의 이점은 전체적인 복잡도 감소의 이점을 능가하므로, .NET Core 1.0에 적용된 구현이 되돌려졌습니다. 자세한 내용은 [이 dotnet/런타임 문제](https://github.com/dotnet/runtime/issues/31554)를 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

개발자는 아무 작업도 수행하지 않아도 됩니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->

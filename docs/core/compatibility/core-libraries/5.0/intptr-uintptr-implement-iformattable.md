---
title: '호환성이 손상되는 변경: IntPtr 및 UIntPtr에서 IFormattable 구현'
description: IntPtr 및 UIntPtr에서 IFormattable을 구현하는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 0684652cdc2b8cf1d237074263bf0809082b0dcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759954"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a>IntPtr 및 UIntPtr에서 IFormattable 구현

<xref:System.IntPtr> 및 <xref:System.UIntPtr>에서는 이제 <xref:System.IFormattable>을 구현합니다. <xref:System.IFormattable> 지원을 확인하는 함수는 형식 지정자와 문화권을 전달할 수 있으므로 이러한 형식에 대해 다른 결과를 반환할 수 있습니다.

## <a name="change-description"></a>변경 내용 설명

이전 버전의 .NET에서는 <xref:System.IntPtr> 및 <xref:System.UIntPtr>이 <xref:System.IFormattable>을 구현하지 않습니다. <xref:System.IFormattable>을 확인하는 함수는 <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> 또는 <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>를 호출하는 것으로 대체될 수 있습니다. 이 경우 형식 지정자와 문화권이 적용되지 않습니다.

.NET 5.0 이상 버전에서는 <xref:System.IntPtr> 및 <xref:System.UIntPtr>이 <xref:System.IFormattable>을 구현합니다. <xref:System.IFormattable> 지원을 확인하는 함수는 형식 지정자와 문화권을 전달할 수 있으므로 이러한 형식에 대해 다른 결과를 반환할 수 있습니다.

이러한 변경은 보간된 문자열 및 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>과 같은 시나리오에 영향을 줍니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.IntPtr> 및 <xref:System.UIntPtr>은 이제 `nint` 및 `nuint` 키워드를 통해 C# 언어를 지원합니다. 지원 형식이 <xref:System.Int32?displayProperty=nameWithType> 등의 다른 기본 형식에 의해 노출되는 기능을 근거리 패리티(가능한 경우)에 제공하도록 업데이트되었습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

이러한 형식의 값을 표시할 때 형식 지정자 또는 사용자 지정 문화권을 사용하지 않으려는 경우 `ToString()`의 <xref:System.IntPtr.ToString?displayProperty=nameWithType> 및 <xref:System.UIntPtr.ToString?displayProperty=nameWithType> 오버로드를 호출할 수 있습니다.

## <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->

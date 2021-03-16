---
title: '호환성이 손상되는 변경: FrameworkDescription의 값은 .NET Core가 아닌 .NET입니다.'
description: RuntimeInformation.FrameworkDescription에서 “.NET Core” 대신 “.NET”을 반환하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 18aa9a30a149b3c38d4bbfe4a0c99446f4372f07
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257520"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a>FrameworkDescription의 값은 .NET Core가 아닌 .NET입니다.

<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 이제 ".NET Core" 대신 ".NET"을 반환합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 `.NET Core 3.1.1`과 같은 설명 문자열의 일부로 ".NET Core"를 반환합니다.

.NET 5부터 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 `.NET 5.0.0`과 같은 설명 문자열의 일부로 ".NET"을 반환합니다.

## <a name="reason-for-change"></a>변경 이유

.NET 5에서 `netcoreapp`은 짧은 대상 프레임워크 모니커인 `net`으로 대체됩니다. 일관성을 위해 프레임워크의 설명도 업데이트되었습니다. `FrameworkName`이 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> 속성 이외의 다른 곳에서는 인코딩되지 않기 때문에 외관만 변경되었습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>에서 반환된 문자열에서 ".NET Core"를 검색하는 코드를 업데이트합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->

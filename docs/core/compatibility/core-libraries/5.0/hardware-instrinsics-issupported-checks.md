---
title: '호환성이 손상되는 변경: 중첩 형식의 경우 하드웨어 내장 IsSupported 검사가 다를 수 있음'
description: X64.IsSupported에서 하드웨어 내장 함수를 확인하면 다른 결과가 생성될 수 있는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 5c6049ad5881c0389870cfd5e1550f8358c67599
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257455"
---
# <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a>중첩 형식의 경우 하드웨어 내장 IsSupported 검사가 다를 수 있음

`<Isa>`에서 <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> 네임스페이스의 클래스를 참조하는 `<Isa>.X64.IsSupported`를 확인할 경우 이전 버전의 .NET과는 다른 결과가 생성될 수 있습니다.

> [!TIP]
> *ISA* 는 업계 표준 아키텍처의 약어입니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="change-description"></a>변경 내용 설명

이전 버전의 .NET에서는 <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>과 같은 <xref:System.Runtime.Intrinsics.X86> 하드웨어 내장 형식 중 일부가 중첩된 `X64` 클래스를 노출하지 않았습니다. 해당 형식에 대해 `<Isa>.X64.IsSupported`를 호출하면 부모 클래스 `<Isa>`에 중첩된 `X64` 클래스의 `IsSupported` 속성으로 확인되었습니다. 즉, `<Isa>.IsSupported`에서 `false`를 반환하는 경우에도 속성이 `true`를 반환할 수 있었습니다.

.NET 5 이상 버전에서는 모든 <xref:System.Runtime.Intrinsics.X86> 형식이 적절하게 지원을 보고하는 중첩된 `X64` 클래스를 공개합니다. 따라서 일반 계층 구조가 올바르게 유지되고, `<Isa>.X64.IsSupported`가 `true`이면 `<Isa>.IsSupported`도 `true`로 간주할 수 있습니다.

## <a name="reason-for-change"></a>변경 이유

`<Isa>.X64.IsSupported`가 `true`이면 `<Isa>.IsSupported`도 `true`로 암시되도록 하려고 했습니다. 그러나 C#에서 멤버 확인이 작동하는 방식 때문에 중첩된 `X64` 클래스가 없는 클래스에서 해당 사례가 아니고 사용자 코드 버그가 발생하는 상황이 노출되었습니다.

## <a name="recommended-action"></a>권장 조치

필요한 경우 `IsSupported`를 검사하여 적절한 ISA를 확인하는 코드를 조정합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->

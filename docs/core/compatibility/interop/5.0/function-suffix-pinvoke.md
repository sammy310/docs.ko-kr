---
title: '호환성이 손상되는 변경: 비 Windows 플랫폼에서 A/W 접미사 검색 안 함'
description: Windows가 아닌 플랫폼에서 P/Invoke를 검색하는 동안 함수 내보내기 이름에 접미사가 더 이상 추가되지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 08/13/2020
ms.openlocfilehash: 924cbcb6c432e2f7c52c7218d48a938b61306c9c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256623"
---
# <a name="no-aw-suffix-probing-on-non-windows-platforms"></a>비 Windows 플랫폼에서 A/W 접미사 검색 안 함

.NET 런타임은 비 Windows 플랫폼에서 P/Invoke를 검색하는 동안 함수 내보내기 이름에 `A` 또는 `W` 접미사를 더 이상 추가하지 않습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="change-description"></a>변경 내용 설명

Windows에는 `A` 또는 `W` 접미사를 각각 Windows 코드 페이지 및 유니코드 버전에 해당하는 Windows SDK 함수 이름에 추가하는 [규칙이 있습니다](/windows/win32/intl/conventions-for-function-prototypes).

이전 버전의 .NET에서는 CoreCLR 및 Mono 런타임 둘 다 ‘모든 플랫폼에서’ P/Invokes 내보내기 검색 중에 `A` 또는 `W` 접미사를 내보내기 이름에 추가합니다.

.NET 5 이상 버전에서는 ‘Windows에서만’ 내보내기 검색 중에 `A` 또는 `W` 접미사를 내보내기 이름에 추가합니다. Unix 플랫폼에서 접미사는 추가되지 않습니다. Windows 플랫폼에서 두 런타임의 의미 체계는 그대로 유지됩니다.

## <a name="reason-for-change"></a>변경 이유

플랫폼 간 검색을 간소화하기 위해 이렇게 변경되었습니다. 비 Windows 플랫폼이 이 의미 체계를 포함하지 않는다는 사실을 고려할 때 이는 발생하지 않아야 하는 오버헤드입니다.

## <a name="recommended-action"></a>권장 조치

변경을 완화하기 위해 비 Windows 플랫폼에서 원하는 접미사를 수동으로 추가할 수 있습니다. 예를 들어:

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

### Category

Interop

-->

---
title: Interop 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5.0 이상에서 interop 관련 호환성이 손상되는 변경 내용을 나열합니다.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438033"
---
# <a name="interop-breaking-changes"></a>Interop 관련 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | :-: |
| [RCW를 `InterfaceIsIInspectable` 인터페이스로 캐스팅하면 PlatformNotSupportedException이 throw됨](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | 5.0 |
| [비 Windows 플랫폼에서 A/W 접미사 검색 안 함](#no-aw-suffix-probing-on-non-windows-platforms) | 5.0 |
| [WinRT의 기본 제공 지원이 .NET에서 제거됨](#built-in-support-for-winrt-is-removed-from-net) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***

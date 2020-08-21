---
title: Interop 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5.0 이상에서 interop 관련 호환성이 손상되는 변경 내용을 나열합니다.
ms.date: 06/23/2020
ms.openlocfilehash: bac60631f8515eaf102f9d6e75fe817baceb7824
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062428"
---
# <a name="interop-breaking-changes"></a>Interop 관련 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | :-: |
| [비 Windows 플랫폼에서 A/W 접미사 검색 안 함](#no-aw-suffix-probing-on-non-windows-platforms) | 5.0 |
| [WinRT의 기본 제공 지원이 .NET에서 제거됨](#built-in-support-for-winrt-is-removed-from-net) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***

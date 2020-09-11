---
title: 네트워킹 관련 호환성이 손상되는 변경
description: .NET Core의 네트워킹에 호환성이 손상되는 변경을 나열합니다.
ms.date: 05/05/2020
ms.openlocfilehash: fa5807c882c3bc6f66e8a27361ccc14254e90b3e
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465518"
---
# <a name="networking-breaking-changes"></a>네트워킹 관련 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | - |
| [.NET 런타임에서 WinHttpHandler 제거됨](#winhttphandler-removed-from-net-runtime) | 5.0 |
| [MulticastOption.Group에서 null 값을 허용하지 않음](#multicastoptiongroup-doesnt-accept-a-null-value) | 5.0 |
| [이제 쿠키 경로 처리가 RFC 6265를 준수함](#cookie-path-handling-now-conforms-to-rfc-6265) | 5.0 |
| [HttpRequestMessage.Version의 기본값은 1.1로 변경되었습니다.](#default-value-of-httprequestmessageversion-changed-to-11) | 3.0 |
| [WebClient.CancelAsync가 항상 즉시 취소되지는 않음](#webclientcancelasync-doesnt-always-cancel-immediately) | 2.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

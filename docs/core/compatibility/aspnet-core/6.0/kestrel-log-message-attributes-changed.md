---
title: '호환성이 손상되는 변경: Kestrel: 로그 메시지 특성이 변경됨'
description: 'ASP.NET Core 6.0의 호환성이 손상되는 변경에 대해 알아보기. Kestrel: 로그 메시지 특성이 변경됨'
author: scottaddie
ms.author: scaddie
ms.date: 02/01/2021
ms.openlocfilehash: 30b03c22a6c85623fec7db14b58b169f887395a0
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99551535"
---
# <a name="kestrel-log-message-attributes-changed"></a>Kestrel: 로그 메시지 특성이 변경됨

Kestrel 로그 메시지에는 ID 및 이름이 연결되어 있습니다. 이러한 특성은 다양한 종류의 로그 메시지를 고유하게 식별합니다. 이러한 ID 및 이름 중 일부가 잘못 중복되었습니다. 이 중복 문제가 ASP.NET Core 6.0에서 해결되었습니다.

## <a name="version-introduced"></a>도입된 버전

6.0

## <a name="old-behavior"></a>이전 동작

다음 표에서는 ASP.NET Core 6.0 이전에서 영향을 받는 로그 메시지의 상태를 보여 줍니다.

| 메시지 설명                   | 속성                    | ID |
|---------------------------------------|-------------------------|----|
| HTTP/2 연결 닫힘 로그 메시지 | `Http2ConnectionClosed` | 36 |
| HTTP/2 프레임 전송 로그 메시지     | `Http2FrameReceived`    | 37 |

## <a name="new-behavior"></a>새 동작

다음 표에서는 ASP.NET Core 6.0에서 영향을 받는 로그 메시지의 상태를 보여 줍니다.

| 메시지 설명                   | 속성                    | ID |
|---------------------------------------|-------------------------|----|
| HTTP/2 연결 닫힘 로그 메시지 | `Http2ConnectionClosed` | 48 |
| HTTP/2 프레임 전송 로그 메시지     | `Http2FrameSending`     | 49 |

## <a name="reason-for-change"></a>변경 이유

로그 ID 및 이름은 서로 다른 메시지 유형을 식별할 수 있도록 고유해야 합니다.

## <a name="recommended-action"></a>권장 조치

이전 ID 및 이름을 참조하는 코드 또는 구성이 있는 경우 새 ID 및 이름을 사용하도록 해당 참조를 업데이트하세요.

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->

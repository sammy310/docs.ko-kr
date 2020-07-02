---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617542"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>터치 지원 시스템에서 System.Windows.Input.PenContext.Disable 호출하면 ArgumentException이 throw될 수 있음

#### <a name="details"></a>설명

상황에 따라 터치 지원 시스템에서 내부 **System.Windows.Input.PenContext.Disable** 메서드를 호출하면 재진입 때문에 처리되지 않은 `T:System.ArgumentException`가 throw될 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 문제는 .NET Framework 4.7에서 해결되었습니다. 예외를 방지하려면 .NET Framework 4.7 이상의 .NET Framework 버전으로 업그레이드합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6.1       |
| 형식    | 대상 변경 |

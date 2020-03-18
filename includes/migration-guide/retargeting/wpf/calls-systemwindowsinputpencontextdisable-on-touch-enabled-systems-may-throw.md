---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887808"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>터치 지원 시스템에서 System.Windows.Input.PenContext.Disable 호출하면 ArgumentException이 throw될 수 있음

|   |   |
|---|---|
|세부 정보|상황에 따라 터치 지원 시스템에서 내부 **System.Windows.Input.PenContext.Disable** 메서드를 호출하면 재진입 때문에 처리되지 않은 <code>T:System.ArgumentException</code>가 throw될 수 있습니다.|
|제안 해결 방법|이 문제는 .NET Framework 4.7에서 해결되었습니다. 예외를 방지하려면 .NET Framework 4.7 이상의 .NET Framework 버전으로 업그레이드합니다.|
|범위|가장자리|
|Version|4.6.1|
|형식|대상 변경|

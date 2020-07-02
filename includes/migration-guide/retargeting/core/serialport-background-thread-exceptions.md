---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614746"
---
### <a name="serialport-background-thread-exceptions"></a>SerialPort 백그라운드 스레드 예외

#### <a name="details"></a>세부 정보

<xref:System.IO.Ports.SerialPort> 스트림을 사용하여 만든 백그라운드 스레드는 OS 예외가 throw될 때 더 이상 프로세스를 종료하지 않습니다. <br/>.NET Framework 4.7 및 이전 버전을 대상으로 하는 애플리케이션에서 운영 체제 예외가 <xref:System.IO.Ports.SerialPort> 스트림을 사용하여 만든 백그라운드에서 throw되면 프로세스가 종료됩니다. <br/>.NET Framework 4.7.1 또는 이상 버전을 대상으로 하는 애플리케이션에서 백그라운드 스레드는 활성 직렬 포트와 관련된 OS 이벤트에 대해 기다리며 직렬 포트의 급격한 제거와 같은 일부 경우에 충돌할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.7.1을 대상으로 하는 앱의 경우, 필요하지 않으면 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 예외 처리를 옵트아웃할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 앱의 경우 `app.config` 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 예외 처리를 옵트인할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.1       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>

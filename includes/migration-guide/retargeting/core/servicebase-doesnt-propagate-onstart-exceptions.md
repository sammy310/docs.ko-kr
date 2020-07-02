---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614779"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase는 OnStart 예외를 전파하지 않음

#### <a name="details"></a>세부 정보

.NET Framework 4.7 및 이전 버전에서 서비스 시작 시 throw되는 예외는 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>의 호출자에게 전파되지 않습니다.<br/>.NET Framework 4.7.1을 대상으로 하는 애플리케이션을 시작으로 런타임은 시작에 실패하는 서비스에 대해 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>에 예외를 전파합니다.

#### <a name="suggestion"></a>제안 해결 방법

서비스 시작 시 예외가 있는 경우 해당 예외가 전파됩니다. 이는 서비스가 시작에 실패하는 사례를 진단하는 데 도움이 됩니다. <br/>이 동작을 원치 않을 경우 애플리케이션 구성 파일의 &lt;runtime&gt; 섹션에 다음 &lt;AppContextSwitchOverrides&gt; 요소를 추가하여 옵트아웃할 수 있습니다.

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

애플리케이션이 4.7.1 이전 버전을 대상으로 하지만 이 동작을 원할 경우 애플리케이션 구성 파일의 &lt;runtime&gt; 섹션에 다음 &lt;AppContextSwitchOverrides&gt; 요소를 추가합니다.

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.1       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>

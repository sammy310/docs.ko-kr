---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614782"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>재진입 서비스를 사용할 때 교착 상태가 발생할 수 있습니다.

#### <a name="details"></a>설명

교착 상태가 발생하면 재진입 서비스의 인스턴스가 한번에 하나의 실행 스레드로 제한됩니다. 이 문제가 발생하기 쉬운 서비스는 코드에 다음과 같은 <xref:System.ServiceModel.ServiceBehaviorAttribute>가 있습니다.

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>제안 해결 방법

이 문제를 해결하려면 다음을 수행합니다.

- 서비스의 동시성 모드를 <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> 또는 &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;로 설정합니다. 예를 들어:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- .NET Framework 4.6.2의 최신 업데이트를 설치하거나 이후 버전의 .NET Framework로 업그레이드합니다. 이렇게 하면 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>에서 <xref:System.Threading.ExecutionContext>의 흐름이 비활성화됩니다. 이 동작은 구성할 수 있습니다. 구성 파일에 다음 앱 설정을 추가하는 것과 같습니다.

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

`Switch.System.ServiceModel.DisableOperationContextAsyncFlow`의 값은 재진입 서비스에 대해 `false`로 설정하면 안 됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>

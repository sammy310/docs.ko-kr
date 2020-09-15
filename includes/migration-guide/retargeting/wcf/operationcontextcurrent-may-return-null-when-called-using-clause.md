---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614755"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>OperationContext.Current는 using 절에서 호출될 때 null을 반환할 수 있습니다.

#### <a name="details"></a>설명

다음 조건이 모두 참인 경우 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>이 `null`를 반환하고 <xref:System.NullReferenceException>이 발생할 수 있습니다.

- <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>을 반환하는 메서드에서 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 속성 값을 검색합니다.
- <xref:System.ServiceModel.OperationContextScope> 개체는 `using` 절에서 인스턴스화됩니다.
- `using statement` 내의 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 속성 값을 검색합니다. 예를 들어:

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a>제안 해결 방법

이 문제를 해결하려면 다음을 수행합니다.

- 다음과 같이 코드를 수정하여 새로운 `null` <xref:System.ServiceModel.OperationContext.Current%2A> 이외의 개체를 인스턴스화합니다.

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- .NET Framework 4.6.2의 최신 업데이트를 설치하거나 이후 버전의 .NET Framework로 업그레이드합니다. 이렇게 하면 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>에서 <xref:System.Threading.ExecutionContext>의 흐름이 비활성화되고 .NET Framework 4.6.1 및 이전 버전에서 WCF 애플리케이션의 동작이 복원됩니다. 이 동작은 구성할 수 있습니다. 구성 파일에 다음 앱 설정을 추가하는 것과 같습니다.

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    이러한 변경은 바람직하지 않으며 애플리케이션이 작업 컨텍스트 간에 흐르는 실행 컨텍스트에 의존하는 경우 다음과 같이 해당 흐름을 활성화할수 있습니다.

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>

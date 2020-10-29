---
ms.openlocfilehash: 959d8cb6d3e52916f6777054f3e9b327dc8edb4e
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434934"
---
### <a name="global-assembly-cache-apis-are-obsolete"></a>전역 어셈블리 캐시 API가 사용되지 않음

.NET Core 및 .NET 5.0 이상 버전에서는 .NET Framework에 있었던 GAC(전역 어셈블리 캐시) 개념이 사라집니다. 따라서 GAC를 처리하는 모든 .NET Core 및 .NET 5+ API가 실패하거나 작업을 수행하지 않습니다.

개발자가 이러한 API를 사용하지 않도록 하기 위해 일부 GAC 관련 API는 사용되지 않는 것으로 표시되고 컴파일 시간에 `SYSLIB0005` 경고를 생성합니다. 이러한 API는 향후 .NET 버전에서 제거될 수 있습니다.

#### <a name="change-description"></a>변경 내용 설명

다음은 사용되지 않는 것으로 표시되는 API입니다.

| API | 사용되지 않음으로 표시... |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | 5.0 RC1 |

.NET Framework 2.x - 4.x에서 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성은 쿼리된 어셈블리가 GAC에서 로드되면 `true`를 반환하고, 디스크의 다른 위치에서 로드되면 `false`를 반환합니다. .NET Core 2.x - 3.x에서 <xref:System.Reflection.Assembly.GlobalAssemblyCache>는 항상 `false`를 반환하여 GAC가 .NET Core에 없음을 반영합니다.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

.NET 5.0 이상 버전에서 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성은 항상 `false`를 반환합니다. 그러나 속성 getter도 사용되지 않는 것으로 표시되어 속성 액세스를 중지해야 함을 호출자에게 표시합니다. 라이브러리와 앱은 런타임 동작에 대한 결정을 내릴 때 <xref:System.Reflection.Assembly.GlobalAssemblyCache> API를 사용하면 안 됩니다. 이 API는 .NET Core 및 .NET 5.0 이상 버전에서 항상 `false`를 반환하기 때문입니다.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

이는 컴파일 시간 전용 변경입니다. .NET Core의 이전 버전에서 런타임 변경은 없습니다.

#### <a name="reason-for-change"></a>변경 이유

GAC(전역 어셈블리 캐시)는 .NET Core 및 .NET 5.0 이상 버전에서 개념으로 존재하지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

.NET 5.0

#### <a name="recommended-action"></a>권장 조치

- 애플리케이션이 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성을 쿼리하는 경우 호출을 제거하는 것이 좋습니다. <xref:System.Reflection.Assembly.GlobalAssemblyCache> 값을 사용하여 런타임에 “GAC에 있는 어셈블리” 흐름과 “GAC에 없는 어셈블리” 흐름을 선택하는 경우 이 흐름이 .NET Core 또는 .NET 5.0+ 애플리케이션에 적합한지를 재고해야 합니다.

- 사용되지 않는 API를 계속 사용해야 하는 경우 코드에서 `SYSLIB0005` 경고를 표시하지 않을 수 있습니다.

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  프로젝트 파일에서 경고를 표시하지 않고 프로젝트의 모든 소스 파일에 대해 경고를 사용하지 않도록 설정할 수도 있습니다.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  `SYSLIB0005`를 표시하지 않으면 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 사용되지 않음 경고만 사용하지 않도록 설정됩니다. 다른 경고를 사용하지 않도록 설정하는 것은 아닙니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->

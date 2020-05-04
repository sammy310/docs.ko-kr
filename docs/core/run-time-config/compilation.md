---
title: 컴파일 구성 설정
description: .NET Core 앱에 대해 JIT 컴파일러가 작동하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 4db20ee6d36fe3d3d66f473644b70c02d4e02cb3
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506846"
---
# <a name="run-time-configuration-options-for-compilation"></a>컴파일을 위한 런타임 구성 옵션

## <a name="tiered-compilation"></a>계층화된 컴파일

- JIT(Just-In-Time) 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다. 계층화된 컴파일은 두 계층을 통해 메서드를 전환합니다.
  - 첫 번째 계층은 코드를 더 빠르게 생성([빠른 JIT](#quick-jit))하거나 미리 컴파일된 코드([ReadyToRun](#readytorun))를 로드합니다.
  - 두 번째 계층은 백그라운드에서 최적화된 코드를 생성합니다("JIT 최적화").
- .NET Core 3.0 이상에서는 기본적으로 계층화된 컴파일이 사용하도록 설정됩니다.
- .NET Core 2.1 및 2.2에서는 기본적으로 계층화된 컴파일이 사용하지 않도록 설정됩니다.
- 자세한 내용은 [계층화된 컴파일 가이드](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md)를 참조하세요.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true` - 사용<br/>`false` - 사용 안 함 |
| **MSBuild 속성** | `TieredCompilation` | `true` - 사용<br/>`false` - 사용 안 함 |
| **환경 변수** | `COMPlus_TieredCompilation` | `1` - 사용<br/>`0` - 사용 안 함 |

### <a name="examples"></a>예

*runtimeconfig.json* 파일:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

프로젝트 파일:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a>빠른 JIT

- JIT 컴파일러가 *빠른 JIT*를 사용하는지 여부를 구성합니다. 루프를 포함되어 있지 않고 미리 컴파일된 코드를 사용할 수 없는 메서드의 경우 빠른 JIT는 최적화하지 않고도 빠르게 컴파일합니다.
- 빠른 JIT를 사용하도록 설정하면 시작 시간이 단축되지만 성능 특성이 저하된 코드가 생성될 수 있습니다. 예를 들어 코드에서 더 많은 스택 공간을 사용하고, 더 많은 메모리를 할당하며 느리게 실행될 수 있습니다.
- 빠른 JIT를 사용하지 않도록 설정하고 [계층화된 컴파일](#tiered-compilation)을 사용하도록 설정한 경우에는 미리 컴파일된 코드만 계층화된 컴파일에 참여합니다. 메서드를 [ReadyToRun](#readytorun)으로 미리 컴파일하지 않은 경우 JIT 동작은 [계층화된 컴파일](#tiered-compilation)이 사용하지 않도록 설정된 것과 같습니다.
- .NET Core 3.0 이상에서는 기본적으로 빠른 JIT가 사용하도록 설정됩니다.
- .NET Core 2.1 및 2.2에서는 기본적으로 빠른 JIT가 사용하지 않도록 설정됩니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJit` | `true` - 사용<br/>`false` - 사용 안 함 |
| **MSBuild 속성** | `TieredCompilationQuickJit` | `true` - 사용<br/>`false` - 사용 안 함 |
| **환경 변수** | `COMPlus_TC_QuickJit` | `1` - 사용<br/>`0` - 사용 안 함 |

### <a name="examples"></a>예

*runtimeconfig.json* 파일:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

프로젝트 파일:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a>루프에 대한 빠른 JIT

- JIT 컴파일러가 루프를 포함하는 메서드에서 빠른 JIT를 사용할지 여부를 구성합니다.
- 루프에 대한 빠른 JIT를 사용하도록 설정하면 시작 성능이 향상될 수 있습니다. 그러나 장기 실행 루프의 경우 오랜 기간 동안 덜 최적화된 코드에서 중단될 수 있습니다.
- [빠른 JIT](#quick-jit)를 사용하지 않도록 설정한 경우에는 이 설정이 적용되지 않습니다.
- 기본값: 사용 안 함(`false`).

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation.QuickJitForLoops` | `false` - 사용 안 함<br/>`true` - 사용 |
| **MSBuild 속성** | `TieredCompilationQuickJitForLoops` | `false` - 사용 안 함<br/>`true` - 사용 |
| **환경 변수** | `COMPlus_TC_QuickJitForLoops` | `0` - 사용 안 함<br/>`1` - 사용 |

### <a name="examples"></a>예

*runtimeconfig.json* 파일:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

프로젝트 파일:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a>ReadyToRun

- .NET Core 런타임이 사용 가능한 ReadyToRun 데이터가 포함된 이미지에 미리 컴파일된 코드를 사용하도록 할지 여부를 구성합니다. 이 옵션을 사용하지 않도록 설정하면 런타임에서 프레임워크 코드를 강제로 JIT 컴파일하게 합니다.
- 자세한 내용은 [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images)을 참조하세요.
- 기본값: 사용(`1`).

| | 설정 이름 | 값 |
| - | - | - |
| **환경 변수** | `COMPlus_ReadyToRun` | `1` - 사용<br/>`0` - 사용 안 함 |

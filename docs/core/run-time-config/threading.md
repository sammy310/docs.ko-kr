---
title: 스레딩 구성 설정
description: .NET Core 앱의 스레딩을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761930"
---
# <a name="run-time-configuration-options-for-threading"></a>스레딩을 위한 런타임 구성 옵션

## <a name="cpu-groups"></a>CPU 그룹

- 스레드가 여러 CPU 그룹에 자동으로 분산되는지 여부를 구성합니다.
- 이 설정을 생략하면 스레드가 CPU 그룹 간에 분산되지 않습니다. 이는 값을 `0`으로 설정하는 것과 같습니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | N/A | N/A |
| **환경 변수** | `COMPlus_Thread_UseAllCpuGroups` | `0` - 사용 안 함<br/>`1` - 사용 |

## <a name="minimum-threads"></a>최소 스레드

- 작업자 스레드 풀의 최소 스레드 개수를 지정합니다.
- <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | 최소 스레드 개수를 나타내는 정수 |
| **MSBuild 속성** | `ThreadPoolMinThreads` | 최소 스레드 개수를 나타내는 정수 |
| **환경 변수** | N/A | N/A |

### <a name="examples"></a>예

*runtimeconfig.json* 파일:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

프로젝트 파일:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a>최대 스레드

- 작업자 스레드 풀의 최대 스레드 개수를 지정합니다.
- <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | 최대 스레드 개수를 나타내는 정수 |
| **MSBuild 속성** | `ThreadPoolMaxThreads` | 최대 스레드 개수를 나타내는 정수 |
| **환경 변수** | N/A | N/A |

### <a name="examples"></a>예

*runtimeconfig.json* 파일:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

프로젝트 파일:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

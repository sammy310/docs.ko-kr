---
title: 스레딩 구성 설정
description: .NET Core 앱의 스레딩을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998830"
---
# <a name="run-time-configuration-options-for-threading"></a>스레딩을 위한 런타임 구성 옵션

## <a name="cpu-groups"></a>CPU 그룹

- 스레드가 여러 CPU 그룹에 자동으로 분산되는지 여부를 구성합니다.
- 기본값: 사용 안 함(`0`).

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | 해당 사항 없음 | 해당 사항 없음 |
| **환경 변수** | `COMPlus_Thread_UseAllCpuGroups` | `0` - 사용 안 함<br/>`1` - 사용 |

## <a name="minimum-threads"></a>최소 스레드

- 작업자 스레드 풀의 최소 스레드 개수를 지정합니다.
- <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | 최소 스레드 개수를 나타내는 정수 |
| **환경 변수** | 해당 사항 없음 | 해당 사항 없음 |

## <a name="maximum-threads"></a>최대 스레드

- 작업자 스레드 풀의 최대 스레드 개수를 지정합니다.
- <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> 메서드에 대응됩니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | 최대 스레드 개수를 나타내는 정수 |
| **환경 변수** | 해당 사항 없음 | 해당 사항 없음 |

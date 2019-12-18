---
title: 컴파일 구성 설정
description: .NET Core 앱에 대해 JIT 컴파일러가 작동하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998878"
---
# <a name="run-time-configuration-options-for-compilation"></a>컴파일을 위한 런타임 구성 옵션

## <a name="tiered-compilation"></a>계층화된 컴파일

- JIT 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다.
- .NET Core 3.0 이상에서는 기본적으로 계층화된 컴파일이 사용하도록 설정됩니다.
- .NET Core 2.1 및 2.2에서는 기본적으로 계층화된 컴파일이 사용하지 않도록 설정됩니다.

| | 설정 이름 | 값 |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true` - 사용<br/>`false` - 사용 안 함 |
| **환경 변수** | `COMPlus_TieredCompilation` | `1` - 사용<br/>`0` - 사용 안 함 |

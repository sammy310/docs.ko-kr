---
title: '호환성이 손상되는 변경: .NET 5를 대상으로 하는 경우 NETCOREAPP3_1 전처리기 기호가 정의되지 않음'
description: 프로젝트가 이전 버전의 전처리기 기호를 더 이상 정의하지 않는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/17/2020
ms.openlocfilehash: 61a5e4fce258d2be3d584318e154bb752b88ebe1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759704"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a>.NET 5를 대상으로 하는 경우 NETCOREAPP3_1 전처리기 기호가 정의되지 않음

.NET 5.0 RC2 이상 버전에서는 프로젝트에서 이전 버전의 전처리기 기호를 더 이상 정의하지 않고 대상으로 하는 버전의 기호만 정의합니다. 이는 .NET Core 1.0~3.1과 동일한 동작입니다.

## <a name="version-introduced"></a>도입된 버전

5.0 RC2

## <a name="change-description"></a>변경 내용 설명

.NET 5.0 미리 보기 7~RC1에서는 `net5.0`을 대상으로 하는 프로젝트에서 `NETCOREAPP3_1` 및 `NET5_0` 전처리기 기호를 모두 정의합니다. 이와 같이 동작을 변경하는 이유는 .NET 5.0부터 조건부 컴파일 [기호가 누적되기](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols) 때문이었습니다.

.NET 5.0 RC2 이상에서는 프로젝트에서 이전 버전이 아니라 대상으로 하는 TFM(대상 프레임워크 모니커)의 기호만 정의합니다.

## <a name="reason-for-change"></a>변경 이유

고객 피드백을 반영하여 미리 보기 7의 변경 내용을 되돌렸습니다. 이전 버전의 기호를 정의하면 고객이 놀라거나 혼동했으며 일부 고객은 C# 컴파일러의 버그로 여기기도 했습니다.

## <a name="recommended-action"></a>권장 조치

프로젝트가 `net5.0` 이상을 대상으로 하는 경우 `#if` 논리에서 `NETCOREAPP3_1`이 정의되어 있다고 간주하지 않아야 합니다. 대신, 프로젝트가 명시적으로 `netcoreapp3.1`을 대상으로 하는 경우에만 `NETCOREAPP3_1`이 정의되어 있다고 간주하세요.

예를 들어 프로젝트가 .NET Core 2.1 및 .NET Core 3.1을 멀티 타기팅하고 .NET Core 3.1에 도입된 API를 호출하는 경우 `#if` 논리는 다음과 같이 표시됩니다.

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a>영향을 받는 API

N/A

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->

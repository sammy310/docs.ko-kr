---
title: '호환성이 손상되는 변경: CreateCounterSetInstance는 인스턴스가 이미 있는 경우 InvalidOperationException을 throw함'
description: 카운터가 이미 있는 경우 CounterSet.CreateCounterSetInstance에서 다른 예외를 throw하는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 28042690b71f9b86e4e54748ec75467bbe232684
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759839"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>CounterSet.CreateCounterSetInstance는 인스턴스가 이미 있는 경우 이제 InvalidOperationException을 throw함

.NET 5.0부터 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType>은 카운터 집합이 이미 있는 경우 <xref:System.ArgumentException> 대신 <xref:System.InvalidOperationException>을 throw합니다.

## <a name="change-description"></a>변경 내용 설명

.NET Framework 및 .NET Core 1.0~3.1에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하여 카운터 집합의 인스턴스를 만들 수 있습니다. 그러나 카운터 집합이 이미 있는 경우 메서드는 <xref:System.ArgumentException> 예외를 throw합니다.

.NET 5.0 이상 버전에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하고 카운터 집합이 있으면 <xref:System.InvalidOperationException> 예외가 throw됩니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

<xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출할 때 앱에서 <xref:System.ArgumentException> 예외를 catch하는 경우 <xref:System.InvalidOperationException> 예외도 catch하는 것이 좋습니다.

> [!NOTE]
> <xref:System.ArgumentException> 예외를 catch하는 것은 권장되지 않습니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->

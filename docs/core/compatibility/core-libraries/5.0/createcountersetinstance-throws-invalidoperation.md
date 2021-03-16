---
title: '호환성이 손상되는 변경: CreateCounterSetInstance는 인스턴스가 이미 있는 경우 InvalidOperationException을 throw함'
description: 카운터가 이미 있는 경우 CounterSet.CreateCounterSetInstance에서 다른 예외를 throw하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: bf59677a85538bc4992c589f8642ab4a0fce54ac
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257572"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="16229-103">CounterSet.CreateCounterSetInstance는 인스턴스가 이미 있는 경우 이제 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="16229-103">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="16229-104">.NET 5부터 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType>은 카운터 집합이 이미 있는 경우 <xref:System.ArgumentException> 대신 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="16229-104">Starting in .NET 5, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

## <a name="change-description"></a><span data-ttu-id="16229-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="16229-105">Change description</span></span>

<span data-ttu-id="16229-106">.NET Framework 및 .NET Core 1.0~3.1에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하여 카운터 집합의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16229-106">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="16229-107">그러나 카운터 집합이 이미 있는 경우 메서드는 <xref:System.ArgumentException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="16229-107">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="16229-108">.NET 5 이상 버전에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하고 카운터 집합이 있으면 <xref:System.InvalidOperationException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="16229-108">In .NET 5 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="16229-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="16229-109">Version introduced</span></span>

<span data-ttu-id="16229-110">5.0</span><span class="sxs-lookup"><span data-stu-id="16229-110">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="16229-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="16229-111">Recommended action</span></span>

<span data-ttu-id="16229-112"><xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출할 때 앱에서 <xref:System.ArgumentException> 예외를 catch하는 경우 <xref:System.InvalidOperationException> 예외도 catch하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16229-112">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="16229-113"><xref:System.ArgumentException> 예외를 catch하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16229-113">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="16229-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="16229-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->

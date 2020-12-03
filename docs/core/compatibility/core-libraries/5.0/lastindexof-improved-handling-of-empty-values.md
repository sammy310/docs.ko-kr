---
title: '호환성이 손상되는 변경: LastIndexOf에서 빈 검색 문자열 처리 기능이 향상됨'
description: LastIndexOf 및 관련 API가 길이가 0인 substring을 검색할 때 올바른 값을 반환하는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 6d1a676eb2b9ed3de6a745db27d53bd43560a32f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759631"
---
# <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a><span data-ttu-id="94908-103">LastIndexOf에서 빈 검색 문자열 처리 기능이 향상됨</span><span class="sxs-lookup"><span data-stu-id="94908-103">LastIndexOf has improved handling of empty search strings</span></span>

<span data-ttu-id="94908-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> 및 관련 API가 더 큰 문자열 내에서 길이가 0이거나 이와 동등한 substring을 검색할 때 올바른 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94908-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs now return correct values when searching for a zero-length (or zero-length equivalent) substring within a larger string.</span></span>

## <a name="change-description"></a><span data-ttu-id="94908-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="94908-105">Change description</span></span>

<span data-ttu-id="94908-106">.NET Framework 및 .NET Core 1.0~3.1에서는 호출자가 길이가 0인 substring을 검색할 때 <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> 및 관련 API가 잘못된 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94908-106">In .NET Framework and .NET Core 1.0 - 3.1, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs might return an incorrect value when the caller searches for a zero-length substring.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

<span data-ttu-id="94908-107">.NET 5.0부터는 이러한 API가 `LastIndexOf`에 대한 올바른 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94908-107">Starting with .NET 5.0, these APIs return the correct value for `LastIndexOf`.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

<span data-ttu-id="94908-108">이러한 예제에서는 `"Hello".Substring(5)`과 `"Hello".AsSpan().Slice(5)`가 모두 빈 문자열을 생성하기 때문에 `5`가 올바른 답이며, 일반적으로 이 값은 검색되는 빈 substring과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94908-108">In these examples, `5` is the correct answer because `"Hello".Substring(5)` and `"Hello".AsSpan().Slice(5)` both produce an empty string, which is trivially equal to the empty substring that is sought.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="94908-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="94908-109">Reason for change</span></span>

<span data-ttu-id="94908-110">이러한 변경은 .NET 5의 문자열 처리와 관련된 전체적인 버그 수정 과정의 일부였습니다.</span><span class="sxs-lookup"><span data-stu-id="94908-110">This change was part of an overall bug fixing effort around string handling for .NET 5.</span></span> <span data-ttu-id="94908-111">또한 Windows 플랫폼과 비 Windows 플랫폼 간의 동작을 통합하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94908-111">It also helps unify our behavior between Windows and non-Windows platforms.</span></span> <span data-ttu-id="94908-112">자세한 내용은 [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) 및 [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94908-112">For more information, see [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) and [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="94908-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="94908-113">Version introduced</span></span>

<span data-ttu-id="94908-114">5.0</span><span class="sxs-lookup"><span data-stu-id="94908-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="94908-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="94908-115">Recommended action</span></span>

<span data-ttu-id="94908-116">아무 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94908-116">You don't need to take any action.</span></span> <span data-ttu-id="94908-117">.NET 5.0 런타임은 새로운 동작을 자동으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94908-117">The .NET 5.0 runtime provides the new behaviors automatically.</span></span>

<span data-ttu-id="94908-118">이전 동작을 복원할 호환성 스위치가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94908-118">There is no compatibility switch to restore the old behavior.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="94908-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="94908-119">Affected APIs</span></span>

- <xref:System.String.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.Globalization.CompareInfo.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.MemoryExtensions.LastIndexOf%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.String.LastIndexOf`
- `Overload:System.Globalization.CompareInfo.LastIndexOf`
- `Overload:System.MemoryExtensions.LastIndexOf`

-->

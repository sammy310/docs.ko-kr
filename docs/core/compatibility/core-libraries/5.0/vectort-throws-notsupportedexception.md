---
title: '호환성이 손상되는 변경: Vector<T>가 NotSupportedException을 throw함'
description: Vector<T>가 지원되지 않는 형식 매개 변수에 대해 항상 예외를 throw하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: dccd39c01f4debd7d1432195e7f3cb14aeda5f65
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257013"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="0e9bd-103">Vector\<T>가 지원되지 않는 형식에 대해 항상 NotSupportedException을 throw</span><span class="sxs-lookup"><span data-stu-id="0e9bd-103">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="0e9bd-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType>는 이제 지원되지 않는 형식 매개 변수에 대해 항상 <xref:System.NotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

## <a name="change-description"></a><span data-ttu-id="0e9bd-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0e9bd-105">Change description</span></span>

<span data-ttu-id="0e9bd-106">이전에는 `T`가 [지원되지 않는 형식](#unsupported-types)인 경우 <xref:System.Numerics.Vector%601>의 멤버가 항상 <xref:System.NotSupportedException>을 throw하지는 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-106">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="0e9bd-107">하드웨어 가속을 지원하는 코드 경로 때문에 예외가 throw되지 않는 경우가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-107">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="0e9bd-108">예를 들어 ARM32 같이 하드웨어 가속이 없는 플랫폼에서는 `Vector<bool> + Vector<bool>`가 예외를 throw하는 대신 `default`를 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-108">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="0e9bd-109">지원되지 않는 형식의 경우 <xref:System.Numerics.Vector%601> 멤버는 다양한 플랫폼 및 하드웨어 구성에서 일관되지 않은 동작을 보였습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-109">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="0e9bd-110">.NET 5부터 <xref:System.Numerics.Vector%601> 멤버는 `T`가 지원되는 형식이 아닌 경우 모든 하드웨어 구성에서 항상 <xref:System.NotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-110">Starting in .NET 5, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

### <a name="unsupported-types"></a><span data-ttu-id="0e9bd-111">지원되지 않는 형식</span><span class="sxs-lookup"><span data-stu-id="0e9bd-111">Unsupported types</span></span>

<span data-ttu-id="0e9bd-112"><xref:System.Numerics.Vector%601>의 형식 매개 변수에 대해 지원되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-112">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="0e9bd-113">그러나 지원되는 형식이 변경된 적은 없지만 향후에 변경될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-113">The supported types have not changed, however, they may change in the future.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0e9bd-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0e9bd-114">Version introduced</span></span>

<span data-ttu-id="0e9bd-115">5.0</span><span class="sxs-lookup"><span data-stu-id="0e9bd-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0e9bd-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0e9bd-116">Recommended action</span></span>

<span data-ttu-id="0e9bd-117"><xref:System.Numerics.Vector%601>의 형식 매개 변수에 지원되지 않는 형식을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0e9bd-117">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0e9bd-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0e9bd-118">Affected APIs</span></span>

- <span data-ttu-id="0e9bd-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> 및 모든 해당 멤버</span><span class="sxs-lookup"><span data-stu-id="0e9bd-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->

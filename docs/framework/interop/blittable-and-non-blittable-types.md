---
title: Blittable 형식 및 비 Blittable 형식
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
ms.openlocfilehash: 816b854120f09efef69bd8ceb2d3650e5a8e7af0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123731"
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="699ff-102">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="699ff-102">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="699ff-103">대부분의 데이터 형식은 관리되는 메모리와 관리되지 않는 메모리 둘 다에서 공통된 표현을 사용하며 interop 마샬러의 특별한 처리가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-103">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="699ff-104">이러한 형식은 관리 코드와 비관리 코드 간에 전달될 때 변환이 필요하지 않기 때문에 *blittable 형식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-104">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="699ff-105">플랫폼 호출에서 반환되는 구조는 blittable 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-105">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="699ff-106">플랫폼 호출은 비 blittable 구조를 반환 형식으로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-106">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="699ff-107"><xref:System> 네임스페이스의 다음 형식은 blittable 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-107">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="699ff-108">다음 복합 형식도 blittable 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-108">The following complex types are also blittable types:</span></span>  
  
- <span data-ttu-id="699ff-109">정수 배열 등 blittable 형식의 1차원 배열.</span><span class="sxs-lookup"><span data-stu-id="699ff-109">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="699ff-110">그러나 blittable 형식의 변수 배열을 포함하는 형식 자체는 blittable이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-110">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
- <span data-ttu-id="699ff-111">blittable 형식(및 서식이 지정된 형식으로 마샬링된 경우 클래스)만 포함하는 서식이 지정된 값 형식.</span><span class="sxs-lookup"><span data-stu-id="699ff-111">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="699ff-112">서식이 지정된 값 형식에 대한 자세한 내용은 [값 형식에 대한 기본 마샬링](default-marshaling-behavior.md#default-marshaling-for-value-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="699ff-112">For more information about formatted value types, see [Default marshaling for value types](default-marshaling-behavior.md#default-marshaling-for-value-types).</span></span>  
  
 <span data-ttu-id="699ff-113">개체 참조는 blittable이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-113">Object references are not blittable.</span></span> <span data-ttu-id="699ff-114">여기에는 그 자체가 blittable인 개체에 대한 참조 배열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-114">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="699ff-115">예를 들어 blittable인 구조를 정의할 수 있지만 이러한 구조에 대한 참조 배열을 포함하는 blittable 형식을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-115">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="699ff-116">최적화로, blittable 형식의 배열 및 blittable 멤버만 포함하는 클래스는 마샬링 중 복사되지 않고 [고정](copying-and-pinning.md)됩니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-116">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="699ff-117">호출자와 호출 수신자가 동일한 아파트에 있을 경우 이러한 형식은 In/Out 매개 변수로 마샬링되는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-117">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="699ff-118">그러나 이러한 형식은 실제로 In 매개 변수로 마샬링되며, 인수를 In/Out 매개 변수로 마샬링하려는 경우 <xref:System.Runtime.InteropServices.InAttribute> 및 <xref:System.Runtime.InteropServices.OutAttribute> 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-118">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="699ff-119">관리되는 일부 데이터 형식은 관리되지 않는 환경에서 다른 표현이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-119">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="699ff-120">이러한 비 blittable 데이터 형식을 마샬링할 수 있는 형식으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-120">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="699ff-121">예를 들어 관리되는 문자열은 문자열 개체로 변환해야 마샬링할 수 있기 때문에 비 blittable 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-121">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="699ff-122">다음 표에는 <xref:System> 네임스페이스의 비 blittable 형식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-122">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="699ff-123">정적 메서드 또는 클래스 인스턴스를 참조하는 데이터 구조인 [대리자](default-marshaling-behavior.md#default-marshaling-for-delegates)도 비 blittable입니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-123">[Delegates](default-marshaling-behavior.md#default-marshaling-for-delegates), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="699ff-124">비 blittable 형식</span><span class="sxs-lookup"><span data-stu-id="699ff-124">Non-blittable type</span></span>|<span data-ttu-id="699ff-125">설명</span><span class="sxs-lookup"><span data-stu-id="699ff-125">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="699ff-126">System.Array</span><span class="sxs-lookup"><span data-stu-id="699ff-126">System.Array</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="699ff-127">C 스타일 배열 또는 `SAFEARRAY`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-127">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|<span data-ttu-id="699ff-128">[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="699ff-128">[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span></span>|<span data-ttu-id="699ff-129">`true`가 1 또는 -1인 1, 2 또는 4바이트 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-129">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|<span data-ttu-id="699ff-130">[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="699ff-130">[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span></span>|<span data-ttu-id="699ff-131">유니코드 또는 ANSI 문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-131">Converts to a Unicode or ANSI character.</span></span>|  
|<span data-ttu-id="699ff-132">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="699ff-132">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span></span>|<span data-ttu-id="699ff-133">클래스 인터페이스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-133">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="699ff-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="699ff-134">System.Object</span></span>](default-marshaling-for-objects.md)|<span data-ttu-id="699ff-135">Variant 또는 인터페이스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-135">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="699ff-136">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="699ff-136">System.Mdarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="699ff-137">C 스타일 배열 또는 `SAFEARRAY`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-137">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="699ff-138">System.String</span><span class="sxs-lookup"><span data-stu-id="699ff-138">System.String</span></span>](default-marshaling-for-strings.md)|<span data-ttu-id="699ff-139">null 참조로 종료되는 문자열 또는 BSTR로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-139">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|<span data-ttu-id="699ff-140">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="699ff-140">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span></span>|<span data-ttu-id="699ff-141">고정된 메모리 레이아웃을 사용하는 구조로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-141">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="699ff-142">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="699ff-142">System.Szarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="699ff-143">C 스타일 배열 또는 `SAFEARRAY`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-143">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="699ff-144">클래스 및 개체 형식은 COM interop에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="699ff-144">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="699ff-145">Visual Basic, C# 및 C++의 해당 형식은 [클래스 라이브러리 개요](../../standard/class-library-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="699ff-145">For corresponding types in Visual Basic, C#, and C++, see the [Class Library Overview](../../standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699ff-146">참조</span><span class="sxs-lookup"><span data-stu-id="699ff-146">See also</span></span>

- [<span data-ttu-id="699ff-147">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="699ff-147">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)

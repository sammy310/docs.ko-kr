---
title: .NET의 형식 변환표
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET], type conversions
- data types [.NET], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
ms.openlocfilehash: 27578d46a80b0372c6ddc2266a751cd0e6e9aa91
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889454"
---
# <a name="type-conversion-tables-in-net"></a><span data-ttu-id="cbbeb-102">.NET의 형식 변환표</span><span class="sxs-lookup"><span data-stu-id="cbbeb-102">Type Conversion Tables in .NET</span></span>
<span data-ttu-id="cbbeb-103">확대 변환은 한 형식의 값을 크기가 같거나 더 큰 다른 형식으로 변환할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-103">Widening conversion occurs when a value of one type is converted to another type that is of equal or greater size.</span></span> <span data-ttu-id="cbbeb-104">축소 변환은 한 형식의 값을 크기가 더 작은 다른 형식의 값으로 변환할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-104">A narrowing conversion occurs when a value of one type is converted to a value of another type that is of a smaller size.</span></span> <span data-ttu-id="cbbeb-105">이 항목의 표에서는 두 가지 유형의 변환에서 모두 나타나는 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-105">The tables in this topic illustrate the behaviors exhibited by both types of conversions.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="cbbeb-106">확대 변환</span><span class="sxs-lookup"><span data-stu-id="cbbeb-106">Widening Conversions</span></span>  
 <span data-ttu-id="cbbeb-107">다음 표에서는 정보 손실 없이 수행할 수 있는 확대 변환에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-107">The following table describes the widening conversions that can be performed without the loss of information.</span></span>  
  
|<span data-ttu-id="cbbeb-108">형식</span><span class="sxs-lookup"><span data-stu-id="cbbeb-108">Type</span></span>|<span data-ttu-id="cbbeb-109">데이터 손실 없이 다음 형식으로 변환할 수 있음</span><span class="sxs-lookup"><span data-stu-id="cbbeb-109">Can be converted without data loss to</span></span>|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<span data-ttu-id="cbbeb-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="cbbeb-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.SByte>|<span data-ttu-id="cbbeb-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="cbbeb-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="cbbeb-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="cbbeb-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="cbbeb-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="cbbeb-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Char>|<span data-ttu-id="cbbeb-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="cbbeb-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="cbbeb-115"><xref:System.Int64>에서 <xref:System.Double>에서 <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="cbbeb-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="cbbeb-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="cbbeb-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 <span data-ttu-id="cbbeb-117"><xref:System.Single> 또는 <xref:System.Double>로의 일부 확대 변환에서는 정밀도 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-117">Some widening conversions to <xref:System.Single> or <xref:System.Double> can cause a loss of precision.</span></span> <span data-ttu-id="cbbeb-118">다음 표에서는 때때로 정보 손실이 발생할 수 있는 확대 변환에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-118">The following table describes the widening conversions that sometimes result in a loss of information.</span></span>  
  
|<span data-ttu-id="cbbeb-119">형식</span><span class="sxs-lookup"><span data-stu-id="cbbeb-119">Type</span></span>|<span data-ttu-id="cbbeb-120">다음 형식으로 변환할 수 있음</span><span class="sxs-lookup"><span data-stu-id="cbbeb-120">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<span data-ttu-id="cbbeb-121"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="cbbeb-121"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="cbbeb-122"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="cbbeb-122"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="cbbeb-123"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="cbbeb-123"><xref:System.Single>, <xref:System.Double></span></span>|  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="cbbeb-124">축소 변환</span><span class="sxs-lookup"><span data-stu-id="cbbeb-124">Narrowing Conversions</span></span>  
 <span data-ttu-id="cbbeb-125"><xref:System.Single> 또는 <xref:System.Double>로의 축소 변환에서는 정보 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-125">A narrowing conversion to <xref:System.Single> or <xref:System.Double> can cause a loss of information.</span></span> <span data-ttu-id="cbbeb-126">대상 형식이 소스 크기를 제대로 표시할 수 없는 경우 결과 형식이 상수 `PositiveInfinity` 또는 `NegativeInfinity`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-126">If the target type cannot properly express the magnitude of the source, the resulting type is set to the constant `PositiveInfinity` or `NegativeInfinity`.</span></span> <span data-ttu-id="cbbeb-127">`PositiveInfinity`는 양수를 0으로 나눈 결과이며 <xref:System.Single> 또는 <xref:System.Double> 값이 `MaxValue` 필드 값을 초과하는 경우에도 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-127">`PositiveInfinity` results from dividing a positive number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> exceeds the value of the `MaxValue` field.</span></span> <span data-ttu-id="cbbeb-128">`NegativeInfinity`는 음수를 0으로 나눈 결과이며 <xref:System.Single> 또는 <xref:System.Double> 값이 `MinValue` 필드 값보다 작은 경우에도 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-128">`NegativeInfinity` results from dividing a negative number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> falls below the value of the `MinValue` field.</span></span> <span data-ttu-id="cbbeb-129"><xref:System.Double>에서 <xref:System.Single>로 변환하면 `PositiveInfinity` 또는 `NegativeInfinity`가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-129">A conversion from a <xref:System.Double> to a <xref:System.Single> might result in `PositiveInfinity` or `NegativeInfinity`.</span></span>  
  
 <span data-ttu-id="cbbeb-130">축소 변환 시 다른 데이터 형식에 대한 정보 손실도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-130">A narrowing conversion can also result in a loss of information for other data types.</span></span> <span data-ttu-id="cbbeb-131">그러나 변환 중인 형식의 값이 대상 형식의 `MaxValue` 및 `MinValue` 필드에 지정된 범위를 벗어나면 <xref:System.OverflowException>이 throw되며, 런타임에서 변환을 검사하여 대상 형식의 값이 해당 `MaxValue` 또는 `MinValue`를 초과하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-131">However, an <xref:System.OverflowException> is thrown if the value of a type that is being converted falls outside of the range specified by the target type's `MaxValue` and `MinValue` fields, and the conversion is checked by the runtime to ensure that the value of the target type does not exceed its `MaxValue` or `MinValue`.</span></span> <span data-ttu-id="cbbeb-132"><xref:System.Convert?displayProperty=nameWithType> 클래스로 수행하는 변환은 항상 이런 방식으로 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-132">Conversions that are performed with the <xref:System.Convert?displayProperty=nameWithType> class are always checked in this manner.</span></span>  
  
 <span data-ttu-id="cbbeb-133">다음 표에서는 <xref:System.Convert?displayProperty=nameWithType> 사용 시 <xref:System.OverflowException>을 throw하는 변환 또는 변환 중인 형식의 값이 정의된 결과 형식 범위를 벗어나는지 확인한 모든 변환을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbeb-133">The following table lists conversions that throw an <xref:System.OverflowException> using <xref:System.Convert?displayProperty=nameWithType> or any checked conversion if the value of the type being converted is outside the defined range of the resulting type.</span></span>  
  
|<span data-ttu-id="cbbeb-134">형식</span><span class="sxs-lookup"><span data-stu-id="cbbeb-134">Type</span></span>|<span data-ttu-id="cbbeb-135">다음 형식으로 변환할 수 있음</span><span class="sxs-lookup"><span data-stu-id="cbbeb-135">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<span data-ttu-id="cbbeb-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="cbbeb-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="cbbeb-137"><xref:System.Byte>에서 <xref:System.SByte>에서 <xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="cbbeb-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="cbbeb-138"><xref:System.Byte>에서 <xref:System.SByte>에서 <xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="cbbeb-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="cbbeb-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="cbbeb-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="cbbeb-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="cbbeb-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span></span>|  
|<xref:System.Int64>|<span data-ttu-id="cbbeb-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="cbbeb-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="cbbeb-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="cbbeb-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="cbbeb-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="cbbeb-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Single>|<span data-ttu-id="cbbeb-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="cbbeb-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Double>|<span data-ttu-id="cbbeb-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="cbbeb-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbbeb-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbbeb-146">See also</span></span>

- <xref:System.Convert?displayProperty=nameWithType>
- [<span data-ttu-id="cbbeb-147">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="cbbeb-147">Type Conversion in .NET</span></span>](type-conversion.md)

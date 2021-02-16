---
description: '자세히 알아보기: 확대 및 축소 변환 (Visual Basic)'
title: Widening and Narrowing Conversions
ms.date: 07/20/2015
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
ms.openlocfilehash: 2ccd7d51b811aaf0f3e29dc0dc1730dffad2106b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468436"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="13346-103">확대 변환과 축소 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13346-103">Widening and Narrowing Conversions (Visual Basic)</span></span>

<span data-ttu-id="13346-104">형식 변환의 중요 한 고려 사항은 변환 결과가 대상 데이터 형식의 범위 내에 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="13346-104">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="13346-105">*확대 변환* 에서는 원래 데이터의 가능한 값을 허용할 수 있는 데이터 형식으로 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="13346-105">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="13346-106">확대 변환은 원본 값을 유지 하지만 표시를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-106">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="13346-107">이는 정수 계열 형식에서로 변환 하거나에서로 변환 하는 경우에 발생 `Decimal` `Char` `String` 합니다.</span><span class="sxs-lookup"><span data-stu-id="13346-107">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="13346-108">*축소 변환* 은 가능한 값의 일부를 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13346-108">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="13346-109">예를 들어 정수 계열 형식으로 변환 될 때 소수 값이 반올림 되 고 변환 되는 숫자 형식이 `Boolean` 또는로 줄어듭니다 `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="13346-109">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="13346-110">확대 변환</span><span class="sxs-lookup"><span data-stu-id="13346-110">Widening Conversions</span></span>  

 <span data-ttu-id="13346-111">다음 표에서는 표준 확대 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13346-111">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="13346-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="13346-112">Data type</span></span>|<span data-ttu-id="13346-113">데이터 형식 확대 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13346-113">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="13346-114">SByte</span><span class="sxs-lookup"><span data-stu-id="13346-114">SByte</span></span>](../../../language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="13346-115">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="13346-115">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="13346-116">Byte</span><span class="sxs-lookup"><span data-stu-id="13346-116">Byte</span></span>](../../../language-reference/data-types/byte-data-type.md)|<span data-ttu-id="13346-117">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="13346-117">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="13346-118">Short</span><span class="sxs-lookup"><span data-stu-id="13346-118">Short</span></span>](../../../language-reference/data-types/short-data-type.md)|<span data-ttu-id="13346-119">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="13346-119">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="13346-120">UShort</span><span class="sxs-lookup"><span data-stu-id="13346-120">UShort</span></span>](../../../language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="13346-121">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="13346-121">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="13346-122">Integer</span><span class="sxs-lookup"><span data-stu-id="13346-122">Integer</span></span>](../../../language-reference/data-types/integer-data-type.md)|<span data-ttu-id="13346-123">`Integer`, `Long` , `Decimal` , `Single` , `Double` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="13346-123">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="13346-124">UInteger</span><span class="sxs-lookup"><span data-stu-id="13346-124">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="13346-125">`UInteger`,,, `Long` `ULong` `Decimal` , `Single` , `Double` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="13346-125">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="13346-126">Long</span><span class="sxs-lookup"><span data-stu-id="13346-126">Long</span></span>](../../../language-reference/data-types/long-data-type.md)|<span data-ttu-id="13346-127">`Long`, `Decimal` , `Single` , `Double` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="13346-127">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="13346-128">ULong</span><span class="sxs-lookup"><span data-stu-id="13346-128">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="13346-129">`ULong`, `Decimal` , `Single` , `Double` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="13346-129">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="13346-130">10진수</span><span class="sxs-lookup"><span data-stu-id="13346-130">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="13346-131">`Decimal`, `Single` , `Double` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="13346-131">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="13346-132">Single</span><span class="sxs-lookup"><span data-stu-id="13346-132">Single</span></span>](../../../language-reference/data-types/single-data-type.md)|<span data-ttu-id="13346-133">`Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="13346-133">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="13346-134">double</span><span class="sxs-lookup"><span data-stu-id="13346-134">Double</span></span>](../../../language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="13346-135">모든 열거 형식 ([열거형](../../../language-reference/statements/enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="13346-135">Any enumerated type ([Enum](../../../language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="13346-136">기본 정수 형식 및 기본 형식이 확대 되는 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="13346-136">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="13346-137">Char</span><span class="sxs-lookup"><span data-stu-id="13346-137">Char</span></span>](../../../language-reference/data-types/char-data-type.md)|<span data-ttu-id="13346-138">`Char`, `String`</span><span class="sxs-lookup"><span data-stu-id="13346-138">`Char`, `String`</span></span>|  
|<span data-ttu-id="13346-139">`Char` 배열</span><span class="sxs-lookup"><span data-stu-id="13346-139">`Char` array</span></span>|<span data-ttu-id="13346-140">`Char` 배열과 `String`</span><span class="sxs-lookup"><span data-stu-id="13346-140">`Char` array, `String`</span></span>|  
|<span data-ttu-id="13346-141">모든 형식</span><span class="sxs-lookup"><span data-stu-id="13346-141">Any type</span></span>|[<span data-ttu-id="13346-142">개체</span><span class="sxs-lookup"><span data-stu-id="13346-142">Object</span></span>](../../../language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="13346-143">모든 파생 형식</span><span class="sxs-lookup"><span data-stu-id="13346-143">Any derived type</span></span>|<span data-ttu-id="13346-144">파생 되는 기본 형식 <sup>3</sup>입니다.</span><span class="sxs-lookup"><span data-stu-id="13346-144">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="13346-145">모든 형식</span><span class="sxs-lookup"><span data-stu-id="13346-145">Any type</span></span>|<span data-ttu-id="13346-146">구현 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="13346-146">Any interface it implements.</span></span>|  
|[<span data-ttu-id="13346-147">Nothing</span><span class="sxs-lookup"><span data-stu-id="13346-147">Nothing</span></span>](../../../language-reference/nothing.md)|<span data-ttu-id="13346-148">모든 데이터 형식 또는 개체 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="13346-148">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="13346-149"><sup>1</sup> 정의에 따라 모든 데이터 형식이 그 자체로 확대 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13346-149"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="13346-150"><sup>2</sup> ,, `Integer` `UInteger` `Long` , 또는에서 `ULong` `Decimal` 또는로 변환 `Single` 하면 `Double` 전체 자릿수가 손실 될 수 있지만 크기는 손실 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-150"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="13346-151">이러한 의미에서는 정보 손실이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-151">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="13346-152"><sup>3</sup> 파생 형식에서 해당 기본 형식 중 하나로 변환 하는 것은 확대 된 것 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-152"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="13346-153">양쪽 맞춤은 파생 된 형식에 기본 형식의 모든 멤버가 포함 되어 있으므로 기본 형식의 인스턴스로 한정 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13346-153">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="13346-154">반대 방향으로 기본 형식에는 파생 형식으로 정의 된 새 멤버가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-154">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="13346-155">확대 변환은 런타임에 항상 성공 하며 데이터 손실이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-155">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="13346-156">[Option Strict 문이](../../../language-reference/statements/option-strict-statement.md) 유형 검사를 또는로 설정 하는지 여부에 관계 없이 항상 암시적으로이를 수행할 수 있습니다 `On` `Off` .</span><span class="sxs-lookup"><span data-stu-id="13346-156">You can always perform them implicitly, whether the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="13346-157">축소 변환</span><span class="sxs-lookup"><span data-stu-id="13346-157">Narrowing Conversions</span></span>  

 <span data-ttu-id="13346-158">표준 축소 변환에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13346-158">The standard narrowing conversions include the following:</span></span>  
  
- <span data-ttu-id="13346-159">위의 표에서 확대 변환의 반대 방향 (모든 형식이 자체로 확대 됨을 제외 하 고)</span><span class="sxs-lookup"><span data-stu-id="13346-159">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
- <span data-ttu-id="13346-160">두 방향 모두에서 [부울](../../../language-reference/data-types/boolean-data-type.md) 과 임의의 숫자 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="13346-160">Conversions in either direction between [Boolean](../../../language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
- <span data-ttu-id="13346-161">모든 숫자 형식에서 열거형 형식으로 변환 ( `Enum` )</span><span class="sxs-lookup"><span data-stu-id="13346-161">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
- <span data-ttu-id="13346-162">[문자열과](../../../language-reference/data-types/string-data-type.md) 숫자 형식, `Boolean` 또는 [날짜](../../../language-reference/data-types/date-data-type.md) 사이에서 두 방향으로 변환</span><span class="sxs-lookup"><span data-stu-id="13346-162">Conversions in either direction between [String](../../../language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../language-reference/data-types/date-data-type.md)</span></span>  
  
- <span data-ttu-id="13346-163">데이터 형식 또는 개체 형식에서 파생 된 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="13346-163">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="13346-164">축소 변환은 런타임에 항상 성공 하지 않으며 데이터 손실이 발생 하거나 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-164">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="13346-165">대상 데이터 형식이 변환 중인 값을 받을 수 없는 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="13346-165">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="13346-166">예를 들어 숫자를 변환 하면 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-166">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="13346-167">[Option Strict 문이](../../../language-reference/statements/option-strict-statement.md) 형식 확인 스위치를로 설정 하지 않으면 컴파일러에서 축소 변환을 암시적으로 수행할 수 없습니다 `Off` .</span><span class="sxs-lookup"><span data-stu-id="13346-167">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13346-168">컬렉션의 요소에서 루프 제어 변수로의 변환에 대 한 축소 변환 오류는 무시 됩니다 `For Each…Next` .</span><span class="sxs-lookup"><span data-stu-id="13346-168">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="13346-169">자세한 내용 및 예제는 각 항목에 대 한 "축소 변환" 섹션을 참조 하세요. [ 다음 문](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="13346-169">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="13346-170">축소 변환을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="13346-170">When to Use Narrowing Conversions</span></span>  

 <span data-ttu-id="13346-171">원본 값이 오류 또는 데이터 손실 없이 대상 데이터 형식으로 변환 될 수 있다는 것을 알고 있는 경우 축소 변환을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13346-171">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="13346-172">예를 들어 사용자에 게 `String` "True" 또는 "False"가 포함 된 경우 키워드를 사용 하 여 `CBool` 로 변환할 수 있습니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="13346-172">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="13346-173">변환 하는 동안 발생 하는 예외</span><span class="sxs-lookup"><span data-stu-id="13346-173">Exceptions During Conversion</span></span>  

 <span data-ttu-id="13346-174">확대 변환은 항상 성공 하므로 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-174">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="13346-175">축소 변환은 실패할 경우 가장 일반적으로 다음과 같은 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="13346-175">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
- <span data-ttu-id="13346-176"><xref:System.InvalidCastException> -두 형식 간에 변환이 정의 되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="13346-176"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
- <span data-ttu-id="13346-177"><xref:System.OverflowException> -(정수 계열 형식에만 해당) 변환 된 값이 대상 형식에 비해 너무 클 경우</span><span class="sxs-lookup"><span data-stu-id="13346-177"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="13346-178">클래스 또는 구조체에서 해당 클래스 또는 구조체에 대 한 변환 연산자로 사용할 [CType 함수](../../../language-reference/functions/ctype-function.md) 를 정의 하는 경우 `CType` 적절 한 하다 고 판단 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-178">If a class or structure defines a [CType Function](../../../language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="13346-179">또한 `CType` Visual Basic 함수나 .NET Framework 메서드를 호출 하 여 다양 한 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-179">In addition, that `CType` might call Visual Basic functions or .NET Framework methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="13346-180">참조 형식 변환 중 변경</span><span class="sxs-lookup"><span data-stu-id="13346-180">Changes During Reference Type Conversions</span></span>  

 <span data-ttu-id="13346-181">*참조 형식* 에서의 변환은 포인터만 값에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="13346-181">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="13346-182">값 자체는 어떠한 방식으로든 복사 되거나 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-182">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="13346-183">변경할 수 있는 유일한 사항은 포인터를 포함 하는 변수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="13346-183">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="13346-184">다음 예제에서는 데이터 형식이 파생 클래스에서 기본 클래스로 변환 되지만 이제 두 변수가 가리키는 개체가 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13346-184">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```vb  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="13346-185">추가 정보</span><span class="sxs-lookup"><span data-stu-id="13346-185">See also</span></span>

- [<span data-ttu-id="13346-186">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="13346-186">Data Types</span></span>](index.md)
- [<span data-ttu-id="13346-187">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="13346-187">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="13346-188">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="13346-188">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="13346-189">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="13346-189">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="13346-190">방법: Visual Basic에서 Object를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="13346-190">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="13346-191">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="13346-191">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="13346-192">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="13346-192">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="13346-193">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="13346-193">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)

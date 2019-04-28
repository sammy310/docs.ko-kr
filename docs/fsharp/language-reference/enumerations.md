---
title: 열거형
description: 사용 하는 방법을 알아봅니다 F# 코드를 더 읽기 쉽고 쉽게 리터럴 대신 열거형입니다.
ms.date: 05/16/2016
ms.openlocfilehash: a8839b73de074f62606b70ffe969a53b3db753bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921578"
---
# <a name="enumerations"></a><span data-ttu-id="3252b-103">열거형</span><span class="sxs-lookup"><span data-stu-id="3252b-103">Enumerations</span></span>

<span data-ttu-id="3252b-104">*열거형*이 라고도 *열거형*,는 정수 계열 형식 값의 하위 집합에 레이블 할당 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="3252b-105">코드를 더 읽기 쉽고 유지 가능하도록 만들기 위해 리터럴 대신 이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="3252b-106">구문</span><span class="sxs-lookup"><span data-stu-id="3252b-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="3252b-107">설명</span><span class="sxs-lookup"><span data-stu-id="3252b-107">Remarks</span></span>

<span data-ttu-id="3252b-108">열거형 유사한 간단한 값이 있는 구별된 된 공용 구조체는 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="3252b-109">값은 일반적으로 0 또는 1부터 시작 하는 정수 또는 비트 위치를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="3252b-110">열거형은 비트 위치를 나타내는 데, 하는 경우 사용 해야 합니다 [플래그](xref:System.FlagsAttribute) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="3252b-111">열거형의 내부 형식, 예를 들어 하면 사용할 수 있도록 리터럴 접미사를 사용 하 여 같은 사용 되는 리터럴을 기준으로 결정 됩니다 `1u`, `2u`등, 부호 없는 정수 (`uint32`) 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="3252b-112">명명된 된 값을 참조할 때 사용 해야 열거형 형식 자체의 이름 한정자로, 즉 `enum-name.value1`뿐 아니라, `value1`합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="3252b-113">구별 된 공용 구조체의 경우 다르게이 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="3252b-114">열거형에는 항상 이므로이 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="3252b-115">다음 코드는 선언과 열거형의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="3252b-116">쉽게 변환할 수 있습니다 열거형 기본 형식에 적절 한 연산자를 사용 하 여 다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="3252b-117">열거 형식은 다음 기본 형식 중 하나일 수 있습니다: `sbyte`, `byte`, `int16`, `uint16`, `int32`를 `uint32`, `int64`, `uint16`, `uint64`, 및 `char`합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="3252b-118">열거형 형식에서 상속 된 형식으로.NET Framework에서 표현 됩니다 `System.Enum`를 차례로에서 상속 됨 `System.ValueType`합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="3252b-119">따라서 스택 또는 인라인으로 포함 하는 개체에 있는 값 형식 및 기본 형식의 모든 값이 열거형의 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="3252b-120">중요 한 경우 이것이 열거형에 패턴 일치 값으로 명명 되지 않은 값을 catch 하는 패턴을 제공 해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="3252b-121">합니다 `enum` 함수는 F# 명명 된 값 외의 미리 정의 된 다른 값도 열거형 값을 생성 하려면 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="3252b-122">사용 된 `enum` 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="3252b-123">기본값 `enum` 형식을 사용 하 여 함수가 작동 `int32`합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="3252b-124">따라서 다른 기본 형식을 포함 하는 열거형을 사용 하 여 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="3252b-125">대신, 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="3252b-126">또한으로 항상 내보내지는 열거형에 대 한 사례 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="3252b-127">이 C# 및.NET 플랫폼의 rest를 사용 하 여 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3252b-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="3252b-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="3252b-128">See also</span></span>

- [<span data-ttu-id="3252b-129">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3252b-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3252b-130">캐스팅 및 변환</span><span class="sxs-lookup"><span data-stu-id="3252b-130">Casting and Conversions</span></span>](casting-and-conversions.md)
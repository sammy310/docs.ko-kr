---
title: 열거형
description: '리터럴 대신 F # 열거를 사용 하 여 코드를 보다 쉽게 읽고 유지 관리할 수 있도록 하는 방법을 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812109"
---
# <a name="enumerations"></a><span data-ttu-id="244f6-103">열거형</span><span class="sxs-lookup"><span data-stu-id="244f6-103">Enumerations</span></span>

<span data-ttu-id="244f6-104">열거형 ( *열거형* *이 라고도*함)은 레이블이 값의 하위 집합에 할당 되는 정수 계열 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="244f6-105">코드를 더 읽기 쉽고 유지 가능하도록 만들기 위해 리터럴 대신 이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="244f6-106">구문</span><span class="sxs-lookup"><span data-stu-id="244f6-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="244f6-107">설명</span><span class="sxs-lookup"><span data-stu-id="244f6-107">Remarks</span></span>

<span data-ttu-id="244f6-108">열거형은 값을 지정할 수 있는 경우를 제외 하 고는 단순 값을 포함 하는 구별 된 공용 구조체와 매우 유사 하 게 보입니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="244f6-109">값은 일반적으로 0 또는 1에서 시작 하는 정수 이거나 비트 위치를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="244f6-110">열거형이 비트 위치를 나타내도록 하려는 경우 [Flags](xref:System.FlagsAttribute) 특성도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="244f6-111">열거형의 기본 형식은 사용 된 리터럴에 따라 결정 됩니다. 예를 들어, 등의 접미사를 사용 하 여, 등의 `1u` `2u` 부호 없는 정수 () 형식에 대해 리터럴을 사용할 수 있습니다 `uint32` .</span><span class="sxs-lookup"><span data-stu-id="244f6-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="244f6-112">명명 된 값을 참조 하는 경우 열거형 형식의 이름을 한정자로 사용 해야 `enum-name.value1` 합니다. 즉, 뿐 `value1` 입니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="244f6-113">이 동작은 구별 된 공용 구조체의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="244f6-114">열거형은 항상 [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) 특성을 포함 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-114">This is because enumerations always have the [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) attribute.</span></span>

<span data-ttu-id="244f6-115">다음 코드에서는 열거형을 선언 하 고 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="244f6-116">다음 코드와 같이 적절 한 연산자를 사용 하 여 열거형을 기본 형식으로 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="244f6-117">열거 형식은,,,,,,,, `sbyte` `byte` `int16` `uint16` `int32` `uint32` `int64` `uint16` `uint64` 및와 `char` 같은 기본 형식 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="244f6-118">열거형 형식은 .NET Framework에서 상속 되는 형식으로 표현 됩니다 `System.Enum` `System.ValueType` .</span><span class="sxs-lookup"><span data-stu-id="244f6-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="244f6-119">따라서 이러한 값 형식은 스택에 있고 포함 하는 개체의 인라인 값 형식으로, 기본 형식의 값은 열거형의 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="244f6-120">이는 명명 되지 않은 값을 catch 하는 패턴을 제공 해야 하기 때문에 열거 값에 대 한 패턴 일치에서 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="244f6-121">`enum`F # 라이브러리의 함수를 사용 하 여 미리 정의 된 명명 된 값 중 하나 이외의 값을 포함 하 여 열거형 값을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="244f6-122">`enum`다음과 같이 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="244f6-123">기본 `enum` 함수는 형식에서 작동 합니다 `int32` .</span><span class="sxs-lookup"><span data-stu-id="244f6-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="244f6-124">따라서 다른 기본 형식을 가진 열거형 형식에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="244f6-125">대신 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="244f6-126">또한 열거형의 사례는 항상로 내보내집니다 `public` .</span><span class="sxs-lookup"><span data-stu-id="244f6-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="244f6-127">이것은 c # 및 .NET 플랫폼의 나머지 부분에 맞게 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="244f6-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="244f6-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="244f6-128">See also</span></span>

- [<span data-ttu-id="244f6-129">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="244f6-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="244f6-130">캐스팅 및 변환</span><span class="sxs-lookup"><span data-stu-id="244f6-130">Casting and Conversions</span></span>](casting-and-conversions.md)

---
description: '자세한 정보: 데이터 형식에 대 한 효율적인 사용 (Visual Basic)'
title: 데이터 형식의 효율적 사용
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: e7660bbdec530ef18d663975e314d90b64e4b055
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476438"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="4754f-103">데이터 형식의 효율적 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4754f-103">Efficient Use of Data Types (Visual Basic)</span></span>

<span data-ttu-id="4754f-104">선언 되지 않은 변수와 데이터 형식 없이 선언 된 변수에는 `Object` 데이터 형식이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-104">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="4754f-105">이렇게 하면 프로그램을 신속 하 게 작성할 수 있지만 더 느리게 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-105">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="4754f-106">강력한 형식 지정</span><span class="sxs-lookup"><span data-stu-id="4754f-106">Strong Typing</span></span>

 <span data-ttu-id="4754f-107">모든 변수에 대 한 데이터 형식을 지정 하는 것을 *강력한 형식화* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-107">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="4754f-108">강력한 형식화를 사용 하는 경우 다음과 같은 여러 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-108">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="4754f-109">변수에 대해 IntelliSense를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-109">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="4754f-110">이렇게 하면 코드에 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-110">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="4754f-111">컴파일러 형식 검사를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-111">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="4754f-112">이는 오버플로와 같은 오류로 인해 런타임에 실패할 수 있는 문을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-112">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="4754f-113">또한 지원 하지 않는 개체의 메서드에 대 한 호출을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-113">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="4754f-114">그러면 코드 실행 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-114">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="4754f-115">가장 효율적인 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4754f-115">Most Efficient Data Types</span></span>

 <span data-ttu-id="4754f-116">분수를 포함 하지 않는 변수의 경우 정수 계열 데이터 형식이 비정 수 형식 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-116">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="4754f-117">Visual Basic에서 `Integer` 및 `UInteger` 는 가장 효율적인 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-117">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="4754f-118">`Double`현재 플랫폼의 프로세서는 배정밀도로 부동 소수점 연산을 수행 하므로 소수 자릿수의 경우 가장 효율적인 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-118">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="4754f-119">그러나를 사용 하 `Double` 는 연산은와 같은 정수 계열 형식과는 속도가 빠르지 않습니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="4754f-119">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="4754f-120">데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="4754f-120">Specifying Data Type</span></span>

 <span data-ttu-id="4754f-121">[Dim 문을](../../../language-reference/statements/dim-statement.md) 사용 하 여 특정 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-121">Use the [Dim Statement](../../../language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="4754f-122">다음 예제와 같이 [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)또는 [Private](../../../language-reference/modifiers/private.md) 키워드를 사용 하 여 해당 액세스 수준을 동시에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-122">You can simultaneously specify its access level by using the [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), or [Private](../../../language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="4754f-123">문자 변환</span><span class="sxs-lookup"><span data-stu-id="4754f-123">Character Conversion</span></span>

 <span data-ttu-id="4754f-124">`AscW`및 `ChrW` 함수는 유니코드로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-124">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="4754f-125">및에 대 한 기본 설정에서 사용 해야 하며 `Asc` `Chr` ,이는 유니코드로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4754f-125">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="4754f-126">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4754f-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="4754f-127">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4754f-127">Data Types</span></span>](index.md)
- [<span data-ttu-id="4754f-128">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4754f-128">Numeric Data Types</span></span>](numeric-data-types.md)
- [<span data-ttu-id="4754f-129">변수 선언</span><span class="sxs-lookup"><span data-stu-id="4754f-129">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="4754f-130">IntelliSense 사용</span><span class="sxs-lookup"><span data-stu-id="4754f-130">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)

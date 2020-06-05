---
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
ms.openlocfilehash: 0de02840cb18fde16134ef43df9d63abb503c979
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394173"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="c561b-102">데이터 형식의 효율적 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c561b-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="c561b-103">선언 되지 않은 변수와 데이터 형식 없이 선언 된 변수에는 `Object` 데이터 형식이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="c561b-104">이렇게 하면 프로그램을 신속 하 게 작성할 수 있지만 더 느리게 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="c561b-105">강력한 형식 지정</span><span class="sxs-lookup"><span data-stu-id="c561b-105">Strong Typing</span></span>
 <span data-ttu-id="c561b-106">모든 변수에 대 한 데이터 형식을 지정 하는 것을 *강력한 형식화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="c561b-107">강력한 형식화를 사용 하는 경우 다음과 같은 여러 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-107">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="c561b-108">변수에 대해 IntelliSense를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="c561b-109">이렇게 하면 코드에 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-109">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="c561b-110">컴파일러 형식 검사를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="c561b-111">이는 오버플로와 같은 오류로 인해 런타임에 실패할 수 있는 문을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="c561b-112">또한 지원 하지 않는 개체의 메서드에 대 한 호출을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-112">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="c561b-113">그러면 코드 실행 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-113">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="c561b-114">가장 효율적인 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c561b-114">Most Efficient Data Types</span></span>
 <span data-ttu-id="c561b-115">분수를 포함 하지 않는 변수의 경우 정수 계열 데이터 형식이 비정 수 형식 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="c561b-116">Visual Basic에서 `Integer` 및 `UInteger` 는 가장 효율적인 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="c561b-117">`Double`현재 플랫폼의 프로세서는 배정밀도로 부동 소수점 연산을 수행 하므로 소수 자릿수의 경우 가장 효율적인 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="c561b-118">그러나를 사용 하 `Double` 는 연산은와 같은 정수 계열 형식과는 속도가 빠르지 않습니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="c561b-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="c561b-119">데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="c561b-119">Specifying Data Type</span></span>
 <span data-ttu-id="c561b-120">[Dim 문을](../../../language-reference/statements/dim-statement.md) 사용 하 여 특정 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-120">Use the [Dim Statement](../../../language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="c561b-121">다음 예제와 같이 [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)또는 [Private](../../../language-reference/modifiers/private.md) 키워드를 사용 하 여 해당 액세스 수준을 동시에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-121">You can simultaneously specify its access level by using the [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), or [Private](../../../language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="c561b-122">문자 변환</span><span class="sxs-lookup"><span data-stu-id="c561b-122">Character Conversion</span></span>
 <span data-ttu-id="c561b-123">`AscW`및 `ChrW` 함수는 유니코드로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="c561b-124">및에 대 한 기본 설정에서 사용 해야 하며 `Asc` `Chr` ,이는 유니코드로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c561b-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="c561b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c561b-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="c561b-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c561b-126">Data Types</span></span>](index.md)
- [<span data-ttu-id="c561b-127">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c561b-127">Numeric Data Types</span></span>](numeric-data-types.md)
- [<span data-ttu-id="c561b-128">변수 선언</span><span class="sxs-lookup"><span data-stu-id="c561b-128">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="c561b-129">IntelliSense 사용</span><span class="sxs-lookup"><span data-stu-id="c561b-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)

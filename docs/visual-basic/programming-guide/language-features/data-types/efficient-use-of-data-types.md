---
title: 데이터 형식의 효율적 사용(Visual Basic)
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
ms.openlocfilehash: 0b517bca3a9e296eb891e30df91c1d32eb357432
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830125"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="5723c-102">데이터 형식의 효율적 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5723c-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="5723c-103">데이터 형식 없이 선언 된 변수와 선언 되지 않은 변수 할당 되는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="5723c-104">이 사용 하면 쉽게 프로그램을 신속 하 게 작성할 수 있지만 느리게 실행 되기를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="5723c-105">강력한 형식화</span><span class="sxs-lookup"><span data-stu-id="5723c-105">Strong Typing</span></span>  
 <span data-ttu-id="5723c-106">모든 변수에 대 한 데이터 형식을 지정 하는 이라고 *강력한 형식화*합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="5723c-107">강력한 형식 지정을 사용 하 여에 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="5723c-108">변수에 대 한 IntelliSense 지원을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="5723c-109">이렇게 하면 코드에서 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="5723c-110">이 컴파일러에서 형식 검사 하는 작업을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="5723c-111">이 문은 런타임에 오버플로 같은 오류로 인해 실패할 수 있는 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="5723c-112">또한 지원 하지 않는 개체에 메서드 호출을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="5723c-113">코드의 더 빠른 실행에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="5723c-114">가장 효율적인 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5723c-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="5723c-115">분수를 포함 하지 않은 변수는 정수 데이터 형식의 비정 수 형식 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="5723c-116">Visual basic에서는 `Integer` 및 `UInteger` 은 가장 효율적인 숫자 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="5723c-117">소수에 `Double` 가장 효율적인 데이터 형식 이므로 현재 플랫폼의 프로세서에서 배정밀도 부동 소수점 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="5723c-118">그러나 작업과 `Double` 와 같은 정수 계열 형식과 마찬가지로 빠르지 않습니다 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="5723c-119">데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="5723c-119">Specifying Data Type</span></span>  
 <span data-ttu-id="5723c-120">사용 된 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 특정 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="5723c-121">해당 액세스 수준을 사용 하 여 동시에 지정할 수 있습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md)를 [보호 된](../../../../visual-basic/language-reference/modifiers/protected.md)를 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 에서처럼 키워드는 다음 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="5723c-122">문자 변환</span><span class="sxs-lookup"><span data-stu-id="5723c-122">Character Conversion</span></span>  
 <span data-ttu-id="5723c-123">합니다 `AscW` 및 `ChrW` 함수는 유니코드에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="5723c-124">우선적으로 사용 해야 `Asc` 고 `Chr`, 내부 및 외부로 유니코드 변환 해야 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5723c-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="5723c-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="5723c-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5723c-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="5723c-127">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5723c-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="5723c-128">변수 선언</span><span class="sxs-lookup"><span data-stu-id="5723c-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="5723c-129">IntelliSense 사용</span><span class="sxs-lookup"><span data-stu-id="5723c-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)

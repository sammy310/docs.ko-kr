---
description: '자세한 정보: ByVal (Visual Basic)'
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: cd7116c0bcc3d263cc2bb6a9b95e46e8ff0cc116
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774618"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="f26b4-103">ByVal(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f26b4-103">ByVal (Visual Basic)</span></span>

<span data-ttu-id="f26b4-104">호출 된 프로시저 또는 속성이 호출 코드에서 인수를 기반으로 하는 변수의 값을 변경할 수 없도록 인수를 [값으로](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)전달 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f26b4-104">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="f26b4-105">한정자를 지정 하지 않으면 기본적으로 ByVal이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f26b4-105">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="f26b4-106">기본값 이기 때문에 메서드 시그니처에서 키워드를 명시적으로 지정 하지 않아도 `ByVal` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f26b4-106">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="f26b4-107">이 경우 잡음이 있는 코드를 생성 하 고 기본값이 아닌 `ByRef` 키워드가 간과 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b4-107">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="f26b4-108">설명</span><span class="sxs-lookup"><span data-stu-id="f26b4-108">Remarks</span></span>

 <span data-ttu-id="f26b4-109">`ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b4-109">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="f26b4-110">Declare 문</span><span class="sxs-lookup"><span data-stu-id="f26b4-110">Declare Statement</span></span>](../statements/declare-statement.md)

 [<span data-ttu-id="f26b4-111">Function 문</span><span class="sxs-lookup"><span data-stu-id="f26b4-111">Function Statement</span></span>](../statements/function-statement.md)
  
 [<span data-ttu-id="f26b4-112">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="f26b4-112">Operator Statement</span></span>](../statements/operator-statement.md)
  
 [<span data-ttu-id="f26b4-113">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f26b4-113">Property Statement</span></span>](../statements/property-statement.md)
  
 [<span data-ttu-id="f26b4-114">Sub 문</span><span class="sxs-lookup"><span data-stu-id="f26b4-114">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="f26b4-115">예제</span><span class="sxs-lookup"><span data-stu-id="f26b4-115">Example</span></span>

 <span data-ttu-id="f26b4-116">다음 예제에서는 `ByVal` 참조 형식 인수를 사용 하 여 매개 변수 전달 메커니즘을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f26b4-116">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="f26b4-117">예제에서 인수는 `c1` 클래스의 인스턴스입니다 `Class1` .</span><span class="sxs-lookup"><span data-stu-id="f26b4-117">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="f26b4-118">`ByVal` 프로시저의 코드가 참조 인수의 기본 값을 변경 하는 것을 방지 `c1` 하지만의 액세스 가능 필드와 속성은 보호 하지 않습니다 `c1` .</span><span class="sxs-lookup"><span data-stu-id="f26b4-118">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="f26b4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f26b4-119">See also</span></span>

- [<span data-ttu-id="f26b4-120">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="f26b4-120">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="f26b4-121">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f26b4-121">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)

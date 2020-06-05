---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373026"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="01d0c-102">ByVal(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01d0c-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="01d0c-103">호출 된 프로시저 또는 속성이 호출 코드에서 인수를 기반으로 하는 변수의 값을 변경할 수 없도록 인수를 [값으로](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)전달 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d0c-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="01d0c-104">한정자를 지정 하지 않으면 기본적으로 ByVal이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d0c-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="01d0c-105">기본값 이기 때문에 메서드 시그니처에서 키워드를 명시적으로 지정 하지 않아도 `ByVal` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d0c-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="01d0c-106">이 경우 잡음이 있는 코드를 생성 하 고 기본값이 아닌 `ByRef` 키워드가 간과 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="01d0c-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="01d0c-107">설명</span><span class="sxs-lookup"><span data-stu-id="01d0c-107">Remarks</span></span>
 <span data-ttu-id="01d0c-108">`ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d0c-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="01d0c-109">Declare 문</span><span class="sxs-lookup"><span data-stu-id="01d0c-109">Declare Statement</span></span>](../statements/declare-statement.md)

 [<span data-ttu-id="01d0c-110">Function 문</span><span class="sxs-lookup"><span data-stu-id="01d0c-110">Function Statement</span></span>](../statements/function-statement.md)
  
 [<span data-ttu-id="01d0c-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="01d0c-111">Operator Statement</span></span>](../statements/operator-statement.md)
  
 [<span data-ttu-id="01d0c-112">Property Statement</span><span class="sxs-lookup"><span data-stu-id="01d0c-112">Property Statement</span></span>](../statements/property-statement.md)
  
 [<span data-ttu-id="01d0c-113">Sub 문</span><span class="sxs-lookup"><span data-stu-id="01d0c-113">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="01d0c-114">예제</span><span class="sxs-lookup"><span data-stu-id="01d0c-114">Example</span></span>
 <span data-ttu-id="01d0c-115">다음 예제에서는 `ByVal` 참조 형식 인수를 사용 하 여 매개 변수 전달 메커니즘을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01d0c-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="01d0c-116">예제에서 인수는 `c1` 클래스의 인스턴스입니다 `Class1` .</span><span class="sxs-lookup"><span data-stu-id="01d0c-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="01d0c-117">`ByVal`프로시저의 코드가 참조 인수의 기본 값을 변경 하는 것을 방지 `c1` 하지만의 액세스 가능 필드와 속성은 보호 하지 않습니다 `c1` .</span><span class="sxs-lookup"><span data-stu-id="01d0c-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="01d0c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01d0c-118">See also</span></span>

- [<span data-ttu-id="01d0c-119">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="01d0c-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="01d0c-120">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="01d0c-120">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)

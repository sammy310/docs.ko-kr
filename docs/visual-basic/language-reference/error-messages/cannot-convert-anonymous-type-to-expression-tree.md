---
title: 익명 형식이 다른 필드를 초기화하는 데 사용되는 필드를 포함하고 있으므로 식 트리로 변환할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: ba14c0cd8781b8771ac8b746e3efec29a457294a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701185"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="3ce9b-102">익명 형식이 다른 필드를 초기화하는 데 사용되는 필드를 포함하고 있으므로 식 트리로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce9b-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="3ce9b-103">익명 형식의 속성 하나를 사용 하 여 익명 형식의 다른 속성을 초기화 하는 경우 컴파일러는 익명의 식 트리로의 변환을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce9b-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="3ce9b-104">예를 들어 다음 코드에서 `Prop1`은 초기화 목록에 선언 된 다음 `Prop2`의 초기 값으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce9b-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="3ce9b-105">**오류 ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="3ce9b-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3ce9b-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3ce9b-106">To correct this error</span></span>  
  
- <span data-ttu-id="3ce9b-107">@No__t-0에 대 한 초기 값을 지역 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce9b-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="3ce9b-108">다음 코드와 같이 `Prop1` 및 `Prop2` 모두에 해당 변수를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce9b-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```vb  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3ce9b-109">참조</span><span class="sxs-lookup"><span data-stu-id="3ce9b-109">See also</span></span>

- [<span data-ttu-id="3ce9b-110">익명 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ce9b-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="3ce9b-111">식 트리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ce9b-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- <span data-ttu-id="3ce9b-112">[방법: 식 트리를 사용 하 여 동적 쿼리 (Visual Basic) @no__t 빌드-0</span><span class="sxs-lookup"><span data-stu-id="3ce9b-112">[How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)</span></span>

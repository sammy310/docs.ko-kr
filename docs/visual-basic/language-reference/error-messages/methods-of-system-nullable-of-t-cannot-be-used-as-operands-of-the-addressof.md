---
title: "'System.Nullable(Of T)'의 메서드는 'AddressOf' 연산자의 피연산자로 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 54d66a60d20a6add4c2b4a160f87b58b5a1d00e9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817268"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a><span data-ttu-id="ce33b-102">'System.Nullable(Of T)'의 메서드는 'AddressOf' 연산자의 피연산자로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce33b-102">Methods of 'System.Nullable(Of T)' cannot be used as operands of the 'AddressOf' operator</span></span>
<span data-ttu-id="ce33b-103">문을 사용 하는 `AddressOf` 의 프로시저를 나타내는 피연산자와 연산자를 <xref:System.Nullable%601> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ce33b-103">A statement uses the `AddressOf` operator with an operand that represents a procedure of the <xref:System.Nullable%601> structure.</span></span>  
  
 <span data-ttu-id="ce33b-104">**오류 ID:** BC32126</span><span class="sxs-lookup"><span data-stu-id="ce33b-104">**Error ID:** BC32126</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce33b-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ce33b-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ce33b-106">프로시저 이름을 대체 합니다 `AddressOf` 소속 된 피연산자를 사용 하 여 절 <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="ce33b-106">Replace the procedure name in the `AddressOf` clause with an operand that is not a member of <xref:System.Nullable%601>.</span></span>  
  
-   <span data-ttu-id="ce33b-107">메서드를 래핑하는 클래스를 작성 <xref:System.Nullable%601> 사용 하려는.</span><span class="sxs-lookup"><span data-stu-id="ce33b-107">Write a class that wraps the method of <xref:System.Nullable%601> that you want to use.</span></span> <span data-ttu-id="ce33b-108">다음 예제에서는 `NullableWrapper` 라는 새 메서드를 정의 하는 클래스 `GetValueOrDefault`합니다.</span><span class="sxs-lookup"><span data-stu-id="ce33b-108">In the following example, the `NullableWrapper` class defines a new method named `GetValueOrDefault`.</span></span> <span data-ttu-id="ce33b-109">이 새 메서드 멤버인 아니므로 <xref:System.Nullable%601>에 적용할 수 있습니다 `nullInstance`, nullable 형식에 대 한 인수에 인스턴스의 `AddressOf`합니다.</span><span class="sxs-lookup"><span data-stu-id="ce33b-109">Because this new method is not a member of <xref:System.Nullable%601>, it can be applied to `nullInstance`, an instance of a nullable type, to form an argument for `AddressOf`.</span></span>  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce33b-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="ce33b-110">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="ce33b-111">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="ce33b-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="ce33b-112">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="ce33b-112">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ce33b-113">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="ce33b-113">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

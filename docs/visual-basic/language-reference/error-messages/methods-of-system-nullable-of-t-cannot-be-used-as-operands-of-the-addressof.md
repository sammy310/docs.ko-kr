---
title: "'System.Nullable(Of T)'의 메서드는 'AddressOf' 연산자의 피연산자로 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 61c6fe7c33b3292066e653304ded43a863413723
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397222"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a><span data-ttu-id="c1807-102">'System.Nullable(Of T)'의 메서드는 'AddressOf' 연산자의 피연산자로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1807-102">Methods of 'System.Nullable(Of T)' cannot be used as operands of the 'AddressOf' operator</span></span>
<span data-ttu-id="c1807-103">문은 `AddressOf` 구조체의 프로시저를 나타내는 피연산자와 함께 연산자를 사용 합니다 <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="c1807-103">A statement uses the `AddressOf` operator with an operand that represents a procedure of the <xref:System.Nullable%601> structure.</span></span>  
  
 <span data-ttu-id="c1807-104">**오류 ID:** BC32126</span><span class="sxs-lookup"><span data-stu-id="c1807-104">**Error ID:** BC32126</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1807-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c1807-105">To correct this error</span></span>  
  
- <span data-ttu-id="c1807-106">절의 프로시저 이름을 `AddressOf` 의 멤버가 아닌 피연산자로 바꿉니다 <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="c1807-106">Replace the procedure name in the `AddressOf` clause with an operand that is not a member of <xref:System.Nullable%601>.</span></span>  
  
- <span data-ttu-id="c1807-107">사용 하려는의 메서드를 래핑하는 클래스를 작성 <xref:System.Nullable%601> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1807-107">Write a class that wraps the method of <xref:System.Nullable%601> that you want to use.</span></span> <span data-ttu-id="c1807-108">다음 예제에서 `NullableWrapper` 클래스는 라는 새 메서드를 정의 `GetValueOrDefault` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1807-108">In the following example, the `NullableWrapper` class defines a new method named `GetValueOrDefault`.</span></span> <span data-ttu-id="c1807-109">이 새 메서드는의 멤버가 아니므로 <xref:System.Nullable%601> `nullInstance` nullable 형식의 인스턴스인에 적용 하 여에 대 한 인수를 형성할 수 있습니다 `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="c1807-109">Because this new method is not a member of <xref:System.Nullable%601>, it can be applied to `nullInstance`, an instance of a nullable type, to form an argument for `AddressOf`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1807-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1807-110">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="c1807-111">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="c1807-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="c1807-112">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="c1807-112">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="c1807-113">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="c1807-113">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)

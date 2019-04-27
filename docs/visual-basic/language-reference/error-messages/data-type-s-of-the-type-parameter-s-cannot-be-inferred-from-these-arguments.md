---
title: 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 91ee4bf9242df822890b0a171061f375a3b24cbc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803872"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="da32b-102">이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="da32b-103">이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="da32b-104">데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="da32b-105">이 오류는 오버로드 확인에 실패한 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="da32b-106">특정 오버로드 후보가 제거된 이유를 나타내는 하위 메시지로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="da32b-107">오류 메시지 컴파일러 형식 매개 변수 데이터 형식을 찾는 데 형식 유추를 사용할 수 없습니다를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da32b-108">인수 지정이 옵션이 아닌 경우(예: 쿼리 식의 쿼리 연산자) 두 번째 문장 없이 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="da32b-109">다음 코드에서는 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-109">The following code demonstrates the error.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 <span data-ttu-id="da32b-110">**오류 ID:** BC36647 및 BC36644</span><span class="sxs-lookup"><span data-stu-id="da32b-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da32b-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="da32b-111">To correct this error</span></span>  
  
-   <span data-ttu-id="da32b-112">형식 유추를 사용하지 않고 형식 매개 변수에 대한 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da32b-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da32b-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="da32b-113">See also</span></span>

- [<span data-ttu-id="da32b-114">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="da32b-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="da32b-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da32b-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="da32b-116">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="da32b-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)

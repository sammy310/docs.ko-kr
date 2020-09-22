---
title: 람다 식은 'Select Case' 문의 첫 번째 식에 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 9f200ea44e7505c407c7df56e596435024394875
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873872"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="15c1c-102">람다 식은 'Select Case' 문의 첫 번째 식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1c-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>

<span data-ttu-id="15c1c-103">문에서는 테스트 식에 람다 식을 사용할 수 없습니다 `Select Case` .</span><span class="sxs-lookup"><span data-stu-id="15c1c-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="15c1c-104">람다 식 정의에서 함수를 반환 하 고 문의 테스트 식이 `Select Case` 기본 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1c-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="15c1c-105">다음 코드는이 오류를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="15c1c-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="15c1c-106">**오류 ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="15c1c-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="15c1c-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="15c1c-107">To correct this error</span></span>  
  
- <span data-ttu-id="15c1c-108">코드를 검사하여 `If...Then...Else` 문과 같은 다른 조건부 생성이 적합한지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="15c1c-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
- <span data-ttu-id="15c1c-109">다음 코드와 같이 함수를 호출 하려고 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c1c-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="15c1c-110">참조</span><span class="sxs-lookup"><span data-stu-id="15c1c-110">See also</span></span>

- [<span data-ttu-id="15c1c-111">람다 식</span><span class="sxs-lookup"><span data-stu-id="15c1c-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="15c1c-112">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="15c1c-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="15c1c-113">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="15c1c-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)

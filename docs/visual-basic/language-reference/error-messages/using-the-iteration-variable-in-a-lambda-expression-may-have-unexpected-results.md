---
title: 람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 618fc88a2ca92ec911a3fbd82de580403d924430
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841102"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="d6a6e-102">람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="d6a6e-103">람다 식에 반복 변수를 사용 하 여 있을 예기치 않은 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="d6a6e-104">대신 루프 내의 지역 변수를 만들고 반복 변수의 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="d6a6e-105">루프 반복 변수를 사용 하 여 루프 내에서 선언 된 람다 식에서이 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="d6a6e-106">예를 들어, 다음 예제에서는 경고를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="d6a6e-107">다음 예제에서는 발생할 수 있는 예기치 않은 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-107">The following example shows the unexpected results that might occur.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d6a6e-108">합니다 `For` 루프는 각 루프 반복 변수의 값을 반환 람다 식의 배열을 만듭니다 `i`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="d6a6e-109">람다 식의 평가 하는 경우는 `For Each` 루프를 예상할 수 0, 1, 2, 3 및 4 표시의 연속 값을 보려면 `i` 에 `For` 루프.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="d6a6e-110">최종 값 대신 표시 `i` 다섯 번 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="d6a6e-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-111">By default, this message is a warning.</span></span> <span data-ttu-id="d6a6e-112">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d6a6e-113">**오류 ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="d6a6e-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6a6e-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d6a6e-114">To correct this error</span></span>  
  
-   <span data-ttu-id="d6a6e-115">반복 변수의 값을 지역 변수에 할당 및 람다 식에 지역 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a6e-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6a6e-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d6a6e-116">See also</span></span>

- [<span data-ttu-id="d6a6e-117">람다 식</span><span class="sxs-lookup"><span data-stu-id="d6a6e-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)

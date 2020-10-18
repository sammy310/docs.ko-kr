---
title: 람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: d0deea94084565ea91debe2b6db30def4cd9e00e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161493"
---
# <a name="bc42324-using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="76938-102">BC42324: 람다 식에 반복 변수를 사용 하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76938-102">BC42324: Using the iteration variable in a lambda expression may have unexpected results</span></span>

<span data-ttu-id="76938-103">람다 식에 반복 변수를 사용 하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76938-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="76938-104">대신 루프 내에서 지역 변수를 만들고 반복 변수의 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="76938-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>

 <span data-ttu-id="76938-105">이 경고는 루프 내에서 선언 된 람다 식에서 루프 반복 변수를 사용 하는 경우에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="76938-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="76938-106">예를 들어 다음 예제에서는 경고가 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="76938-106">For example, the following example causes the warning to appear.</span></span>

```vb
For i As Integer = 1 To 10
    ' The warning is given for the use of i.
    Dim exampleFunc As Func(Of Integer) = Function() i
Next
```

 <span data-ttu-id="76938-107">다음 예에서는 예기치 않은 결과가 발생할 수 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76938-107">The following example shows the unexpected results that might occur.</span></span>

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

 <span data-ttu-id="76938-108">`For`루프는 각각 루프 반복 변수의 값을 반환 하는 람다 식의 배열을 만듭니다 `i` .</span><span class="sxs-lookup"><span data-stu-id="76938-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="76938-109">루프에서 람다 식을 계산 하는 경우 `For Each` 루프에서의 연속 값이 0, 1, 2, 3 및 4로 표시 될 수 있습니다 `i` `For` .</span><span class="sxs-lookup"><span data-stu-id="76938-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="76938-110">대신, 최종 값이 `i` 5 번 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76938-110">Instead, you see the final value of `i` displayed five times:</span></span>

 `5`

 `5`

 `5`

 `5`

 `5`

 <span data-ttu-id="76938-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="76938-111">By default, this message is a warning.</span></span> <span data-ttu-id="76938-112">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76938-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="76938-113">**오류 ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="76938-113">**Error ID:** BC42324</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="76938-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="76938-114">To correct this error</span></span>

- <span data-ttu-id="76938-115">반복 변수의 값을 지역 변수에 할당 하 고 람다 식에서 지역 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76938-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="76938-116">참조</span><span class="sxs-lookup"><span data-stu-id="76938-116">See also</span></span>

- [<span data-ttu-id="76938-117">람다 식</span><span class="sxs-lookup"><span data-stu-id="76938-117">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)

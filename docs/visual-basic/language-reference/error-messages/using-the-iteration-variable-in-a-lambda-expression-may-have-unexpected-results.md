---
description: '자세히 알아보기: BC42324: 람다 식에 반복 변수를 사용 하면 예기치 않은 결과가 발생할 수 있습니다.'
title: 람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: a21e33c9a8737642d4d0764e92b1fbb2213f9602
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640877"
---
# <a name="bc42324-using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="c0ec0-103">BC42324: 람다 식에 반복 변수를 사용 하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-103">BC42324: Using the iteration variable in a lambda expression may have unexpected results</span></span>

<span data-ttu-id="c0ec0-104">람다 식에 반복 변수를 사용 하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-104">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="c0ec0-105">대신 루프 내에서 지역 변수를 만들고 반복 변수의 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-105">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>

 <span data-ttu-id="c0ec0-106">이 경고는 루프 내에서 선언 된 람다 식에서 루프 반복 변수를 사용 하는 경우에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-106">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="c0ec0-107">예를 들어 다음 예제에서는 경고가 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-107">For example, the following example causes the warning to appear.</span></span>

```vb
For i As Integer = 1 To 10
    ' The warning is given for the use of i.
    Dim exampleFunc As Func(Of Integer) = Function() i
Next
```

 <span data-ttu-id="c0ec0-108">다음 예에서는 예기치 않은 결과가 발생할 수 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-108">The following example shows the unexpected results that might occur.</span></span>

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

 <span data-ttu-id="c0ec0-109">`For`루프는 각각 루프 반복 변수의 값을 반환 하는 람다 식의 배열을 만듭니다 `i` .</span><span class="sxs-lookup"><span data-stu-id="c0ec0-109">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="c0ec0-110">루프에서 람다 식을 계산 하는 경우 `For Each` 루프에서의 연속 값이 0, 1, 2, 3 및 4로 표시 될 수 있습니다 `i` `For` .</span><span class="sxs-lookup"><span data-stu-id="c0ec0-110">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="c0ec0-111">대신, 최종 값이 `i` 5 번 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-111">Instead, you see the final value of `i` displayed five times:</span></span>

 `5`

 `5`

 `5`

 `5`

 `5`

 <span data-ttu-id="c0ec0-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-112">By default, this message is a warning.</span></span> <span data-ttu-id="c0ec0-113">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-113">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="c0ec0-114">**오류 ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="c0ec0-114">**Error ID:** BC42324</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c0ec0-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c0ec0-115">To correct this error</span></span>

- <span data-ttu-id="c0ec0-116">반복 변수의 값을 지역 변수에 할당 하 고 람다 식에서 지역 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ec0-116">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c0ec0-117">참조</span><span class="sxs-lookup"><span data-stu-id="c0ec0-117">See also</span></span>

- [<span data-ttu-id="c0ec0-118">람다 식</span><span class="sxs-lookup"><span data-stu-id="c0ec0-118">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)

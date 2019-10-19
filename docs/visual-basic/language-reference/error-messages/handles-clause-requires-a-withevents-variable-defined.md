---
title: Handles 절에는 포함하는 형식 또는 해당 형식의 기본 형식 중 하나에 정의된 WithEvents 변수가 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 191415408f607d0ff768e50c41fa9b3c4405a688
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582821"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="e4970-102">Handles 절에는 포함하는 형식 또는 해당 형식의 기본 형식 중 하나에 정의된 WithEvents 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4970-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="e4970-103">@No__t_1 절에 `WithEvents` 변수를 제공 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e4970-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="e4970-104">프로시저 선언 끝의 `Handles` 키워드는 `WithEvents` 키워드를 사용 하 여 선언 된 개체 변수에 의해 발생 된 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4970-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="e4970-105">**오류 ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="e4970-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e4970-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e4970-106">To correct this error</span></span>

<span data-ttu-id="e4970-107">필요한 `WithEvents` 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4970-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="e4970-108">예제</span><span class="sxs-lookup"><span data-stu-id="e4970-108">Example</span></span>

<span data-ttu-id="e4970-109">다음 예제에서는 <xref:System.Timers.Timer?displayProperty=nameWithType> 인스턴스의 정의에 [WithEvents](../modifiers/withevents.md) 키워드가 사용 되지 않으므로 Visual Basic에서 컴파일러 오류 `BC30506`을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4970-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

<span data-ttu-id="e4970-110">다음 예제는 `_timer1` 변수가 `WithEvents` 키워드를 사용 하 여 정의 되기 때문에 성공적으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4970-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a><span data-ttu-id="e4970-111">참조</span><span class="sxs-lookup"><span data-stu-id="e4970-111">See also</span></span>

- [<span data-ttu-id="e4970-112">Handles</span><span class="sxs-lookup"><span data-stu-id="e4970-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)

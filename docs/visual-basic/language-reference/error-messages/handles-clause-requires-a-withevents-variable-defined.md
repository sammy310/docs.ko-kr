---
description: '자세히 알아보기: BC30506: Handles 절에는 포함 하는 형식 또는 해당 기본 형식 중 하나에 정의 된 WithEvents 변수가 필요 합니다.'
title: Handles 절에는 포함하는 형식 또는 해당 형식의 기본 형식 중 하나에 정의된 WithEvents 변수가 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 7253a4766b2015ccbe0ae62f64bc10aaca073dc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796121"
---
# <a name="bc30506-handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="53eac-103">BC30506: Handles 절에는 포함 하는 형식 또는 해당 기본 형식 중 하나에 정의 된 WithEvents 변수가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="53eac-103">BC30506: Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="53eac-104">절에 변수를 제공 하지 않았습니다 `WithEvents` `Handles` .</span><span class="sxs-lookup"><span data-stu-id="53eac-104">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="53eac-105">`Handles`프로시저 선언 끝에 있는 키워드를 사용 하면 키워드를 사용 하 여 선언 된 개체 변수에 의해 발생 된 이벤트를 처리할 수 `WithEvents` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53eac-105">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="53eac-106">**오류 ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="53eac-106">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="53eac-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="53eac-107">To correct this error</span></span>

<span data-ttu-id="53eac-108">필요한 변수를 제공 `WithEvents` 합니다.</span><span class="sxs-lookup"><span data-stu-id="53eac-108">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="53eac-109">예제</span><span class="sxs-lookup"><span data-stu-id="53eac-109">Example</span></span>

<span data-ttu-id="53eac-110">다음 예제에서는 `BC30506` [WithEvents](../modifiers/withevents.md) 키워드가 인스턴스의 정의에 사용 되지 않기 때문에 Visual Basic는 컴파일러 오류를 생성 <xref:System.Timers.Timer?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="53eac-110">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="53eac-111">다음 예제는 키워드를 사용 하 여 변수를 정의 하기 때문에 성공적으로 컴파일됩니다 `_timer1` `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="53eac-111">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="53eac-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53eac-112">See also</span></span>

- [<span data-ttu-id="53eac-113">핸들</span><span class="sxs-lookup"><span data-stu-id="53eac-113">Handles</span></span>](../statements/handles-clause.md)

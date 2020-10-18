---
title: 이벤트 처리기에서 람다 식이 제거되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 5a30e63044b51f8176dfeebdcc9eb8fd517739ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163118"
---
# <a name="bc42326-lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="7591c-102">BC42326:이 이벤트 처리기에서 람다 식이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-102">BC42326: Lambda expression will not be removed from this event handler</span></span>

<span data-ttu-id="7591c-103">이 이벤트 처리기에서 람다 식이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="7591c-104">변수에 람다 식을 할당 하 고 변수를 사용 하 여 이벤트를 추가 및 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>

<span data-ttu-id="7591c-105">이벤트 처리기에 람다 식을 사용 하는 경우에는 원하는 동작이 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="7591c-106">컴파일러는 동일한 경우에도 각 람다 식 정의에 대 한 새 메서드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="7591c-107">따라서 다음 코드는를 표시 합니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="7591c-107">Therefore, the following code displays `False`.</span></span>

```vb
Module Module1

    Sub Main()
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1
        Console.WriteLine(fun1 = fun2)
    End Sub

    Delegate Function ChangeInteger(ByVal x As Integer) As Integer

End Module
```

<span data-ttu-id="7591c-108">이벤트 처리기에 람다 식을 사용 하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="7591c-109">다음 예제에서는에 의해 추가 된 람다 식이 `AddHandler` 문에 의해 제거 되지 않습니다 `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="7591c-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Sub Main()

        ' The following line adds one listener to the event.
        AddHandler ProcessInteger, Function(m As Integer) m

        ' The following statement searches the current listeners
        ' for a match to remove. However, this lambda is not the same
        ' as the previous one, so nothing is removed.
        RemoveHandler ProcessInteger, Function(m As Integer) m

    End Sub
End Module
```

<span data-ttu-id="7591c-110">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-110">By default, this message is a warning.</span></span> <span data-ttu-id="7591c-111">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7591c-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="7591c-112">**오류 ID:** BC42326</span><span class="sxs-lookup"><span data-stu-id="7591c-112">**Error ID:** BC42326</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7591c-113">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7591c-113">To correct this error</span></span>

<span data-ttu-id="7591c-114">경고를 방지 하 고 람다 식을 제거 하려면 다음 예제와 같이 람다 식을 변수에 할당 하 고 및 문에서 변수를 사용 `AddHandler` `RemoveHandler` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7591c-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Dim PrintHandler As ProcessIntegerEventHandler

    Sub Main()

        ' Assign the lambda expression to a variable.
        PrintHandler = Function(m As Integer) m

        ' Use the variable to add the listener.
        AddHandler ProcessInteger, PrintHandler

        ' Use the variable again when you want to remove the listener.
        RemoveHandler ProcessInteger, PrintHandler

    End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="7591c-115">참조</span><span class="sxs-lookup"><span data-stu-id="7591c-115">See also</span></span>

- [<span data-ttu-id="7591c-116">람다 식</span><span class="sxs-lookup"><span data-stu-id="7591c-116">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="7591c-117">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="7591c-117">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="7591c-118">이벤트</span><span class="sxs-lookup"><span data-stu-id="7591c-118">Events</span></span>](../../programming-guide/language-features/events/index.md)

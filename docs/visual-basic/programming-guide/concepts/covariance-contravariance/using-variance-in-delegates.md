---
title: 대리자에서 가변성 사용
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 842392a1342f7d3689d4d1f2a2adb7470eeda05e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375786"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="43770-102">대리자의 가변성 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43770-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="43770-103">메서드를 대리자에 할당하면 *공변성(covariance)* 및 *반공변성(Contravariance)* 은 대리자 형식과 메서드 시그니처의 일치를 확인하는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43770-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="43770-104">공변성(covariance)은 메서드가 대리자에 정의된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="43770-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="43770-105">반공변성(contravariance)은 메서드가 대리자 형식보다 더 적은 수의 파생된 매개 변수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="43770-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="43770-106">예제 1: 공변성(Covariance)</span><span class="sxs-lookup"><span data-stu-id="43770-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="43770-107">설명</span><span class="sxs-lookup"><span data-stu-id="43770-107">Description</span></span>

<span data-ttu-id="43770-108">이 예제에서는 대리자를 대리자 시그니처의 반환 형식에서 파생된 반환 형식이 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43770-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="43770-109">`DogsHandler`에서 반환된 데이터 형식은 `Dogs`이고, 이 형식은 대리자에 정의된 `Mammals` 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="43770-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="43770-110">코드</span><span class="sxs-lookup"><span data-stu-id="43770-110">Code</span></span>

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a><span data-ttu-id="43770-111">예제 2: 반공변성(Contravariance)</span><span class="sxs-lookup"><span data-stu-id="43770-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="43770-112">설명</span><span class="sxs-lookup"><span data-stu-id="43770-112">Description</span></span>

<span data-ttu-id="43770-113">이 예제에서는 대리자를 대리자 시그니처 매개 변수 형식의 기본 형식을 사용하는 매개 변수를 가지고 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43770-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="43770-114">반공변성(contravariance)에서는 별도의 여러 처리기 대신 하나의 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43770-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="43770-115">다음 예제는 두 개의 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43770-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="43770-116">[Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) 이벤트의 시그니처를 정의하는 <xref:System.Windows.Forms.KeyEventHandler> 대리자.</span><span class="sxs-lookup"><span data-stu-id="43770-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="43770-117">해당 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43770-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="43770-118">[Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) 이벤트의 시그니처를 정의하는 <xref:System.Windows.Forms.MouseEventHandler> 대리자.</span><span class="sxs-lookup"><span data-stu-id="43770-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="43770-119">해당 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43770-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="43770-120">예제에서는 <xref:System.EventArgs> 매개 변수를 사용하여 이벤트 처리기를 정의하고 이를 사용하여 `Button.KeyDown` 및 `Button.MouseClick` 이벤트를 모두 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="43770-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="43770-121"><xref:System.EventArgs>는 <xref:System.Windows.Forms.KeyEventArgs> 및 <xref:System.Windows.Forms.MouseEventArgs>의 기본 형식이므로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43770-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="43770-122">코드</span><span class="sxs-lookup"><span data-stu-id="43770-122">Code</span></span>

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a><span data-ttu-id="43770-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43770-123">See also</span></span>

- [<span data-ttu-id="43770-124">대리자의 가변성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43770-124">Variance in Delegates (Visual Basic)</span></span>](variance-in-delegates.md)
- [<span data-ttu-id="43770-125">Func 및 Action 제네릭 대리자에 가변성 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43770-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)

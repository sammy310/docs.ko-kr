---
title: 대리자의 가변성 사용(C#)
description: 포함된 공변성(Covariance) 및 반공변성(Contravariance) 코드 예제를 사용하여 대리자의 가변성을 사용하는 방법을 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 62b0555ee29c5e7d2ba0954a8949d61596122cc7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105680"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="94d3d-103">대리자의 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="94d3d-103">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="94d3d-104">메서드를 대리자에 할당하면 *공변성(covariance)* 및 *반공변성(Contravariance)* 은 대리자 형식과 메서드 시그니처의 일치를 확인하는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-104">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="94d3d-105">공변성(covariance)은 메서드가 대리자에 정의된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-105">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="94d3d-106">반공변성(contravariance)은 메서드가 대리자 형식보다 더 적은 수의 파생된 매개 변수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-106">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="94d3d-107">예제 1: 공변성</span><span class="sxs-lookup"><span data-stu-id="94d3d-107">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="94d3d-108">설명</span><span class="sxs-lookup"><span data-stu-id="94d3d-108">Description</span></span>  
 <span data-ttu-id="94d3d-109">이 예제에서는 대리자를 대리자 시그니처의 반환 형식에서 파생된 반환 형식이 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-109">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="94d3d-110">`DogsHandler`에서 반환된 데이터 형식은 `Dogs`이고, 이 형식은 대리자에 정의된 `Mammals` 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-110">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="94d3d-111">코드</span><span class="sxs-lookup"><span data-stu-id="94d3d-111">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="94d3d-112">예제 2: 반공변성(contravariance)</span><span class="sxs-lookup"><span data-stu-id="94d3d-112">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="94d3d-113">설명</span><span class="sxs-lookup"><span data-stu-id="94d3d-113">Description</span></span>

<span data-ttu-id="94d3d-114">이 예제에서는 대리자를 대리자 시그니처 매개 변수 형식의 기본 형식을 사용하는 매개 변수를 가지고 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-114">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="94d3d-115">반공변성(contravariance)에서는 별도의 여러 처리기 대신 하나의 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-115">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="94d3d-116">다음 예제는 두 개의 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-116">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="94d3d-117">[Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) 이벤트의 시그니처를 정의하는 <xref:System.Windows.Forms.KeyEventHandler> 대리자.</span><span class="sxs-lookup"><span data-stu-id="94d3d-117">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="94d3d-118">해당 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-118">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="94d3d-119">[Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) 이벤트의 시그니처를 정의하는 <xref:System.Windows.Forms.MouseEventHandler> 대리자.</span><span class="sxs-lookup"><span data-stu-id="94d3d-119">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="94d3d-120">해당 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-120">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="94d3d-121">예제에서는 <xref:System.EventArgs> 매개 변수를 사용하여 이벤트 처리기를 정의하고 이를 사용하여 `Button.KeyDown` 및 `Button.MouseClick` 이벤트를 모두 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-121">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="94d3d-122"><xref:System.EventArgs>는 <xref:System.Windows.Forms.KeyEventArgs> 및 <xref:System.Windows.Forms.MouseEventArgs>의 기본 형식이므로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94d3d-122">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="94d3d-123">코드</span><span class="sxs-lookup"><span data-stu-id="94d3d-123">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="94d3d-124">참조</span><span class="sxs-lookup"><span data-stu-id="94d3d-124">See also</span></span>

- [<span data-ttu-id="94d3d-125">대리자의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="94d3d-125">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="94d3d-126">Func 및 Action 제네릭 대리자에 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="94d3d-126">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)

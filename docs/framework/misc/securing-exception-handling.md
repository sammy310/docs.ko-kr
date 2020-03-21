---
title: 예외 처리 보안
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
ms.openlocfilehash: ad27e62197f6fdaa6b5e706f4ae02c03fecae9f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181147"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="443ff-102">예외 처리 보안</span><span class="sxs-lookup"><span data-stu-id="443ff-102">Securing Exception Handling</span></span>
<span data-ttu-id="443ff-103">Visual C++ 및 Visual Basic에서는 **스택을** 더 위로 올라가면 최종 문이 실행되기 전에 필터 식이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="443ff-104">해당 필터와 연결된 **catch** 블록은 **finally** 문 이후에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="443ff-105">자세한 내용은 [사용자 필터링된 예외 사용](../../standard/exceptions/using-user-filtered-exception-handlers.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="443ff-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="443ff-106">이 섹션에서는 이 명령의 보안 영향을 살펴봅습니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="443ff-107">필터 문과 **finally** 문이 실행되는 순서를 보여 주는 다음 의사 코드 예제를 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="443ff-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
```cpp  
void Main()
{  
    try
    {  
        Sub();  
    }
    except (Filter())
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()
{  
    try
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }
    finally
    {  
        Console.WriteLine("finally");  
    }  
}
```  
  
 <span data-ttu-id="443ff-108">이 코드는 다음을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="443ff-109">필터는 **finally** 문 전에 실행되므로 다른 코드의 실행이 활용할 수 있는 상태를 변경하는 모든 문제에서 보안 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="443ff-110">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-110">For example:</span></span>  
  
```cpp  
try
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and
    // so on) that could be exploited if malicious
    // code ran before state is restored.  
    Do_some_work();  
}
finally
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 <span data-ttu-id="443ff-111">이 의사 코드를 사용하면 스택의 상위에서 필터가 임의의 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="443ff-112">비슷한 효과를 낼 수 있는 작업의 다른 예로는 다른 ID의 임시 사칭, 일부 보안 검사를 우회하는 내부 플래그 설정 또는 스레드와 연결된 문화권 변경 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="443ff-113">권장되는 해결 방법은 예외 처리기를 도입하여 코드의 변경 내용을 호출자의 필터 블록에서 스레드 상태로 격리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="443ff-114">그러나 예외 처리기를 제대로 도입하거나 이 문제가 해결되지 않는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="443ff-115">다음 예제에서는 UI 문화를 전환하지만 모든 종류의 스레드 상태 변경도 마찬가지로 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 <span data-ttu-id="443ff-116">이 경우 올바른 수정 은 **try**/**catch** 블록에서 기존 **try**/**finally** 블록을 래핑하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="443ff-117">다음 예제와 같이 기존 **try**/**finally** 블록에 **catch-throw** 절을 도입하기만 하면 문제가 해결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 <span data-ttu-id="443ff-118">**finally** 문이 제어를 `FilterFunc` 받기 전에 실행되지 않았기 때문에 이 문제는 해결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="443ff-119">다음 예제는 **호출자의** 예외 필터 블록에 예외를 제공하기 전에 finally 절이 실행되었는지 확인하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="443ff-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try
    {  
        try
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="443ff-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="443ff-120">See also</span></span>

- [<span data-ttu-id="443ff-121">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="443ff-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)

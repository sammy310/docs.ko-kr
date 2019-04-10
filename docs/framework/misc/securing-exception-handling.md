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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc8cd20a4183ffd002f1399b6b50c8956208a21b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173681"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="01cbb-102">예외 처리 보안</span><span class="sxs-lookup"><span data-stu-id="01cbb-102">Securing Exception Handling</span></span>
<span data-ttu-id="01cbb-103">시각적 개체의 C++ 하기 전에 Visual Basic의 경우 스택에서 추가 필터 식을 실행 **마지막** 문입니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="01cbb-104">**catch** 블록에 연결 된 후 실행 되는 필터는 **마지막으로** 문.</span><span class="sxs-lookup"><span data-stu-id="01cbb-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="01cbb-105">자세한 내용은 [사용자 필터 예외](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="01cbb-106">이 섹션에서는이 주문의 보안 문제를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="01cbb-107">필터 문 순서를 보여 주는 다음 의사 코드 예제 및 **마지막** 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="01cbb-108">이 코드에서는 다음이 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="01cbb-109">필터가 먼저 실행 합니다 **마지막** 되므로 보안 문제가 될 수 있는 다른 코드를 실행 하는 데 이용 변경 상태를 수행 하면 문입니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="01cbb-110">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="01cbb-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="01cbb-111">이 의사 코드 필터를 스택의 상위에 임의의 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="01cbb-112">다른 비슷한 효과 포함 하는 작업의 예로 임시 일부 보안 검사를 우회 하는 내부 플래그를 설정 하는 다른 id 가장 하거나 스레드와 연결 된 문화권을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="01cbb-113">권장 되는 방법은 호출자의 필터 블록에서 스레드 상태를 코드 변경 내용을 격리 하는 예외 처리기를 소개 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="01cbb-114">그러나 예외 처리기의 도입이 제대로 될 중요 한 나이 문제를 해결할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="01cbb-115">다음 예제에서는 UI culture를 전환 하지만 모든 종류의 스레드 상태 변경 마찬가지로 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="01cbb-116">올바른 해결이 경우 기존 래핑할 **시도**/**마지막** 블록에 **시도**/**catch** 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="01cbb-117">간단히 소개를 **catch throw** 기존 절 **시도**/**마지막** 다음 예와에서 같이 블록 문제를 해결 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="01cbb-118">때문에 문제가 해결 되지 않으면이 **마지막** 하기 전에 문이 실행 되지 않은 `FilterFunc` 컨트롤을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="01cbb-119">확인 하 여 문제를 해결 하는 다음 예제에서는 합니다 **마지막** 절이 호출자의 예외 필터 블록에 예외를 제공 하기 전에 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01cbb-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="01cbb-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="01cbb-120">See also</span></span>

- [<span data-ttu-id="01cbb-121">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="01cbb-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)

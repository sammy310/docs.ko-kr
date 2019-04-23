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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173681"
---
# <a name="securing-exception-handling"></a>예외 처리 보안
시각적 개체의 C++ 하기 전에 Visual Basic의 경우 스택에서 추가 필터 식을 실행 **마지막** 문입니다. **catch** 블록에 연결 된 후 실행 되는 필터는 **마지막으로** 문. 자세한 내용은 [사용자 필터 예외](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)합니다. 이 섹션에서는이 주문의 보안 문제를 검사합니다. 필터 문 순서를 보여 주는 다음 의사 코드 예제 및 **마지막** 문을 실행 합니다.  
  
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
  
 이 코드에서는 다음이 출력 합니다.  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 필터가 먼저 실행 합니다 **마지막** 되므로 보안 문제가 될 수 있는 다른 코드를 실행 하는 데 이용 변경 상태를 수행 하면 문입니다. 예를 들어:  
  
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
  
 이 의사 코드 필터를 스택의 상위에 임의의 코드를 실행할 수 있습니다. 다른 비슷한 효과 포함 하는 작업의 예로 임시 일부 보안 검사를 우회 하는 내부 플래그를 설정 하는 다른 id 가장 하거나 스레드와 연결 된 문화권을 변경 합니다. 권장 되는 방법은 호출자의 필터 블록에서 스레드 상태를 코드 변경 내용을 격리 하는 예외 처리기를 소개 하는 것입니다. 그러나 예외 처리기의 도입이 제대로 될 중요 한 나이 문제를 해결할 수는 있습니다. 다음 예제에서는 UI culture를 전환 하지만 모든 종류의 스레드 상태 변경 마찬가지로 노출 될 수 있습니다.  
  
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
  
 올바른 해결이 경우 기존 래핑할 **시도**/**마지막** 블록에 **시도**/**catch** 블록입니다. 간단히 소개를 **catch throw** 기존 절 **시도**/**마지막** 다음 예와에서 같이 블록 문제를 해결 하지 않습니다.  
  
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
  
 때문에 문제가 해결 되지 않으면이 **마지막** 하기 전에 문이 실행 되지 않은 `FilterFunc` 컨트롤을 가져옵니다.  
  
 확인 하 여 문제를 해결 하는 다음 예제에서는 합니다 **마지막** 절이 호출자의 예외 필터 블록에 예외를 제공 하기 전에 실행 됩니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)

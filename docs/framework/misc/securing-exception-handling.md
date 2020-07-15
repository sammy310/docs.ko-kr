---
title: 예외 처리 보안
description: .NET 코드에서 예외 처리를 안전 하 게 만드는 방법을 참조 하세요. Try, except, catch 및 finally 문이 있는 경우 코드가 실행 되는 순서를 검토 합니다.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
ms.openlocfilehash: 73597f83d7236cd48a18a891c987b4f5d7e1723d
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309042"
---
# <a name="securing-exception-handling"></a>예외 처리 보안
Visual C++ 및 Visual Basic에서 스택의 추가 필터 식은 모든 문 보다 먼저 실행 됩니다 `finally` . 해당 필터와 연결 된 **catch** 블록은 문 다음에 실행 됩니다 `finally` . 자세한 내용은 [사용자 필터 예외 사용](../../standard/exceptions/using-user-filtered-exception-handlers.md)을 참조 하세요. 이 섹션에서는이 주문의 보안 의미를 검사 합니다. 필터 문과 문이 실행 되는 순서를 설명 하는 다음 의사 코드 예를 고려해 보세요 `finally` .  
  
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
  
 이 코드는 다음을 출력 합니다.  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 이 필터는 문 보다 먼저 실행 `finally` 되므로 다른 코드를 실행 하는 데 사용 될 수 있는 상태를 변경 하는 모든 항목에 의해 보안 문제가 발생할 수 있습니다. 예를 들면 다음과 같습니다.  
  
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
  
 이 의사 코드는 스택의 상위 필터에서 임의 코드를 실행할 수 있도록 허용 합니다. 유사한 효과가 있는 작업의 다른 예로는 다른 id의 임시 가장, 일부 보안 검사를 우회 하는 내부 플래그 설정 또는 스레드와 연결 된 문화권 변경 등이 있습니다. 권장 되는 해결 방법은 코드의 변경 내용을 호출자의 필터 블록에서 스레드 상태로 격리 하는 예외 처리기를 도입 하는 것입니다. 그러나 예외 처리기를 올바르게 도입 하는 것이 중요 합니다. 그렇지 않으면이 문제가 수정 되지 않습니다. 다음 예제에서는 UI 문화권을 전환 하지만 모든 종류의 스레드 상태 변경이 비슷한 방식으로 노출 될 수 있습니다.  
  
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
  
 이 경우 올바른 픽스는 **try** / **finally** **try** / **catch** 블록에서 기존 try finally 블록을 래핑하는 것입니다. 다음 예제와 같이 **catch throw** 절을 기존 **try** / **finally** 블록에 도입 하면 문제가 해결 되지 않습니다.  
  
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
  
 이는가 `finally` 컨트롤을 가져오기 전에 실행 되지 않았기 때문에 문제가 해결 되지 않습니다 `FilterFunc` .  
  
 다음 예제에서는 `finally` 호출자의 예외 필터 블록에 예외를 제공 하기 전에 절이 실행 되도록 하 여 문제를 해결 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- [보안 코딩 지침](../../standard/security/secure-coding-guidelines.md)

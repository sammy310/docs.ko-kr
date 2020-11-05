---
title: 스레드 제거
description: .NET에서 스레드를 제거해야 하는 경우 협조적 취소 또는 Thread.Abort 메서드 같은 옵션에 대해 알아봅니다. ThreadAbortException을 처리하는 방법을 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: caf7e29742bd7c0481badeeace91b7851520ad12
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188369"
---
# <a name="destroying-threads"></a>스레드 제거

스레드의 실행을 종료하려면 일반적으로 [협조적 취소 모델](cancellation-in-managed-threads.md)을 사용합니다. 경우에 따라 스레드의 협조적 중지가 불가할 수 있는데, 이는 협조적 취소를 위해 설계되지 않은 타사 코드를 실행하기 때문입니다. .NET Framework의 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 메서드를 사용하여 관리되는 스레드를 강제로 종료할 수 있습니다. <xref:System.Threading.Thread.Abort%2A>를 호출할 때 공용 언어 런타임이 대상 스레드에서 <xref:System.Threading.ThreadAbortException>을 throw하며, 대상 스레드가 이를 catch할 수 있습니다. 자세한 내용은 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 참조하세요. <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 메서드는 .NET Core를 포함하여 .Net 5 이상 버전에서 지원되지 않습니다. .NET 5 이상에서 강제로 타사 코드 실행을 종료해야 하는 경우 별도의 프로세스에서 실행하고 <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>을 사용합니다.

> [!NOTE]
> <xref:System.Threading.Thread.Abort%2A> 메서드가 호출될 때 스레드가 비관리 코드를 실행하는 경우 런타임은 이를 <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>로 표시합니다. 스레드가 관리 코드로 돌아오면 예외가 throw됩니다.  
  
 스레드가 중단되면 다시 시작할 수 없습니다.  
  
 대상 스레드가 <xref:System.Threading.ThreadAbortException>를 catch하고 `finally` 블록에서 임의의 코드를 실행할 수 있으므로 <xref:System.Threading.Thread.Abort%2A> 메서드로 인해 스레드가 즉시 중단되지 않습니다. 스레드가 종료될 때까지 기다려야 하는 경우 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>을 호출할 수 있습니다. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>은 스레드가 실제로 실행을 중지했거나 선택적 시간 제한 간격이 경과할 때까지 반환하지 않는 차단 호출입니다. 중단된 스레드는 <xref:System.Threading.Thread.ResetAbort%2A> 메서드를 호출하거나 `finally` 블록에서 제한 없는 처리를 수행할 수 있으므로 제한 시간을 지정하지 않으면 대기가 종료되지 않습니다.  
  
 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> 메서드 호출을 대기 중인 스레드는 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>을 호출하는 다른 스레드에 의해 중단될 수 있습니다.  
  
## <a name="handling-threadabortexception"></a>ThreadAbortException 처리  
 자체 코드에서 <xref:System.Threading.Thread.Abort%2A>를 호출한 결과로 또는 스레드가 실행 중인 애플리케이션 도메인을 언로드한(<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>에서 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 사용하여 스레드 종료) 결과로 스레드가 중단될 것으로 예상되는 경우 스레드에서 <xref:System.Threading.ThreadAbortException>을 처리하고 다음 코드와 같이 `finally` 절에서 최종 처리를 수행해야 합니다.  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try
{  
    // Code that is executing when the thread is aborted.  
}
catch (ThreadAbortException ex)
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.
}  
// Do not put clean-up code here, because the exception
// is rethrown at the end of the Finally clause.  
```  
  
 <xref:System.Threading.ThreadAbortException>이 `finally` 절의 끝에서 또는 `finally` 절이 없는 경우 `catch` 절의 끝에서 시스템을 통해 다시 throw되므로 정리 코드가 `catch` 절 또는 `finally` 절에 있어야 합니다.  
  
 <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> 메서드를 호출하여 시스템이 예외를 다시 throw하지 않도록 할 수 있습니다. 그러나 사용자의 코드가 <xref:System.Threading.ThreadAbortException>을 발생시킨 경우에만 이를 수행해야 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [스레드 및 스레딩 사용](using-threads-and-threading.md)

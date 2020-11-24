---
title: 포그라운드 및 백그라운드 스레드
description: .NET에서 Thread.IsBackground 속성을 사용하여 스레드가 백그라운드 스레드 또는 포그라운드 스레드인지 여부를 확인하거나 변경합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- threading [.NET], foreground
- threading [.NET], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 9f0ea1d53eb2f96b8a56cacc089cf90eb2f079a0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819905"
---
# <a name="foreground-and-background-threads"></a>포그라운드 및 백그라운드 스레드

관리되는 스레드는 백그라운드 스레드 또는 포그라운드 스레드입니다. 백그라운드 스레드는 하나의 예외가 있는 포그라운드 스레드와 동일합니다. 백그라운드 스레드는 관리되는 실행 환경을 계속 실행하지 않습니다. 모든 포그라운드 스레드가 관리되는 프로세스(.exe 파일이 관리되는 어셈블리인 프로세스)에서 중지되면 시스템이 모든 백그라운드 스레드를 중지하고 종료됩니다.  
  
> [!NOTE]
> 프로세스가 종료되고 있기 때문에 런타임이 백그라운드 스레드를 중지하면 스레드에서 예외가 throw되지 않습니다. 그러나 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 메서드가 애플리케이션 도메인을 언로드하기 때문에 스레드가 중지되면 포그라운드 및 백그라운드 스레드 모두에서 <xref:System.Threading.ThreadAbortException>이 throw됩니다.  
  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> 속성을 사용하여 스레드가 백그라운드 또는 포그라운드 스레드인지 확인하거나 해당 상태를 변경합니다. 언제든지 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정하여 스레드를 백그라운드 스레드로 변경할 수 있습니다.  
  
> [!IMPORTANT]
> 스레드의 포그라운드 또는 백그라운드 상태는 스레드에서 처리되지 않은 예외의 결과에 영향을 주지 않습니다. 포그라운드 또는 백그라운드 스레드에서 처리되지 않은 예외로 인해 애플리케이션이 종료됩니다. [관리되는 스레드의 예외](exceptions-in-managed-threads.md)를 참조하세요.  
  
 관리되는 스레드 풀(<xref:System.Threading.Thread.IsThreadPoolThread%2A> 속성이 `true`인 스레드)에 속하는 스레드는 백그라운드 스레드입니다. 비관리 코드에서 관리되는 실행 환경에 들어가는 모든 스레드는 백그라운드 스레드로 표시됩니다. 새 <xref:System.Threading.Thread> 개체를 만들고 시작하여 생성된 모든 스레드는 기본적으로 포그라운드 스레드입니다.  
  
 스레드를 사용하여 소켓 연결과 같은 활동을 모니터링하는 경우 스레드가 프로세스 종료를 차단하지 않도록 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>

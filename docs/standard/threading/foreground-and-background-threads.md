---
title: 포그라운드 및 백그라운드 스레드
description: .NET에서 Thread.IsBackground 속성을 사용하여 스레드가 백그라운드 스레드 또는 포그라운드 스레드인지 여부를 확인하거나 변경합니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 6cb7a92851728e16f4a317d6c24d072acee72a94
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769043"
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="02343-103">포그라운드 및 백그라운드 스레드</span><span class="sxs-lookup"><span data-stu-id="02343-103">Foreground and Background Threads</span></span>
<span data-ttu-id="02343-104">관리되는 스레드는 백그라운드 스레드 또는 포그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="02343-104">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="02343-105">백그라운드 스레드는 하나의 예외가 있는 포그라운드 스레드와 동일합니다. 백그라운드 스레드는 관리되는 실행 환경을 계속 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02343-105">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="02343-106">모든 포그라운드 스레드가 관리되는 프로세스(.exe 파일이 관리되는 어셈블리인 프로세스)에서 중지되면 시스템이 모든 백그라운드 스레드를 중지하고 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="02343-106">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02343-107">프로세스가 종료되고 있기 때문에 런타임이 백그라운드 스레드를 중지하면 스레드에서 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02343-107">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="02343-108">그러나 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 메서드가 애플리케이션 도메인을 언로드하기 때문에 스레드가 중지되면 포그라운드 및 백그라운드 스레드 모두에서 <xref:System.Threading.ThreadAbortException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="02343-108">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="02343-109"><xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> 속성을 사용하여 스레드가 백그라운드 또는 포그라운드 스레드인지 확인하거나 해당 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="02343-109">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="02343-110">언제든지 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정하여 스레드를 백그라운드 스레드로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02343-110">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="02343-111">스레드의 포그라운드 또는 백그라운드 상태는 스레드에서 처리되지 않은 예외의 결과에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02343-111">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="02343-112">.NET Framework 버전 2.0에서는 포그라운드 또는 백그라운드 스레드에서 처리되지 않은 예외로 인해 애플리케이션이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="02343-112">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="02343-113">[관리되는 스레드의 예외](exceptions-in-managed-threads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02343-113">See [Exceptions in Managed Threads](exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="02343-114">관리되는 스레드 풀(<xref:System.Threading.Thread.IsThreadPoolThread%2A> 속성이 `true`인 스레드)에 속하는 스레드는 백그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="02343-114">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="02343-115">비관리 코드에서 관리되는 실행 환경에 들어가는 모든 스레드는 백그라운드 스레드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="02343-115">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="02343-116">새 <xref:System.Threading.Thread> 개체를 만들고 시작하여 생성된 모든 스레드는 기본적으로 포그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="02343-116">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="02343-117">스레드를 사용하여 소켓 연결과 같은 활동을 모니터링하는 경우 스레드가 프로세스 종료를 차단하지 않도록 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02343-117">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02343-118">참조</span><span class="sxs-lookup"><span data-stu-id="02343-118">See also</span></span>

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>

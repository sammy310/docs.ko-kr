---
title: 관리되는 스레드의 예외
description: .NET에서 처리되지 않은 예외를 처리하는 방법을 참조하세요. 대부분의 처리되지 않은 스레드 예외는 정상적으로 진행되며 애플리케이션 종료로 이어집니다.
ms.date: 03/30/2017
helpviewer_keywords:
- unhandled exceptions,in managed threads
- threading [.NET],unhandled exceptions
- threading [.NET],exceptions in managed threads
- managed threading
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
ms.openlocfilehash: 740cd1b78b96c2fcaecf39a725973d738037f403
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723755"
---
# <a name="exceptions-in-managed-threads"></a><span data-ttu-id="1cdd9-104">관리형 스레드의 예외</span><span class="sxs-lookup"><span data-stu-id="1cdd9-104">Exceptions in managed threads</span></span>

<span data-ttu-id="1cdd9-105">공용 언어 런타임을 통해 스레드에 있는 대부분의 처리되지 않은 예외가 정상적으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-105">The common language runtime allows most unhandled exceptions in threads to proceed naturally.</span></span> <span data-ttu-id="1cdd9-106">즉, 대부분의 경우에서 처리되지 않은 예외는 애플리케이션을 종료시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-106">In most cases this means that the unhandled exception causes the application to terminate.</span></span>
  
<span data-ttu-id="1cdd9-107">공용 언어 런타임은 프로그램 흐름을 제어하는 데 사용되는 처리되지 않은 예외에 백업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-107">The common language runtime provides a backstop for certain unhandled exceptions that are used for controlling program flow:</span></span>  
  
- <span data-ttu-id="1cdd9-108"><xref:System.Threading.Thread.Abort%2A>가 호출되었으므로 스레드에서 <xref:System.Threading.ThreadAbortException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-108">A <xref:System.Threading.ThreadAbortException> is thrown in a thread because <xref:System.Threading.Thread.Abort%2A> was called.</span></span>  
  
- <span data-ttu-id="1cdd9-109">스레드가 실행 중인 애플리케이션 도메인이 언로드되는 중이므로 스레드에서 <xref:System.AppDomainUnloadedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-109">An <xref:System.AppDomainUnloadedException> is thrown in a thread because the application domain in which the thread is executing is being unloaded.</span></span>  
  
- <span data-ttu-id="1cdd9-110">공용 언어 런타임 또는 호스트 프로세스에서 내부 예외를 throw하여 스레드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-110">The common language runtime or a host process terminates the thread by throwing an internal exception.</span></span>  
  
 <span data-ttu-id="1cdd9-111">이러한 예외가 공용 언어 런타임에서 만든 스레드에서 처리되지 않는 경우 해당 예외는 스레드를 종료시키지만, 공용 언어 런타임에서 해당 예외가 계속 진행되도록 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-111">If any of these exceptions are unhandled in threads created by the common language runtime, the exception terminates the thread, but the common language runtime does not allow the exception to proceed further.</span></span>  
  
 <span data-ttu-id="1cdd9-112">이러한 예외가 주 스레드나 비관리 코드에서 런타임으로 들어간 스레드에서 처리되지 않는 경우 해당 예외는 정상적으로 진행되고 애플리케이션이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-112">If these exceptions are unhandled in the main thread, or in threads that entered the runtime from unmanaged code, they proceed normally, resulting in termination of the application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cdd9-113">관리 코드가 예외 처리기를 설치하기 전에 런타임은 처리되지 않은 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-113">It is possible for the runtime to throw an unhandled exception before any managed code has had a chance to install an exception handler.</span></span> <span data-ttu-id="1cdd9-114">관리 코드가 이러한 예외를 처리하지 못하더라도 예외는 정상적으로 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-114">Even though managed code had no chance to handle such an exception, the exception is allowed to proceed naturally.</span></span>  
  
## <a name="exposing-threading-problems-during-development"></a><span data-ttu-id="1cdd9-115">개발하는 동안 스레딩 문제 노출</span><span class="sxs-lookup"><span data-stu-id="1cdd9-115">Exposing Threading Problems During Development</span></span>  

 <span data-ttu-id="1cdd9-116">애플리케이션이 종료되지 않고 스레드에 오류가 발생할 수 있는 경우 심각한 프로그래밍 문제를 발견하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-116">When threads are allowed to fail silently, without terminating the application, serious programming problems can go undetected.</span></span> <span data-ttu-id="1cdd9-117">이것은 확장된 기간 동안 실행되는 서비스와 기타 애플리케이션에 특정된 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-117">This is a particular problem for services and other applications that run for extended periods.</span></span> <span data-ttu-id="1cdd9-118">스레드에 오류가 발생하면 프로그램 상태가 서서히 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-118">As threads fail, program state gradually becomes corrupted.</span></span> <span data-ttu-id="1cdd9-119">애플리케이션 성능이 저하되거나 애플리케이션이 응답하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-119">Application performance may degrade, or the application might become unresponsive.</span></span>  
  
 <span data-ttu-id="1cdd9-120">운영 체제가 응용 프로그램을 종료시킬 때까지 스레드의 처리되지 않은 예외가 정상적으로 진행되도록 허용하면 개발이나 테스트하는 동안 이러한 문제에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-120">Allowing unhandled exceptions in threads to proceed naturally, until the operating system terminates the program, exposes such problems during development and testing.</span></span> <span data-ttu-id="1cdd9-121">프로그램 종료에 대한 오류 보고서는 디버깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-121">Error reports on program terminations support debugging.</span></span>  
  
## <a name="change-from-previous-versions"></a><span data-ttu-id="1cdd9-122">이전 버전의 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1cdd9-122">Change from previous versions</span></span>

<span data-ttu-id="1cdd9-123">.NET Framework 버전 1.0 및 1.1에서는 공용 언어 런타임이 다음과 같은 상황에서 처리되지 않은 예외에 백업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-123">In .NET Framework versions 1.0 and 1.1, the common language runtime provides a backstop for unhandled exceptions in the following situations:</span></span>  
  
- <span data-ttu-id="1cdd9-124">스레드 풀 스레드에 처리되지 않은 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-124">There is no such thing as an unhandled exception on a thread pool thread.</span></span> <span data-ttu-id="1cdd9-125">작업이 처리하지 않는 예외를 throw하는 경우 런타임은 해당 예외의 스택 추적을 콘솔에 출력한 다음 해당 스레드를 스레드 풀에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-125">When a task throws an exception that it does not handle, the runtime prints the exception stack trace to the console and then returns the thread to the thread pool.</span></span>  
  
- <span data-ttu-id="1cdd9-126"><xref:System.Threading.Thread> 클래스의 <xref:System.Threading.Thread.Start%2A> 메서드를 사용하여 만들어진 스레드에는 처리되지 않은 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-126">There is no such thing as an unhandled exception on a thread created with the <xref:System.Threading.Thread.Start%2A> method of the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="1cdd9-127">해당 스레드에서 실행되는 코드가 처리하지 않는 예외를 throw하는 경우 런타임은 해당 예외의 스택 추적을 콘솔에 출력한 다음 해당 스레드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-127">When code running on such a thread throws an exception that it does not handle, the runtime prints the exception stack trace to the console and then gracefully terminates the thread.</span></span>  
  
- <span data-ttu-id="1cdd9-128">종료자 스레드에 처리되지 않은 예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-128">There is no such thing as an unhandled exception on the finalizer thread.</span></span> <span data-ttu-id="1cdd9-129">종료자가 처리하지 않는 예외를 throw하는 경우 런타임은 해당 예외의 스택 추적을 콘솔에 출력한 다음 해당 종료자 스레드가 종료자 실행을 다시 시작하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-129">When a finalizer throws an exception that it does not handle, the runtime prints the exception stack trace to the console and then allows the finalizer thread to resume running finalizers.</span></span>  
  
 <span data-ttu-id="1cdd9-130">관리되는 스레드의 포그라운드 또는 백그라운드 상태가 이 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-130">The foreground or background status of a managed thread does not affect this behavior.</span></span>  
  
 <span data-ttu-id="1cdd9-131">비관리 코드에서 발생되는 스레드의 처리되지 않은 예외의 경우 이 차이점은 더 미묘합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-131">For unhandled exceptions on threads originating in unmanaged code, the difference is more subtle.</span></span> <span data-ttu-id="1cdd9-132">네이티브 코드를 통해 전달된 스레드의 관리되는 예외 또는 네이티브 예외에 대해 런타임 JIT 연결 대화 상자가 운영 체제 대화 상자를 선점합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-132">The runtime JIT-attach dialog preempts the operating system dialog for managed exceptions or native exceptions on threads that have passed through native code.</span></span> <span data-ttu-id="1cdd9-133">모든 경우에 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-133">The process terminates in all cases.</span></span>

### <a name="migration"></a><span data-ttu-id="1cdd9-134">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1cdd9-134">Migration</span></span>

<span data-ttu-id="1cdd9-135">.NET Framework 1.0 또는 1.1에서 마이그레이션 중이고 스레드 종료 등을 위해 런타임 백업을 활용하는 경우 다음 마이그레이션 전략 중 하나를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-135">If you are migrating from .NET Framework 1.0 or 1.1 and took advantage of the runtime backstop, for example to terminate threads, consider one of the following migration strategies:</span></span>  
  
- <span data-ttu-id="1cdd9-136">코드를 재구성하여 신호를 받으면 스레드가 정상적으로 종료되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-136">Restructure the code so the thread exits gracefully when a signal is received.</span></span>  
  
- <span data-ttu-id="1cdd9-137"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 메서드를 사용하여 스레드를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-137">Use the <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method to abort the thread.</span></span>  
  
- <span data-ttu-id="1cdd9-138">프로세스 종료가 진행될 수 있도록 스레드가 중단되어야 하는 경우 해당 스레드를 백그라운드 스레드로 만들어 프로세스가 종료되면 자동으로 종료되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-138">If a thread must be stopped so that process termination can proceed, make the thread a background thread so that it is automatically terminated on process exit.</span></span>  
  
<span data-ttu-id="1cdd9-139">모든 경우에서 전략은 예외에 대한 다음 디자인 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-139">In all cases, the strategy should follow the design guidelines for exceptions.</span></span> <span data-ttu-id="1cdd9-140">[예외 디자인 지침](../design-guidelines/exceptions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-140">See [Design Guidelines for Exceptions](../design-guidelines/exceptions.md).</span></span>  
  
<span data-ttu-id="1cdd9-141">임시 호환을 위해 관리자는 애플리케이션 구성 파일의 `<runtime>` 섹션에 호환 플래그를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-141">As a temporary compatibility measure, administrators can place a compatibility flag in the `<runtime>` section of the application configuration file.</span></span> <span data-ttu-id="1cdd9-142">이렇게 하면 공용 언어 런타임이 버전 1.0 및 1.1의 동작으로 다시 돌아옵니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-142">This causes the common language runtime to revert to the behavior of versions 1.0 and 1.1.</span></span>  
  
```xml  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## <a name="host-override"></a><span data-ttu-id="1cdd9-143">호스트 재정의</span><span class="sxs-lookup"><span data-stu-id="1cdd9-143">Host Override</span></span>

<span data-ttu-id="1cdd9-144">관리되지 않는 호스트가 호스팅 API의 [ICLRPolicyManager](../../framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) 인터페이스를 사용하여 공용 언어 런타임의 기본 처리되지 않은 예외 정책을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-144">An unmanaged host can use the [ICLRPolicyManager](../../framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface in the Hosting API to override the default unhandled exception policy of the common language runtime.</span></span> <span data-ttu-id="1cdd9-145">[ICLRPolicyManager::SetUnhandledExceptionPolicy](../../framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md) 함수를 사용하여 처리되지 않은 예외에 대한 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1cdd9-145">The [ICLRPolicyManager::SetUnhandledExceptionPolicy](../../framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md) function is used to set the policy for unhandled exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cdd9-146">참조</span><span class="sxs-lookup"><span data-stu-id="1cdd9-146">See also</span></span>

- [<span data-ttu-id="1cdd9-147">관리되는 스레딩 기본 사항</span><span class="sxs-lookup"><span data-stu-id="1cdd9-147">Managed Threading Basics</span></span>](managed-threading-basics.md)

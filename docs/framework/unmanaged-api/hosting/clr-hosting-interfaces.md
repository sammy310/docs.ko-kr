---
title: CLR 호스팅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 77f2ba64d9bdbe9793d56e88dae46fd506119ab8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719049"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="a1d12-102">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-102">CLR Hosting Interfaces</span></span>

<span data-ttu-id="a1d12-103">이 섹션에서는 관리 되지 않는 호스트가 CLR (공용 언어 런타임)을 응용 프로그램에 통합 하는 데 사용할 수 있는 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="a1d12-104">이 정보는 .NET Framework 버전 2.0 이상 버전과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="a1d12-105">이러한 인터페이스를 통해 호스트는 버전 1.0 및 1.1에서 제공 되는 것 보다 많은 버전의 런타임을 제어할 수 있으며 CLR과 호스트의 실행 모델 간에 훨씬 긴밀 한 통합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="a1d12-106">.NET Framework 버전 1.0 및 1.1에서 호스팅 모델은 관리 되지 않는 호스트에서 CLR을 프로세스로 로드 하 여 특정 설정을 구성 하 고 이벤트 알림을 수신 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="a1d12-107">그러나 일반적으로 호스트와 CLR은 해당 프로세스에서 독립적으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="a1d12-108">.NET Framework 버전 2.0 이상 버전에서는 새 추상화 계층이 호스트에서 Win32 어셈블리의 형식으로 현재 제공 된 많은 리소스를 제공 하 고 호스트가 구성할 수 있는 기능 집합을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1d12-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a1d12-109">In This Section</span></span>  

 [<span data-ttu-id="a1d12-110">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-110">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)  
 <span data-ttu-id="a1d12-111">등록 된 이벤트에 대해 콜백을 수행 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="a1d12-112">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-112">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)  
 <span data-ttu-id="a1d12-113">아파트 내에서 콜백을 만드는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="a1d12-114">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-114">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)  
 <span data-ttu-id="a1d12-115">런타임 구성을 설정 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="a1d12-116">ICatalogServices 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-116">ICatalogServices Interface</span></span>](icatalogservices-interface.md)  
 <span data-ttu-id="a1d12-117">카탈로그 서비스에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="a1d12-118">이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="a1d12-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="a1d12-119">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="a1d12-120">어셈블리에 대 한 호스트와 CLR 간의 통신을 지 원하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="a1d12-121">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="a1d12-122">호스트가 아닌 CLR에서 로드 하는 어셈블리 목록을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="a1d12-123">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)  
 <span data-ttu-id="a1d12-124">호스트에서 CLR의 다양 한 측면에 대 한 액세스를 얻고 구성 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="a1d12-125">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)  
 <span data-ttu-id="a1d12-126">호스트에서 작업 집합을 식별자와 이름에 연결할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="a1d12-127">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-127">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="a1d12-128">호스트에서 오류 보고를 위해 사용자 지정 힙 덤프를 구성할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="a1d12-129">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-129">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)  
 <span data-ttu-id="a1d12-130">호스트가 CLR의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="a1d12-131">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-131">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="a1d12-132">호스트에서 어셈블리의 정책 정보에 대 한 변경 내용을 평가 하 고 전달 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="a1d12-133">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-133">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="a1d12-134">호스트에서 특정 관리 되는 클래스, 메서드, 속성 및 필드가 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="a1d12-135">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-135">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)  
 <span data-ttu-id="a1d12-136">호스트에서 지정 된 i/o 요청의 상태를 CLR에 알릴 수 있도록 하는 콜백 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="a1d12-137">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="a1d12-138">호스트에서 Win32 함수와 유사한 방법을 사용 하 여 메모리 압력 상태를 보고할 수 있도록 합니다 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="a1d12-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="a1d12-139">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-139">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)  
 <span data-ttu-id="a1d12-140">호스트가 CLR 이벤트의 콜백을 등록 하 고 등록 취소할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="a1d12-141">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)  
 <span data-ttu-id="a1d12-142">호스트에서 오류 및 시간 제한이 발생 하는 경우 수행할 정책 작업을 지정할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="a1d12-143">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="a1d12-144">호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR의 내부에 있는 어셈블리의 id 정보를 사용 하 여 어셈블리의 검색 id를 가져올 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="a1d12-145">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-145">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="a1d12-146">호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR 내부의 어셈블리 id 데이터를 사용 하 여 파일이 나 스트림이 참조 하는 어셈블리 집합을 조작할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="a1d12-147">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-147">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)  
 <span data-ttu-id="a1d12-148">호스트 컨트롤 인터페이스를 설정 하는 추가 메서드를 사용 하 여 [ICorRuntimeHost](icorruntimehost-interface.md)와 유사한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-148">Provides capabilities similar to [ICorRuntimeHost](icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="a1d12-149">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-149">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)  
 <span data-ttu-id="a1d12-150">호스트에서 요청 된 작업에 대 한 정보를 가져오고 해당 동기화 구현에서 교착 상태를 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="a1d12-151">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-151">ICLRTask Interface</span></span>](iclrtask-interface.md)  
 <span data-ttu-id="a1d12-152">호스트가 CLR의 요청을 하거나 연결 된 작업에 대 한 알림을 CLR에 제공할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="a1d12-153">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-153">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)  
 <span data-ttu-id="a1d12-154">호스트가 새 작업을 만들고, 현재 실행 중인 작업을 가져오고, 작업의 지리적 언어와 문화권을 설정 하는 작업을 명시적으로 요청 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="a1d12-155">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-155">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)  
 <span data-ttu-id="a1d12-156">PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="a1d12-157">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-157">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)  
 <span data-ttu-id="a1d12-158">CLR을 구성 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="a1d12-159">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-159">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)  
 <span data-ttu-id="a1d12-160">스레드 풀에 액세스 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="a1d12-161">IDebuggerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-161">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)  
 <span data-ttu-id="a1d12-162">디버깅 서비스의 상태에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="a1d12-163">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-163">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="a1d12-164">디버깅 서비스에서 스레드의 차단 및 차단 해제에 대해 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="a1d12-165">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-165">IGCHost Interface</span></span>](igchost-interface.md)  
 <span data-ttu-id="a1d12-166">가비지 컬렉션 시스템에 대 한 정보를 가져오고 가비지 수집의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="a1d12-167">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-167">IGCHost2 Interface</span></span>](igchost2-interface.md)  
 <span data-ttu-id="a1d12-168">[SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) 메서드를 제공 합니다 .이 메서드를 사용 하면 호스트에서 가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 크기를 0 보다 큰 값으로 설정할 수 있습니다 `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="a1d12-168">Provides the [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="a1d12-169">IGCHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-169">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)  
 <span data-ttu-id="a1d12-170">가비지 수집기에서 호스트에 가상 메모리의 제한을 변경 하도록 요청할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="a1d12-171">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-171">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)  
 <span data-ttu-id="a1d12-172">가비지 수집에 대해 차단 될 스레드 예약에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="a1d12-173">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-173">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)  
 <span data-ttu-id="a1d12-174">호스트가 CLR 또는 호스트에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="a1d12-175">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-175">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)  
 <span data-ttu-id="a1d12-176">호스트가 CLR과는 독립적으로 어셈블리 및 모듈을 로드할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="a1d12-177">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-177">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)  
 <span data-ttu-id="a1d12-178">호스트에서 구현 하는 자동 다시 설정 이벤트의 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="a1d12-179">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-179">IHostControl Interface</span></span>](ihostcontrol-interface.md)  
 <span data-ttu-id="a1d12-180">어셈블리 로드를 구성 하 고 호스트가 지 원하는 호스팅 인터페이스를 결정 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="a1d12-181">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-181">IHostCrst Interface</span></span>](ihostcrst-interface.md)  
 <span data-ttu-id="a1d12-182">스레딩에 대 한 중요 한 섹션의 호스트 표현으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="a1d12-183">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-183">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)  
 <span data-ttu-id="a1d12-184">CLR에서 구현 하는 가비지 수집 메커니즘에서 이벤트의 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="a1d12-185">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-185">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="a1d12-186">CLR이 호스트에서 제공 하는 i/o 완료 포트와 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="a1d12-187">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-187">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)  
 <span data-ttu-id="a1d12-188">호스트를 통해 힙에서 세분화 된 할당을 요청 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="a1d12-189">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-189">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)  
 <span data-ttu-id="a1d12-190">수동 다시 설정 이벤트 표현의 호스트 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="a1d12-191">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-191">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)  
 <span data-ttu-id="a1d12-192">표준 Win32 가상 메모리 함수를 사용 하는 대신 호스트를 통해 가상 메모리 요청을 만드는 CLR에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="a1d12-193">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-193">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)  
 <span data-ttu-id="a1d12-194">중단, 시간 초과 또는 오류가 발생 하는 경우 CLR에서 수행 하는 작업을 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="a1d12-195">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-195">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)  
 <span data-ttu-id="a1d12-196">CLR에서 호스트에 의해 구현 된 보안 컨텍스트 정보를 유지 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="a1d12-197">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-197">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)  
 <span data-ttu-id="a1d12-198">현재 실행 중인 스레드의 보안 컨텍스트에 대 한 액세스 및 제어를 허용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="a1d12-199">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-199">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)  
 <span data-ttu-id="a1d12-200">호스트에서 구현 하는 세마포 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="a1d12-201">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-201">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="a1d12-202">CLR에서 Win32 동기화 함수를 사용 하는 대신 호스트를 호출 하 여 동기화 기본 형식을 만드는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="a1d12-203">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-203">IHostTask Interface</span></span>](ihosttask-interface.md)  
 <span data-ttu-id="a1d12-204">CLR이 호스트와 통신 하 여 작업을 관리할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="a1d12-205">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-205">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)  
 <span data-ttu-id="a1d12-206">CLR이 표준 운영 체제 스레딩 또는 파이버 함수를 사용 하는 대신 호스트를 통해 작업을 수행할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="a1d12-207">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-207">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="a1d12-208">CLR이 스레드 풀을 구성 하 고 작업 항목을 스레드 풀에 대기 시킬 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="a1d12-209">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-209">IManagedObject Interface</span></span>](imanagedobject-interface.md)  
 <span data-ttu-id="a1d12-210">관리 되는 개체를 제어 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="a1d12-211">IObjectHandle</span><span class="sxs-lookup"><span data-stu-id="a1d12-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="a1d12-212">간접 참조에서 값으로 마샬링하는 개체를 래핑 해제 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="a1d12-213">ITypeName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-213">ITypeName Interface</span></span>](itypename-interface.md)  
 <span data-ttu-id="a1d12-214">형식 이름 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="a1d12-215">이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="a1d12-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="a1d12-216">ITypeNameBuilder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-216">ITypeNameBuilder Interface</span></span>](itypenamebuilder-interface.md)  
 <span data-ttu-id="a1d12-217">형식 이름을 빌드하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-217">Provides methods for building a type name.</span></span> <span data-ttu-id="a1d12-218">이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="a1d12-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="a1d12-219">ITypeNameFactory 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-219">ITypeNameFactory Interface</span></span>](itypenamefactory-interface.md)  
 <span data-ttu-id="a1d12-220">형식 이름을 분해 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="a1d12-221">이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="a1d12-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="a1d12-222">IValidator</span><span class="sxs-lookup"><span data-stu-id="a1d12-222">"IValidator"</span></span>  
 <span data-ttu-id="a1d12-223">PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a1d12-224">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a1d12-224">Related Sections</span></span>  

 [<span data-ttu-id="a1d12-225">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="a1d12-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="a1d12-226">.NET Framework 버전 1.0 및 1.1에 제공 된 호스팅 인터페이스를 설명 하는 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="a1d12-227">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d12-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="a1d12-228">.NET Framework 4에서 제공 하는 호스팅 인터페이스를 설명 하는 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d12-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>

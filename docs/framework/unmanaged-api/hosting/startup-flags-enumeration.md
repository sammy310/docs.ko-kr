---
title: STARTUP_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
ms.openlocfilehash: 3c3f4d644bd7073655d2d77fe7f65a3a46cfea24
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729909"
---
# <a name="startup_flags-enumeration"></a><span data-ttu-id="6d506-102">STARTUP_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="6d506-102">STARTUP_FLAGS Enumeration</span></span>

<span data-ttu-id="6d506-103">CLR (공용 언어 런타임)의 시작 동작을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="6d506-104">기본적으로 가비지 수집은 비 동시 이며 기본 클래스 라이브러리만 도메인 중립적 영역에 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d506-105">구문</span><span class="sxs-lookup"><span data-stu-id="6d506-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6d506-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6d506-106">Members</span></span>  
  
|<span data-ttu-id="6d506-107">멤버</span><span class="sxs-lookup"><span data-stu-id="6d506-107">Member</span></span>|<span data-ttu-id="6d506-108">설명</span><span class="sxs-lookup"><span data-stu-id="6d506-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="6d506-109">동시 가비지 수집을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="6d506-110">호출자가 단일 프로세서 컴퓨터에서 서버 빌드 및 동시 가비지 수집을 요청 하면 워크스테이션 빌드 및 비 동시 가비지 수집이 대신 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="6d506-111">**참고:**  Intel Itanium 아키텍처 (이전의 IA-64)를 구현 하는 64 비트 시스템에서 WOW64 x86 에뮬레이터를 실행 하는 응용 프로그램에서는 동시 가비지 수집이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="6d506-112">64 비트 Windows 시스템에서 WOW64를 사용 하는 방법에 대 한 자세한 내용은 [32 비트 응용 프로그램 실행](/windows/desktop/WinProg64/running-32-bit-applications)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d506-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="6d506-113">로더 최적화를 수행 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="6d506-114">어셈블리를 도메인 중립적으로 로드 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="6d506-115">모든 어셈블리를 도메인 중립적으로 로드 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="6d506-116">모든 강력한 이름의 어셈블리를 도메인 중립적으로 로드 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="6d506-117">전달 된 버전에 CLR 버전 정책이 적용 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="6d506-118">CLR에 지정 된 정확한 버전이 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="6d506-119">Shim은 정책을 평가 하 여 호환 되는 최신 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="6d506-120">기본 런타임을 설정 하지만 실제로 시작 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="6d506-121">서버 가비지 수집을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="6d506-122">가비지 수집에서 사용 되는 가상 주소를 유지 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="6d506-123">호스팅 인터페이스를 혼합 하 여 사용할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="6d506-124">기본적으로 가장이 비동기 요소 간에 이동 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="6d506-125">스레드의 실행이 시작 될 때 전체 스레드 스택을 커밋하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="6d506-126">플랫폼 호출을 통해 달성 된 관리 되는 가장 및 가장가 비동기 요소를 통해 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="6d506-127">기본적으로 관리 되는 가장는 비동기 요소를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="6d506-128">시스템 메모리가 부족할 때 가비지 수집에서 커밋된 공간을 적게 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="6d506-129">`gcTrimCommitOnLowMemory` [공유 웹 호스팅을 위한 최적화](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md)에서을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d506-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="6d506-130">공용 언어 런타임 이벤트에 대해 ETW (Windows 용 이벤트 추적)를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="6d506-131">Windows Vista 부터는 이벤트 추적이 항상 사용 되도록 설정 되므로이 플래그는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="6d506-132">[.NET Framework 로깅 제어](../../performance/controlling-logging.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d506-132">See [Controlling .NET Framework Logging](../../performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="6d506-133">응용 프로그램 도메인 리소스 모니터링을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d506-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="6d506-134"><xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>속성 및 [ \<appDomainResourceMonitoring> 요소](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d506-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d506-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d506-135">Requirements</span></span>  

 <span data-ttu-id="6d506-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d506-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d506-137">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6d506-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d506-138">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d506-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d506-139">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d506-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d506-140">참조</span><span class="sxs-lookup"><span data-stu-id="6d506-140">See also</span></span>

- [<span data-ttu-id="6d506-141">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="6d506-141">Hosting Enumerations</span></span>](hosting-enumerations.md)

---
description: '다음에 대 한 자세한 정보: <runtime> 요소'
title: <runtime> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime
helpviewer_keywords:
- <runtime> element
- runtime element
- container tags, <runtime> element
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
ms.openlocfilehash: eeffc8de4eeb6fb53ef3829b8c5b078be4cee83a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652772"
---
# <a name="runtime-element"></a><span data-ttu-id="8d9a6-103">\<runtime> 요소</span><span class="sxs-lookup"><span data-stu-id="8d9a6-103">\<runtime> Element</span></span>

<span data-ttu-id="8d9a6-104">공용 언어 런타임에서 응용 프로그램을 구성 하는 데 사용 되는 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-104">Provides information used by the common language runtime to configure applications.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<runtime>

## <a name="syntax"></a><span data-ttu-id="8d9a6-105">구문</span><span class="sxs-lookup"><span data-stu-id="8d9a6-105">Syntax</span></span>

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d9a6-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8d9a6-106">Attributes and Elements</span></span>

<span data-ttu-id="8d9a6-107">다음 섹션에서는 자식 요소 및 부모 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-107">The following sections describe child elements and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d9a6-108">특성</span><span class="sxs-lookup"><span data-stu-id="8d9a6-108">Attributes</span></span>

<span data-ttu-id="8d9a6-109">없음</span><span class="sxs-lookup"><span data-stu-id="8d9a6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d9a6-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8d9a6-110">Child Elements</span></span>

|<span data-ttu-id="8d9a6-111">요소</span><span class="sxs-lookup"><span data-stu-id="8d9a6-111">Element</span></span>|<span data-ttu-id="8d9a6-112">설명</span><span class="sxs-lookup"><span data-stu-id="8d9a6-112">Description</span></span>|
|-------------|-----------------|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|<span data-ttu-id="8d9a6-113">가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-113">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|<span data-ttu-id="8d9a6-114"><xref:System.AppContext> 클래스에 사용되는 스위치를 하나 이상 정의하여 새 기능의 옵트아웃 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-114">Defines one or more switches used by the <xref:System.AppContext> class to provide an opt-out mechanism for new functionality.</span></span>|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|<span data-ttu-id="8d9a6-115">프로세스의 기본 애플리케이션 도메인용 애플리케이션 도메인 관리자를 제공하는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-115">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|<span data-ttu-id="8d9a6-116">기본 애플리케이션 도메인용 애플리케이션 도메인 관리자로 사용되는 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-116">Specifies the type that serves as the application domain manager for the default application domain.</span></span>|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|<span data-ttu-id="8d9a6-117">프로세스의 수명 동안 프로세스의 모든 애플리케이션 도메인에서 통계를 수집하도록 런타임에 명령합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-117">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|<span data-ttu-id="8d9a6-118">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|<span data-ttu-id="8d9a6-119">신뢰할 수 있는 어셈블리에 대한 강력한 이름 확인을 바이패스할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-119">Specifies whether strong name verification for trusted assemblies should be bypassed.</span></span>|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|<span data-ttu-id="8d9a6-120">런타임에 문자열 비교를 수행할 때 레거시 정렬 동작을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-120">Specifies that the runtime should use legacy sorting behavior when performing string comparisons.</span></span>|
|[\<developmentMode>](developmentmode-element.md)|<span data-ttu-id="8d9a6-121">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-121">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|<span data-ttu-id="8d9a6-122">.NET Framework 버전 2.0의 기본 동작인 바인딩 실패의 캐싱을 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-122">Specifies whether the caching of binding failures, which is the default behavior in the .NET Framework version 2.0, is disabled.</span></span>|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|<span data-ttu-id="8d9a6-123">스레드가 시작될 때 전체 스레드 스택을 커밋할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-123">Specifies whether the full thread stack is committed when a thread is started.</span></span>|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|<span data-ttu-id="8d9a6-124">런타임 호스트가 애플리케이션 도메인에 대한 구성 설정을 재정의할 수 있도록 허용하는 기본 동작을 사용하지 않도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-124">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|<span data-ttu-id="8d9a6-125">날짜 및 시간 구문 분석 메서드가 조정된 규칙 집합을 사용하여 일, 월, 시간 및 오전/오후 지정자만 포함하는 날짜 문자열을 구문 분석할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-125">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|<span data-ttu-id="8d9a6-126">암호화 알고리즘이 FIPS(Federal Information Processing Standards)를 준수해야 하는 컴퓨터 구성 요구 사항을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-126">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>|
|[\<etwEnable>](etwenable-element.md)|<span data-ttu-id="8d9a6-127">공용 언어 런타임 이벤트에 대해 ETW(Windows용 이벤트 추적)를 사용하도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-127">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|<span data-ttu-id="8d9a6-128">PerfCounter.dll이 .NET Framework 버전 1.1 애플리케이션에서 CategoryOptions 레지스트리 설정을 사용하여 성능 카운터 데이터를 범주별 공유 메모리에서 로드할지 또는 전역 메모리에서 로드할지를 결정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-128">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|<span data-ttu-id="8d9a6-129">64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-129">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>|
|[\<gcConcurrent>](gcconcurrent-element.md)|<span data-ttu-id="8d9a6-130">공용 언어 런타임이 동시에 가비지 수집을 실행 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-130">Specifies whether the common language runtime runs garbage collection concurrently.</span></span>|
|[\<GCCpuGroup>](gccpugroup-element.md)|<span data-ttu-id="8d9a6-131">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-131">Specifies whether garbage collection supports multiple CPU groups.</span></span>|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|<span data-ttu-id="8d9a6-132">가비지 수집 힙과 개별 프로세서 간의 선호도를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-132">Defines the affinity between garbage collection heaps and individual processors.</span></span>|
|[\<GCHeapCount>](gcheapcount-element.md)|<span data-ttu-id="8d9a6-133">서버 가비지 수집에 사용할 힙/스레드 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-133">Specifies the number of heaps/threads to use for server garbage collection.</span></span>|
|[\<GCLOHThreshold>](gclohthreshold-element.md)|<span data-ttu-id="8d9a6-134">가비지 수집기가 큰 개체 힙에 개체를 배치 하 게 하는 임계값 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-134">Specifies the threshold size that causes the garbage collector to put objects on the large object heap.</span></span>|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|<span data-ttu-id="8d9a6-135">Cpu를 사용 하 여 서버 가비지 수집 스레드를 선호도 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-135">Specifies whether or not to affinitize server garbage collection threads with CPUs.</span></span>|
|[\<gcServer>](gcserver-element.md)|<span data-ttu-id="8d9a6-136">공용 언어 런타임이 서버 가비지 컬렉션을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-136">Specifies whether the common language runtime runs server garbage collection.</span></span>|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|<span data-ttu-id="8d9a6-137">런타임이 CAS(코드 액세스 보안) 게시자 정책을 사용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-137">Specifies whether the runtime uses code access security (CAS) publisher policy.</span></span>|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|<span data-ttu-id="8d9a6-138">런타임에서 관리 코드가 액세스 위반 및 기타 손상된 상태 예외를 catch하도록 허용하는지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-138">Specifies whether the runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|<span data-ttu-id="8d9a6-139">현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-139">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|<span data-ttu-id="8d9a6-140">원격 소스의 어셈블리를 완전 신뢰로 로드할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-140">Specifies whether assemblies from remote sources are loaded as full trust.</span></span>|
|[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)|<span data-ttu-id="8d9a6-141">런타임이 레거시 CAS(코드 액세스 보안) 정책을 사용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-141">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>|
|[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)|<span data-ttu-id="8d9a6-142">런타임이 잘못된 플랫폼 호출 선언을 실행 시간에 자동으로 수정할지를 지정합니다. 자동 수정을 수행하는 경우 관리 코드와 비관리 코드 간 전환 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-142">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|<span data-ttu-id="8d9a6-143">런타임이 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 대한 해시 코드를 계산하기 위해 고정된 양의 메모리를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-143">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>|
|[\<PreferComInsteadOfRemoting>](prefercominsteadofmanagedremoting-element.md)|<span data-ttu-id="8d9a6-144">런타임이 애플리케이션 도메인 경계 간에 원격 모드가 아닌 COM interop를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-144">Specifies that the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|
|[\<relativeBindForResources>](relativebindforresources-element.md)|<span data-ttu-id="8d9a6-145">위성 어셈블리에 대한 프로브를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-145">Optimizes the probe for satellite assemblies.</span></span>|
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|<span data-ttu-id="8d9a6-146">섀도 복사가 .NET Framework 4에서 도입 된 기본 시작 동작을 사용 하는지 아니면 이전 버전의 .NET Framework의 시작 동작으로 돌아가는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-146">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>|
|[\<supportPortability>](supportportability-element.md)|<span data-ttu-id="8d9a6-147">애플리케이션 이식성을 위해 어셈블리를 동일하게 간주하는 기본 동작을 사용하지 않도록 설정함으로써, 애플리케이션이 .NET Framework의 서로 다른 두 구현에서 같은 어셈블리를 참조할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-147">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="8d9a6-148">기본 메모리 내 개체 캐시에 대한 구성 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-148">Provides configuration information for the default in-memory object cache.</span></span>|
|[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)|<span data-ttu-id="8d9a6-149">런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-149">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|<span data-ttu-id="8d9a6-150">작업 예외가 처리되지 않으면 실행 중인 프로세스를 종료할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-150">Specifies whether unhandled task exceptions should terminate a running process.</span></span>|
|[\<TimeSpan_LegacyFormatMode>](timespan-legacyformatmode-element.md)|<span data-ttu-id="8d9a6-151">런타임이 <xref:System.TimeSpan> 값에 대해 레거시 서식을 사용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-151">Specifies whether the runtime uses legacy formatting for <xref:System.TimeSpan> values.</span></span>|
|[\<useLegacyJit>](uselegacyjit-element.md)|<span data-ttu-id="8d9a6-152">공용 언어 런타임이 Just-In-Time 컴파일에 레거시 64비트 JIT 컴파일러를 사용할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-152">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|<span data-ttu-id="8d9a6-153">런타임이 애플리케이션 도메인별로 문자열의 해시 코드를 계산할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-153">Specifies whether the runtime calculates hash codes for strings on a per application domain basis.</span></span>|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|<span data-ttu-id="8d9a6-154">런타임이 내부적으로 사용하는 특정 스레드를 만들 때 기본 스택 크기가 아닌 명시적 스택 크기를 사용하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-154">Requests that the runtime use explicit stack sizes when it creates certain threads that it uses internally, instead of the default stack size.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8d9a6-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8d9a6-155">Parent Elements</span></span>

|<span data-ttu-id="8d9a6-156">요소</span><span class="sxs-lookup"><span data-stu-id="8d9a6-156">Element</span></span>|<span data-ttu-id="8d9a6-157">설명</span><span class="sxs-lookup"><span data-stu-id="8d9a6-157">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="8d9a6-158">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-158">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d9a6-159">설명</span><span class="sxs-lookup"><span data-stu-id="8d9a6-159">Remarks</span></span>

<span data-ttu-id="8d9a6-160">구성 파일의 섹션에 있는 자식 요소는 [\<runtime>](runtime-element.md) 공용 언어 런타임에서 응용 프로그램이 실행 되는 방식을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-160">The child elements in the [\<runtime>](runtime-element.md) section of a configuration file are used by the common language runtime to configure how an application executes.</span></span> <span data-ttu-id="8d9a6-161">예를 들어, [\<gcServer>](gcserver-element.md) 요소는 가비지 수집기가 워크스테이션 가비지 컬렉션을 사용 하는지 아니면 서버 가비지 컬렉션을 사용 하는지 결정 하 [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) 고, 요소는 공용 언어 런타임이 응용 프로그램당 또는 응용 프로그램당 도메인 별로 문자열의 해시 코드를 계산할지 여부를 결정 하 고, `AppContextSwitchOverrides` 요소를 사용 하면 라이브러리 사용자가 라이브러리에서 제공 하는 변경 된 기능을 옵트인 또는 옵트아웃 (opt out) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-161">For example, the [\<gcServer>](gcserver-element.md) element determines whether the garbage collector uses workstation garbage collection or server garbage collection, the [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) element determines whether the common language runtime calculates hash codes for string on a per-application or a per-application domain basis, and the `AppContextSwitchOverrides` element allows library users to opt in or opt out of changed  functionality provided by a library.</span></span>

<span data-ttu-id="8d9a6-162">섹션의 요소는 [\<runtime>](runtime-element.md) 응용 프로그램 시작 시 공용 언어 런타임에 의해 자동으로 읽힙니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-162">The elements in the [\<runtime>](runtime-element.md) section are read automatically by the common language runtime at application startup.</span></span> <span data-ttu-id="8d9a6-163">속성에 해당 이름을 제공 하 여 기본이 아닌 응용 프로그램 도메인에 대 한 구성 파일을 정의할 수도 있습니다. <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> 이 경우 응용 프로그램 도메인이 로드 될 때 해당 설정이 자동으로 읽힙니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-163">You can also define the configuration file for a non-default application domain by supplying its name to the <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> property; its settings are read automatically when the application domain is loaded.</span></span> <span data-ttu-id="8d9a6-164">[\<runtime>](runtime-element.md)응용 프로그램의 구성 파일에서 섹션의 설정을 직접 읽어야 하는 경우에는 거의 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9a6-164">You should rarely, if ever, have a need to directly read the settings in the [\<runtime>](runtime-element.md) section in your application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d9a6-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d9a6-165">See also</span></span>

- [<span data-ttu-id="8d9a6-166">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8d9a6-166">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8d9a6-167">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8d9a6-167">Configuration File Schema</span></span>](../index.md)

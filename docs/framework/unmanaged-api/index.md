---
title: 관리되지 않는 API 참조
ms.date: 11/06/2017
helpviewer_keywords:
- runtime, unmanaged APIs
- common language runtime, unmanaged APIs
- native API reference [.NET Framework]
- unmanaged API reference [.NET Framework]
ms.assetid: 9aa000ee-c04c-492c-ae4f-83ecdf4fdbbe
ms.openlocfilehash: 0153279608e2359747f1be6b9542d6906c1b3995
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559306"
---
# <a name="unmanaged-api-reference"></a><span data-ttu-id="77386-102">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="77386-102">Unmanaged API Reference</span></span>
<span data-ttu-id="77386-103">이 섹션에는 런타임 호스트, 컴파일러, 디스어셈블러, 난독 처리기, 디버거, 프로파일러 등의 관리 코드 관련 애플리케이션에서 사용할 수 있는 관리되지 않는 API에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77386-103">This section includes information on unmanaged APIs that can be used by managed-code-related applications, such as runtime hosts, compilers, disassemblers, obfuscators, debuggers, and profilers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77386-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="77386-104">In This Section</span></span>  
 [<span data-ttu-id="77386-105">공통 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="77386-105">Common Data Types</span></span>](common-data-types-unmanaged-api-reference.md)  
 <span data-ttu-id="77386-106">특히 관리되지 않는 프로파일링 및 디버깅 API에서 사용되는 공통 데이터 형식에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-106">Lists the common data types that are used, particularly in the unmanaged profiling and debugging APIs.</span></span>  
  
 [<span data-ttu-id="77386-107">ALink</span><span class="sxs-lookup"><span data-stu-id="77386-107">ALink</span></span>](./alink/index.md)  
 <span data-ttu-id="77386-108">.NET Framework 어셈블리 및 바인딩되지 않은 모듈 만들기를 지원하는 ALink API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-108">Describes the ALink API, which supports the creation of .NET Framework assemblies and unbound modules.</span></span>  
  
 [<span data-ttu-id="77386-109">Authenticode</span><span class="sxs-lookup"><span data-stu-id="77386-109">Authenticode</span></span>](./authenticode/index.md)  
 <span data-ttu-id="77386-110">Authenticode XrML 라이센스 만들기 및 확인 모듈을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-110">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
 [<span data-ttu-id="77386-111">상수</span><span class="sxs-lookup"><span data-stu-id="77386-111">Constants</span></span>](constants-unmanaged-api-reference.md)  
 <span data-ttu-id="77386-112">CorSym.idl에 정의된 상수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-112">Describes the constants that are defined in CorSym.idl.</span></span>  
  
 <span data-ttu-id="77386-113">[사용자 지정 인터페이스 특성](/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="77386-113">[Custom Interface Attributes](/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span></span>  
 <span data-ttu-id="77386-114">COM(구성 요소 개체 모델) 사용자 지정 인터페이스 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-114">Describes component object model (COM) custom interface attributes.</span></span>  
  
 [<span data-ttu-id="77386-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="77386-115">Debugging</span></span>](./debugging/index.md)  
 <span data-ttu-id="77386-116">디버거가 CLR(공용 언어 런타임) 환경에서 실행되는 코드를 디버그할 수 있도록 하는 디버깅 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-116">Describes the debugging API, which enables a debugger to debug code that runs in the common language runtime (CLR) environment.</span></span>  
  
 [<span data-ttu-id="77386-117">진단 기호 저장소</span><span class="sxs-lookup"><span data-stu-id="77386-117">Diagnostics Symbol Store</span></span>](./diagnostics/index.md)  
 <span data-ttu-id="77386-118">컴파일러가 디버거에 사용되는 기호 정보를 생성할 수 있도록 하는 진단 기호 저장소 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-118">Describes the diagnostics symbol store API, which enables a compiler to generate symbol information for use by a debugger.</span></span>  
  
 [<span data-ttu-id="77386-119">Fusion</span><span class="sxs-lookup"><span data-stu-id="77386-119">Fusion</span></span>](./fusion/index.md)  
 <span data-ttu-id="77386-120">런타임 호스트가 애플리케이션 리소스의 속성에 액세스하여 애플리케이션용으로 해당 리소스의 정확한 버전을 찾을 수 있도록 하는 Fusion API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-120">Describes the fusion API, which enables a runtime host to access the properties of an application's resources in order to locate the correct versions of those resources for the application.</span></span>  
  
 [<span data-ttu-id="77386-121">호스팅</span><span class="sxs-lookup"><span data-stu-id="77386-121">Hosting</span></span>](./hosting/index.md)  
 <span data-ttu-id="77386-122">관리되지 않는 호스트가 CLR을 애플리케이션에 통합할 수 있도록 하는 호스팅 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-122">Describes the hosting API, which enables unmanaged hosts to integrate the CLR into their applications.</span></span>  
  
 [<span data-ttu-id="77386-123">메타데이터</span><span class="sxs-lookup"><span data-stu-id="77386-123">Metadata</span></span>](./metadata/index.md)  
 <span data-ttu-id="77386-124">컴파일러 등의 클라이언트가 CLR에 형식을 로드하지 않아도 구성 요소 메타데이터를 생성하거나 액세스할 수 있도록 하는 메타데이터 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-124">Describes the metadata API, which enables a client such as a compiler to generate or access a component's metadata without the types being loaded by the CLR.</span></span>  
  
 [<span data-ttu-id="77386-125">프로파일링</span><span class="sxs-lookup"><span data-stu-id="77386-125">Profiling</span></span>](./profiling/index.md)  
 <span data-ttu-id="77386-126">프로파일러가 CLR에 의한 프로그램 실행을 모니터링할 수 있도록 하는 프로파일링 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-126">Describes the profiling API, which enables a profiler to monitor a program's execution by the CLR.</span></span>  
  
 [<span data-ttu-id="77386-127">강력한 이름</span><span class="sxs-lookup"><span data-stu-id="77386-127">Strong Naming</span></span>](./strong-naming/index.md)  
 <span data-ttu-id="77386-128">클라이언트가 어셈블리에 대해 강력한 이름 서명을 관리할 수 있도록 하는 강력한 이름 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-128">Describes the strong naming API, which enables a client to administer strong name signing for assemblies.</span></span>  

 [<span data-ttu-id="77386-129">WMI 및 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="77386-129">WMI and Performance Counters</span></span>](wmi/index.md)  
 <span data-ttu-id="77386-130">WMI(Windows Management Instrumentation) 라이브러리에 대한 호출을 래핑하는 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-130">Describes the APIs that wrap calls to Windows Management Instrumentation (WMI) libraries.</span></span>
  
 [<span data-ttu-id="77386-131">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="77386-131">Tlbexp Helper Functions</span></span>](./tlbexp/index.md)  
 <span data-ttu-id="77386-132">어셈블리에서 형식 라이브러리로의 변환 프로세스 중 형식 라이브러리 내보내기(Tlbexp.exe)에서 사용하는 두 도우미 함수 및 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77386-132">Describes the two helper functions and interface used by the Type Library Exporter (Tlbexp.exe) during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77386-133">관련 단원</span><span class="sxs-lookup"><span data-stu-id="77386-133">Related Sections</span></span>  
 [<span data-ttu-id="77386-134">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="77386-134">Development Guide</span></span>](../development-guide.md)

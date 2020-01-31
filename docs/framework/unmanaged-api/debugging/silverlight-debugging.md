---
title: Silverlight 디버깅
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 91f311818b615ea8f166bb3362ec52d39fcd0297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790320"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="16596-102">Silverlight 디버깅</span><span class="sxs-lookup"><span data-stu-id="16596-102">Silverlight Debugging</span></span>
<span data-ttu-id="16596-103">이 섹션의 항목에서는 CLR(공용 언어 런타임)이 Windows 운영 체제나 Macintosh 플랫폼에서 실행 중인 Silverlight 기반 애플리케이션 디버그를 지원하기 위해 제공하는 환경 및 인터페이스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16596-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16596-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="16596-104">In This Section</span></span>  
 [<span data-ttu-id="16596-105">EnumerateCLRs 함수</span><span class="sxs-lookup"><span data-stu-id="16596-105">EnumerateCLRs Function</span></span>](enumerateclrs-function.md)  
 <span data-ttu-id="16596-106">프로세스의 CLR을 열거하기 위한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16596-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="16596-107">CloseCLREnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="16596-107">CloseCLREnumeration Function</span></span>](closeclrenumeration-function.md)  
 <span data-ttu-id="16596-108">[EnumerateCLRs 함수](enumerateclrs-function.md)에서 반환 된 핸들 배열에 있는 모든 유효한 CLR continue 시작 이벤트를 닫고 핸들 및 문자열 경로 배열에 대 한 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="16596-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="16596-109">CreateCoreClrDebugTarget 함수</span><span class="sxs-lookup"><span data-stu-id="16596-109">CreateCoreClrDebugTarget Function</span></span>](createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="16596-110">프로세스 및 런타임 열거형의 원격 대상에 대한 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16596-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="16596-111">CreateCordbObject 함수</span><span class="sxs-lookup"><span data-stu-id="16596-111">CreateCordbObject Function</span></span>](createcordbobject-function.md)  
 <span data-ttu-id="16596-112">원격 프로세스에서 관리되는 디버깅 세션을 인스턴스화하기 위한 기능을 제공하는 디버거 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16596-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="16596-113">CreateVersionStringFromModule 함수</span><span class="sxs-lookup"><span data-stu-id="16596-113">CreateVersionStringFromModule Function</span></span>](createversionstringfrommodule-function.md)  
 <span data-ttu-id="16596-114">대상 프로세스의 CLR 경로에서 버전 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16596-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="16596-115">CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="16596-115">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="16596-116">[Createversionstringfrommodule 함수](createversionstringfrommodule-function.md)함수에서 반환 된 CLR 버전 문자열을 수락 하 고 해당 디버거 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="16596-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="16596-117">CoreClrDebugProcInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="16596-117">CoreClrDebugProcInfo Structure</span></span>](coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="16596-118">원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16596-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="16596-119">CoreClrDebugRuntimeInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="16596-119">CoreClrDebugRuntimeInfo Structure</span></span>](coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="16596-120">원격 컴퓨터의 프로세스에서 로드된 CLR 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16596-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="16596-121">GetStartupNotificationEvent 함수</span><span class="sxs-lookup"><span data-stu-id="16596-121">GetStartupNotificationEvent Function</span></span>](getstartupnotificationevent-function.md)  
 <span data-ttu-id="16596-122">지정된 대상 프로세스에 로드 중인 CLR(공용 언어 런타임)에서 신호를 전송할 이벤트 핸들을 만들거나 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16596-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="16596-123">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16596-123">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="16596-124">프로세스 및 런타임 열거형의 원격 대상에 대한 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16596-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="16596-125">InitDbgTransportManager 함수</span><span class="sxs-lookup"><span data-stu-id="16596-125">InitDbgTransportManager Function</span></span>](initdbgtransportmanager-function.md)  
 <span data-ttu-id="16596-126">프로세스 및 런타임 열거형의 원격 대상에 연결할 전송 관리자를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="16596-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="16596-127">ShutdownDbgTransportManager 함수</span><span class="sxs-lookup"><span data-stu-id="16596-127">ShutdownDbgTransportManager Function</span></span>](shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="16596-128">원격 대상 컴퓨터에 대한 연결을 위해 전송 관리자를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="16596-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16596-129">참조</span><span class="sxs-lookup"><span data-stu-id="16596-129">See also</span></span>

- [<span data-ttu-id="16596-130">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="16596-130">Debugging Coclasses</span></span>](debugging-coclasses.md)
- [<span data-ttu-id="16596-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16596-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="16596-132">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="16596-132">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
- [<span data-ttu-id="16596-133">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="16596-133">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="16596-134">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="16596-134">Debugging Structures</span></span>](debugging-structures.md)

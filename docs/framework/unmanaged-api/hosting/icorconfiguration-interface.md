---
description: '자세히 알아보기: ICorConfiguration 인터페이스'
title: ICorConfiguration 인터페이스
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: f75e9e445c7fe4615abcae27756bcc420b5255b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636691"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="719b1-103">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="719b1-103">ICorConfiguration Interface</span></span>

<span data-ttu-id="719b1-104">CLR (공용 언어 런타임)을 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="719b1-104">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="719b1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="719b1-105">Methods</span></span>  
  
|<span data-ttu-id="719b1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="719b1-106">Method</span></span>|<span data-ttu-id="719b1-107">설명</span><span class="sxs-lookup"><span data-stu-id="719b1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="719b1-108">AddDebuggerSpecialThread 메서드</span><span class="sxs-lookup"><span data-stu-id="719b1-108">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="719b1-109">관리 되거나 관리 되지 않는 디버깅 시나리오에서 디버거가 응용 프로그램을 중지 하는 동안 특정 스레드가 계속 실행 되도록 허용 해야 하는 디버깅 서비스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="719b1-109">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="719b1-110">SetDebuggerThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="719b1-110">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="719b1-111">디버깅을 위해 CLR 스레드가 차단 되 고 차단 해제 될 때 디버깅 서비스에서 호출할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="719b1-111">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="719b1-112">SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="719b1-112">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="719b1-113">가비지 수집기에서 가상 메모리의 한도를 변경 하는 호스트를 요청 하는 데 사용할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="719b1-113">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="719b1-114">SetGCThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="719b1-114">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="719b1-115">가비지 컬렉션에 대해 차단 되는 런타임 이외의 작업에 대해 스레드를 예약 하는 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="719b1-115">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="719b1-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="719b1-116">Requirements</span></span>  

 <span data-ttu-id="719b1-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="719b1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="719b1-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="719b1-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="719b1-119">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="719b1-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="719b1-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="719b1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="719b1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="719b1-121">See also</span></span>

- [<span data-ttu-id="719b1-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="719b1-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="719b1-123">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="719b1-123">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)

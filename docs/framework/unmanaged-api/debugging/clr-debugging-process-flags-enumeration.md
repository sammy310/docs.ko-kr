---
title: CLR_DEBUGGING_PROCESS_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274109"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="9b775-102">CLR_DEBUGGING_PROCESS_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="9b775-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="9b775-103">[ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) 메서드에서 사용 하는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b775-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b775-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9b775-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9b775-105">Members</span></span>  
  
|<span data-ttu-id="9b775-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9b775-106">Member</span></span>|<span data-ttu-id="9b775-107">설명</span><span class="sxs-lookup"><span data-stu-id="9b775-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="9b775-108">이 런타임에는 catch 할 수 없는 관리 되는 디버거 이벤트를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="9b775-109">보완 이벤트와 비 catch 이벤트의 차이점은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b775-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="9b775-110">보류 중인 <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 관리 되는 이벤트는 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b775-111">설명</span><span class="sxs-lookup"><span data-stu-id="9b775-111">Remarks</span></span>  
 <span data-ttu-id="9b775-112">프로세스에 연결 된 후 디버거를 현재 상태로 전환 하는 프로세스, 응용 프로그램 도메인, 어셈블리, 모듈 및 스레드 만들기 알림이 이벤트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="9b775-113">`CLR_DEBUGGING_MANAGED_EVENT_PENDING` 플래그가 나타내는 비 catch 이벤트는 예외 및 MDA (관리 디버깅 도우미) 알림과 같은 다른 모든 디버거 이벤트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="9b775-114">이 `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` 플래그를 사용 하면 런타임에서 종료 하는 예외와 취소할 수 있는 관리 되는 디버거 연결 요청을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b775-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b775-115">Requirements</span></span>  
 <span data-ttu-id="9b775-116">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b775-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b775-117">**헤더:** Metahost.idl, Metahost.h</span><span class="sxs-lookup"><span data-stu-id="9b775-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="9b775-118">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b775-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b775-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b775-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b775-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b775-120">See also</span></span>

- [<span data-ttu-id="9b775-121">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="9b775-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="9b775-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="9b775-122">Debugging</span></span>](index.md)

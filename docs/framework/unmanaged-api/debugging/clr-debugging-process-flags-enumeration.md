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
ms.openlocfilehash: 8321e5aeba435ca5f1398a9cb827a93ae821d686
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217330"
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="2bac1-102">CLR_DEBUGGING_PROCESS_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="2bac1-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="2bac1-103">사용 되는 값을 제공 합니다 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="2bac1-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bac1-104">구문</span><span class="sxs-lookup"><span data-stu-id="2bac1-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="2bac1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2bac1-105">Members</span></span>  
  
|<span data-ttu-id="2bac1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2bac1-106">Member</span></span>|<span data-ttu-id="2bac1-107">설명</span><span class="sxs-lookup"><span data-stu-id="2bac1-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="2bac1-108">이 런타임에 보내도록 catch up 아닌 관리 되는 디버거 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2bac1-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="2bac1-109">보완 및 비 catch 이벤트 간의 차이 대 한 설명 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bac1-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="2bac1-110">보류 중인 관리 되는 이벤트를 <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bac1-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bac1-111">설명</span><span class="sxs-lookup"><span data-stu-id="2bac1-111">Remarks</span></span>  
 <span data-ttu-id="2bac1-112">후속 이벤트 프로세스, 응용 프로그램 도메인, 어셈블리, 모듈 및 프로세스에 연결 된 후 현재 상태까지 디버거를 제공 하는 스레드 생성 알림을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bac1-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="2bac1-113">표시 된 비-catch-최대 이벤트는 `CLR_DEBUGGING_MANAGED_EVENT_PENDING` 플래그 모든 다른 디버거 이벤트, 예외 등을 포함 하 고 관리 디버깅 도우미 (MDA) 알림.</span><span class="sxs-lookup"><span data-stu-id="2bac1-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="2bac1-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` 플래그 예외를 종료 하 고 취소할 수 있는 관리 되는 디버거가 연결 요청을 구분할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bac1-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bac1-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bac1-115">Requirements</span></span>  
 <span data-ttu-id="2bac1-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2bac1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bac1-117">**헤더:** Metahost.idl, Metahost.h</span><span class="sxs-lookup"><span data-stu-id="2bac1-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="2bac1-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bac1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bac1-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bac1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bac1-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="2bac1-120">See also</span></span>

- [<span data-ttu-id="2bac1-121">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="2bac1-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="2bac1-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="2bac1-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

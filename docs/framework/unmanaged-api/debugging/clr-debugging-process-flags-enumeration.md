---
description: '다음에 대 한 자세한 정보: 열거형 CLR_DEBUGGING_PROCESS_FLAGS'
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
ms.openlocfilehash: 81510bde123ef9a8adefaec5b0708086dacbbf2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772811"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="a392d-103">CLR_DEBUGGING_PROCESS_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="a392d-103">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>

<span data-ttu-id="a392d-104">[ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) 메서드에서 사용 하는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a392d-104">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a392d-105">구문</span><span class="sxs-lookup"><span data-stu-id="a392d-105">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a392d-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a392d-106">Members</span></span>  
  
|<span data-ttu-id="a392d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a392d-107">Member</span></span>|<span data-ttu-id="a392d-108">설명</span><span class="sxs-lookup"><span data-stu-id="a392d-108">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="a392d-109">이 런타임에는 catch 할 수 없는 관리 되는 디버거 이벤트를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a392d-109">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="a392d-110">보완 이벤트와 비 catch 이벤트의 차이점은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a392d-110">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="a392d-111">보류 중인 관리 되는 이벤트는 <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="a392d-111">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a392d-112">설명</span><span class="sxs-lookup"><span data-stu-id="a392d-112">Remarks</span></span>  

 <span data-ttu-id="a392d-113">프로세스에 연결 된 후 디버거를 현재 상태로 전환 하는 프로세스, 응용 프로그램 도메인, 어셈블리, 모듈 및 스레드 만들기 알림이 이벤트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a392d-113">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="a392d-114">플래그가 나타내는 비 catch 이벤트는 `CLR_DEBUGGING_MANAGED_EVENT_PENDING` 예외 및 MDA (관리 디버깅 도우미) 알림과 같은 다른 모든 디버거 이벤트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a392d-114">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="a392d-115">이 `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` 플래그를 사용 하면 런타임에서 종료 하는 예외와 취소할 수 있는 관리 되는 디버거 연결 요청을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a392d-115">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a392d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a392d-116">Requirements</span></span>  

 <span data-ttu-id="a392d-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a392d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a392d-118">**헤더:** Metahost, Metahost</span><span class="sxs-lookup"><span data-stu-id="a392d-118">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="a392d-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a392d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a392d-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a392d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a392d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a392d-121">See also</span></span>

- [<span data-ttu-id="a392d-122">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="a392d-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="a392d-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="a392d-123">Debugging</span></span>](index.md)

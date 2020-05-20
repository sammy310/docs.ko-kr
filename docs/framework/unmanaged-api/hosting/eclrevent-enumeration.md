---
title: EClrEvent 열거형
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 388f0de26983f8bb876f40a527f60d8bc59191a3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616355"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="9cb0d-102">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="9cb0d-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="9cb0d-103">호스트가 콜백을 등록할 수 있는 CLR (공용 언어 런타임) 이벤트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb0d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9cb0d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="9cb0d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9cb0d-105">Members</span></span>  
  
|<span data-ttu-id="9cb0d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9cb0d-106">Member</span></span>|<span data-ttu-id="9cb0d-107">설명</span><span class="sxs-lookup"><span data-stu-id="9cb0d-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="9cb0d-108">심각한 CLR 오류를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="9cb0d-109">특정의 언로드를 지정 합니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="9cb0d-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="9cb0d-110">MDA (관리 디버깅 도우미) 메시지를 생성 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="9cb0d-111">스택 오버플로 오류가 발생 했음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cb0d-112">설명</span><span class="sxs-lookup"><span data-stu-id="9cb0d-112">Remarks</span></span>  
 <span data-ttu-id="9cb0d-113">호스트는 `EClrEvent` [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) 인터페이스의 메서드를 호출 하 여에서 설명 하는 이벤트 형식에 대해 콜백을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="9cb0d-114">호스트는 [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여이 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="9cb0d-115">`Event_CLRDisabled`및 `Event_DomainUnload` 이벤트는 서로 다른 스레드에서 두 번 이상 발생 하거나 CLR을 사용 하지 않도록 설정 하거나 언로드할 때 신호를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="9cb0d-116">`Event_MDAFired`이벤트는 MDA 메시지의 세부 정보가 포함 된 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) 인스턴스 만들기를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="9cb0d-117">Mda에 대 한 자세한 내용은 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cb0d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9cb0d-118">Requirements</span></span>  
 <span data-ttu-id="9cb0d-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cb0d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cb0d-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9cb0d-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cb0d-121">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9cb0d-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cb0d-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cb0d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb0d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cb0d-123">See also</span></span>

- [<span data-ttu-id="9cb0d-124">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb0d-124">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="9cb0d-125">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb0d-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="9cb0d-126">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="9cb0d-126">Hosting Enumerations</span></span>](hosting-enumerations.md)

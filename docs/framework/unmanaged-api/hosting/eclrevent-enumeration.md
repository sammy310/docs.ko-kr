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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13d564be68d6b49a1616be97710312f33f828d48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176347"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="8cf2f-102">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="8cf2f-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="8cf2f-103">호스트 콜백을 등록할 수 있는 공용 언어 런타임 (CLR) 이벤트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf2f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8cf2f-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="8cf2f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8cf2f-105">Members</span></span>  
  
|<span data-ttu-id="8cf2f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8cf2f-106">Member</span></span>|<span data-ttu-id="8cf2f-107">설명</span><span class="sxs-lookup"><span data-stu-id="8cf2f-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="8cf2f-108">CLR 오류를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="8cf2f-109">특정 언로드한다 지정 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="8cf2f-110">관리 디버깅 도우미 (MDA) 메시지에 생성 되었음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="8cf2f-111">스택 오버플로 오류가 발생을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cf2f-112">설명</span><span class="sxs-lookup"><span data-stu-id="8cf2f-112">Remarks</span></span>  
 <span data-ttu-id="8cf2f-113">호스트에 설명 된 이벤트 형식에 대 한 콜백을 등록할 수 있습니다 `EClrEvent` 의 메서드를 호출 하 여 합니다 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="8cf2f-114">호스트를 호출 하 여이 인터페이스에 대 한 포인터를 가져옵니다 합니다 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="8cf2f-115">합니다 `Event_CLRDisabled` 및 `Event_DomainUnload` 이벤트가 두 번 이상 및는 언로드 또는 CLR의 비활성화를 알리기 위해 서로 다른 여러 스레드에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="8cf2f-116">합니다 `Event_MDAFired` 이벤트를 생성 시킵니다는 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) MDA 메시지의 세부 정보를 포함 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="8cf2f-117">Mda에 대 한 자세한 내용은 참조 하세요. [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf2f-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cf2f-118">Requirements</span></span>  
 <span data-ttu-id="8cf2f-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8cf2f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf2f-120">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8cf2f-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cf2f-121">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8cf2f-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cf2f-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf2f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf2f-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="8cf2f-123">See also</span></span>

- [<span data-ttu-id="8cf2f-124">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cf2f-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="8cf2f-125">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cf2f-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8cf2f-126">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="8cf2f-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

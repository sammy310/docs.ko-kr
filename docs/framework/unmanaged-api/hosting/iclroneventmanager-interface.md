---
title: ICLROnEventManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183003"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="475ae-102">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="475ae-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="475ae-103">등록 및 공용 언어 런타임 (CLR) 이벤트에 대 한 콜백을 등록 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="475ae-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="475ae-104">메서드</span><span class="sxs-lookup"><span data-stu-id="475ae-104">Methods</span></span>  
  
|<span data-ttu-id="475ae-105">메서드</span><span class="sxs-lookup"><span data-stu-id="475ae-105">Method</span></span>|<span data-ttu-id="475ae-106">설명</span><span class="sxs-lookup"><span data-stu-id="475ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="475ae-107">RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="475ae-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="475ae-108">지정된 된 이벤트에 대 한 콜백 포인터를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="475ae-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="475ae-109">UnregisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="475ae-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="475ae-110">지정된 된 이벤트에 대 한 이전에 등록 된 콜백 포인터를 등록 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="475ae-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="475ae-111">설명</span><span class="sxs-lookup"><span data-stu-id="475ae-111">Remarks</span></span>  
 <span data-ttu-id="475ae-112">호스트를 등록 하 고 이벤트 콜백을 등록 취소에 대 한 참조를 가져옵니다 `ICLROnEventManager` 를 호출 하 여 합니다 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="475ae-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="475ae-113">설명 하는 이벤트 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 두 번 이상 및는 언로드 또는 CLR의 비활성화를 알리기 위해 서로 다른 여러 스레드에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="475ae-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="475ae-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="475ae-114">Requirements</span></span>  
 <span data-ttu-id="475ae-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="475ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="475ae-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="475ae-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="475ae-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="475ae-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="475ae-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="475ae-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="475ae-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="475ae-119">See also</span></span>

- [<span data-ttu-id="475ae-120">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="475ae-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="475ae-121">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="475ae-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="475ae-122">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="475ae-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="475ae-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="475ae-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

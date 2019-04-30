---
title: IActionOnCLREvent 인터페이스
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864a8a4dd9f96da2fd0e0025848a910b4f8b0a70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985532"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="98720-102">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98720-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="98720-103">제공 합니다 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 에 대 한 호출을 사용 하 여 등록 된 이벤트에서 콜백을 수행 하는 메서드는 [iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="98720-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98720-104">메서드</span><span class="sxs-lookup"><span data-stu-id="98720-104">Methods</span></span>  
  
|<span data-ttu-id="98720-105">메서드</span><span class="sxs-lookup"><span data-stu-id="98720-105">Method</span></span>|<span data-ttu-id="98720-106">설명</span><span class="sxs-lookup"><span data-stu-id="98720-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98720-107">OnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="98720-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="98720-108">등록된 된 이벤트에 대 한 콜백을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="98720-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98720-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98720-109">Requirements</span></span>  
 <span data-ttu-id="98720-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98720-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98720-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98720-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98720-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="98720-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98720-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98720-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98720-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="98720-114">See also</span></span>

- [<span data-ttu-id="98720-115">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="98720-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="98720-116">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98720-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="98720-117">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98720-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="98720-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98720-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

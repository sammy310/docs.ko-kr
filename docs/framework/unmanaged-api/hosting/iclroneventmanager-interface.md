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
ms.openlocfilehash: 3633db69877db771d919c9f43da4809f8321f77c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951192"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="fdca2-102">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdca2-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="fdca2-103">호스트가 CLR (공용 언어 런타임) 이벤트에 대 한 콜백을 등록 하 고 등록 취소할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdca2-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdca2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fdca2-104">Methods</span></span>  
  
|<span data-ttu-id="fdca2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fdca2-105">Method</span></span>|<span data-ttu-id="fdca2-106">Description</span><span class="sxs-lookup"><span data-stu-id="fdca2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdca2-107">RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="fdca2-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="fdca2-108">지정 된 이벤트에 대 한 콜백 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdca2-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="fdca2-109">UnregisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="fdca2-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="fdca2-110">지정 된 이벤트에 대해 이전에 등록 된 콜백 포인터의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdca2-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdca2-111">설명</span><span class="sxs-lookup"><span data-stu-id="fdca2-111">Remarks</span></span>  
 <span data-ttu-id="fdca2-112">이벤트 콜백을 등록 하 고 등록을 취소 하기 위해 호스트는 `ICLROnEventManager` [ICLRControl:: getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fdca2-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdca2-113">[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 에서 설명 하는 이벤트는 여러 스레드에서 두 번 이상 발생 하 여 언로드 또는 CLR 비활성화를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdca2-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdca2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdca2-114">Requirements</span></span>  
 <span data-ttu-id="fdca2-115">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fdca2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdca2-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fdca2-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fdca2-117">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdca2-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdca2-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdca2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdca2-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="fdca2-119">See also</span></span>

- [<span data-ttu-id="fdca2-120">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="fdca2-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="fdca2-121">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdca2-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="fdca2-122">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdca2-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="fdca2-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdca2-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

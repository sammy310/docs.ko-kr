---
title: ICLRIoCompletionManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141023"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="f269f-102">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f269f-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="f269f-103">호스트가 지정 된 i/o 요청 상태를 CLR (공용 언어 런타임)에 알릴 수 있도록 하는 콜백 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f269f-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f269f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f269f-104">Methods</span></span>  
  
|<span data-ttu-id="f269f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f269f-105">Method</span></span>|<span data-ttu-id="f269f-106">설명</span><span class="sxs-lookup"><span data-stu-id="f269f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f269f-107">OnComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="f269f-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="f269f-108">[IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 수행 된 i/o 요청의 상태를 CLR에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f269f-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f269f-109">주의</span><span class="sxs-lookup"><span data-stu-id="f269f-109">Remarks</span></span>  
 <span data-ttu-id="f269f-110">호스트는 [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) 인터페이스를 사용 하 여 i/o 완료 추상화를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f269f-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="f269f-111">CLR은이 인터페이스를 통해 i/o 요청을 수행 하 고, 호스트는 `ICLRIoCompletionManager` 인터페이스를 사용 하 여 이러한 요청의 결과를 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f269f-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f269f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f269f-112">Requirements</span></span>  
 <span data-ttu-id="f269f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f269f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f269f-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f269f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f269f-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f269f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f269f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f269f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f269f-117">참조</span><span class="sxs-lookup"><span data-stu-id="f269f-117">See also</span></span>

- [<span data-ttu-id="f269f-118">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f269f-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="f269f-119">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f269f-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="f269f-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f269f-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

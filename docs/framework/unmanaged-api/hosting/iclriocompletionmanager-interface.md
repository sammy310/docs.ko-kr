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
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703558"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="306ca-102">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="306ca-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="306ca-103">호스트가 지정 된 i/o 요청 상태를 CLR (공용 언어 런타임)에 알릴 수 있도록 하는 콜백 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="306ca-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="306ca-104">메서드</span><span class="sxs-lookup"><span data-stu-id="306ca-104">Methods</span></span>  
  
|<span data-ttu-id="306ca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="306ca-105">Method</span></span>|<span data-ttu-id="306ca-106">설명</span><span class="sxs-lookup"><span data-stu-id="306ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="306ca-107">OnComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="306ca-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="306ca-108">[IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 수행 된 i/o 요청의 상태를 CLR에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="306ca-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="306ca-109">설명</span><span class="sxs-lookup"><span data-stu-id="306ca-109">Remarks</span></span>  
 <span data-ttu-id="306ca-110">호스트는 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) 인터페이스를 사용 하 여 i/o 완료 추상화를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="306ca-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="306ca-111">CLR은이 인터페이스를 통해 i/o 요청을 만들고, 호스트는 인터페이스를 사용 하 여 이러한 요청의 결과를 런타임에 알립니다 `ICLRIoCompletionManager` .</span><span class="sxs-lookup"><span data-stu-id="306ca-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306ca-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="306ca-112">Requirements</span></span>  
 <span data-ttu-id="306ca-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="306ca-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306ca-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="306ca-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="306ca-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="306ca-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="306ca-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306ca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306ca-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="306ca-117">See also</span></span>

- [<span data-ttu-id="306ca-118">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="306ca-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="306ca-119">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="306ca-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="306ca-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="306ca-120">Hosting Interfaces</span></span>](hosting-interfaces.md)

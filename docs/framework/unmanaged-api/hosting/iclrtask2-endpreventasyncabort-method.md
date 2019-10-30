---
title: ICLRTask2::EndPreventAsyncAbort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 8ae66e0bf96138e5bc2f33e4c14ad86e7dabc6b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124546"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="e6af2-102">ICLRTask2::EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="e6af2-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="e6af2-103">새 스레드 또는 보류 중인 스레드 중단 요청을 허용 하 여 현재 스레드에 대 한 스레드 중단을 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6af2-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6af2-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e6af2-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="e6af2-105">Return Value</span></span>  
 <span data-ttu-id="e6af2-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e6af2-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6af2-107">HRESULT</span></span>|<span data-ttu-id="e6af2-108">설명</span><span class="sxs-lookup"><span data-stu-id="e6af2-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6af2-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6af2-109">S_OK</span></span>|<span data-ttu-id="e6af2-110">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="e6af2-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="e6af2-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="e6af2-112">현재 스레드가 아닌 스레드에서 메서드가 호출 된 경우</span><span class="sxs-lookup"><span data-stu-id="e6af2-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6af2-113">주의</span><span class="sxs-lookup"><span data-stu-id="e6af2-113">Remarks</span></span>  
 <span data-ttu-id="e6af2-114">이 메서드를 호출 하면 현재 스레드에 대 한 지연 스레드 중단 카운터가 1 씩 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="e6af2-115">[ICLRTask2:: BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) 및 `EndPreventAsyncAbort`에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="e6af2-116">카운터가 0 보다 큰 경우 현재 스레드에 대 한 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="e6af2-117">이 기능에 의해 노출 되는 기능은 VM (가상 컴퓨터)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="e6af2-118">이러한 메서드를 잘못 지정 하면 VM에서 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="e6af2-119">예를 들어 먼저 `BeginPreventAsyncAbort`를 호출 하지 않고 `EndPreventAsyncAbort`를 호출 하면 VM이 이전에 증가 한 경우 카운터를 0으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="e6af2-120">마찬가지로 내부 카운터는 오버플로를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="e6af2-121">호스트와 VM이 모두 증가 하 여 정수 한도를 초과 하는 경우 결과 동작은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6af2-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6af2-122">Requirements</span></span>  
 <span data-ttu-id="e6af2-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6af2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6af2-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e6af2-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6af2-125">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6af2-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6af2-126">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6af2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6af2-127">참조</span><span class="sxs-lookup"><span data-stu-id="e6af2-127">See also</span></span>

- [<span data-ttu-id="e6af2-128">BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="e6af2-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="e6af2-129">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6af2-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="e6af2-130">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6af2-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e6af2-131">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6af2-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e6af2-132">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6af2-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e6af2-133">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6af2-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

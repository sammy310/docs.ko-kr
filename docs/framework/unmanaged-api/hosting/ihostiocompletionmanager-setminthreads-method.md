---
title: IHostIoCompletionManager::SetMinThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: 29a2fc5652badcc00378192debccba0356f5339e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804662"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="75268-102">IHostIoCompletionManager::SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="75268-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="75268-103">호스트에서 i/o 완료에 대해 할당할 최소 스레드 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75268-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75268-104">구문</span><span class="sxs-lookup"><span data-stu-id="75268-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75268-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75268-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="75268-106">진행 호스트에서 만들어야 하는 i/o 완료 스레드의 최소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="75268-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75268-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="75268-107">Return Value</span></span>  
  
|<span data-ttu-id="75268-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75268-108">HRESULT</span></span>|<span data-ttu-id="75268-109">Description</span><span class="sxs-lookup"><span data-stu-id="75268-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75268-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="75268-110">S_OK</span></span>|<span data-ttu-id="75268-111">`SetMinThreads`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="75268-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="75268-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="75268-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="75268-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="75268-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="75268-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-115">The call timed out.</span></span>|  
|<span data-ttu-id="75268-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="75268-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="75268-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="75268-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="75268-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="75268-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="75268-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75268-120">E_FAIL</span></span>|<span data-ttu-id="75268-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="75268-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="75268-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75268-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="75268-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="75268-124">E_NOTIMPL</span></span>|<span data-ttu-id="75268-125">호스트는의 구현을 제공 하지 않습니다 `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="75268-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75268-126">설명</span><span class="sxs-lookup"><span data-stu-id="75268-126">Remarks</span></span>  
 <span data-ttu-id="75268-127">호스트는 구현, 성능 또는 확장성과 같은 이유로 i/o 요청을 처리 하기 위해 할당할 수 있는 스레드 수에 대 한 배타적 제어를 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75268-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="75268-128">따라서 호스트는를 구현할 필요가 없습니다 `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="75268-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="75268-129">이 경우 호스트는이 메서드에서 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75268-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75268-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75268-130">Requirements</span></span>  
 <span data-ttu-id="75268-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75268-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75268-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="75268-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75268-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75268-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75268-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75268-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75268-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75268-135">See also</span></span>

- [<span data-ttu-id="75268-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75268-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="75268-137">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="75268-137">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="75268-138">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75268-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

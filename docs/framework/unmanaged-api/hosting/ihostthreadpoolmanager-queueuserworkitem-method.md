---
title: IHostThreadPoolManager::QueueUserWorkItem 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
ms.openlocfilehash: 39c35884d0fb53baefafbf86391a349e141418a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141319"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="fde1e-102">IHostThreadPoolManager::QueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="fde1e-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="fde1e-103">실행을 위해 함수를 큐에 대기 시키고 해당 함수에서 사용할 데이터가 포함 된 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="fde1e-104">이 함수는 스레드를 사용할 수 있을 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde1e-105">구문</span><span class="sxs-lookup"><span data-stu-id="fde1e-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fde1e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fde1e-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="fde1e-107">진행 실행할 함수를 나타내는 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="fde1e-108">진행 `Function`에서 사용할 데이터를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="fde1e-109">진행 Win32 `QueueUserWorkItem` 메서드에 대해 정의 된 대로 실행을 제어 하는 플래그 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fde1e-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="fde1e-110">Return Value</span></span>  
  
|<span data-ttu-id="fde1e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fde1e-111">HRESULT</span></span>|<span data-ttu-id="fde1e-112">설명</span><span class="sxs-lookup"><span data-stu-id="fde1e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fde1e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fde1e-113">S_OK</span></span>|<span data-ttu-id="fde1e-114">`QueueUserWorkItem` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="fde1e-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fde1e-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fde1e-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fde1e-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fde1e-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fde1e-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-118">The call timed out.</span></span>|  
|<span data-ttu-id="fde1e-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fde1e-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fde1e-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fde1e-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fde1e-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fde1e-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fde1e-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fde1e-123">E_FAIL</span></span>|<span data-ttu-id="fde1e-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fde1e-125">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fde1e-126">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fde1e-127">주의</span><span class="sxs-lookup"><span data-stu-id="fde1e-127">Remarks</span></span>  
 <span data-ttu-id="fde1e-128">`QueueUserWorkItem` 스레드 풀의 작업자 스레드에 작업 항목을 큐에 대기 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="fde1e-129">해당 시그니처와 매개 변수 형식은 동일한 이름을 가진 해당 Win32 함수의 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="fde1e-130">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fde1e-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde1e-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fde1e-131">Requirements</span></span>  
 <span data-ttu-id="fde1e-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde1e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde1e-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fde1e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fde1e-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde1e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fde1e-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde1e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde1e-136">참조</span><span class="sxs-lookup"><span data-stu-id="fde1e-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="fde1e-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fde1e-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

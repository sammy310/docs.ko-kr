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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c548ae7f8d605ff84da2046d057e436c8e95721
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082116"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="b95cf-102">IHostThreadPoolManager::QueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="b95cf-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="b95cf-103">실행에 대 한 함수에 대기 시키고 해당 함수에서 사용할 데이터가 포함 된 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="b95cf-104">함수는 스레드 사용 가능 해지면를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b95cf-105">구문</span><span class="sxs-lookup"><span data-stu-id="b95cf-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b95cf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b95cf-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="b95cf-107">[in] 실행 하는 함수를 나타내는 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="b95cf-108">[in] 사용할 데이터를 포함 하는 개체 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="b95cf-109">[in] 값 중 하나는 플래그를 Win32에 대해 정의 된 대로 `QueueUserWorkItem` 실행을 제어 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="b95cf-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b95cf-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="b95cf-110">Return Value</span></span>  
  
|<span data-ttu-id="b95cf-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b95cf-111">HRESULT</span></span>|<span data-ttu-id="b95cf-112">설명</span><span class="sxs-lookup"><span data-stu-id="b95cf-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b95cf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b95cf-113">S_OK</span></span>|`QueueUserWorkItem` <span data-ttu-id="b95cf-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-114">returned successfully.</span></span>|  
|<span data-ttu-id="b95cf-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b95cf-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b95cf-116">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b95cf-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b95cf-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b95cf-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-118">The call timed out.</span></span>|  
|<span data-ttu-id="b95cf-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b95cf-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b95cf-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b95cf-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b95cf-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b95cf-122">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b95cf-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b95cf-123">E_FAIL</span></span>|<span data-ttu-id="b95cf-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b95cf-125">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b95cf-126">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b95cf-127">설명</span><span class="sxs-lookup"><span data-stu-id="b95cf-127">Remarks</span></span>  
 `QueueUserWorkItem` <span data-ttu-id="b95cf-128">스레드 풀에서 작업자 스레드가 작업 항목을 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-128">queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="b95cf-129">시그니처 및 매개 변수 형식과을 이름이 같은 해당 Win32 함수를 가지는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b95cf-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="b95cf-130">자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b95cf-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b95cf-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b95cf-131">Requirements</span></span>  
 <span data-ttu-id="b95cf-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b95cf-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b95cf-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b95cf-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b95cf-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b95cf-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b95cf-135">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b95cf-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b95cf-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="b95cf-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="b95cf-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b95cf-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

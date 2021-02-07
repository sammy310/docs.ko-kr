---
description: '자세히 알아보기: IHostThreadPoolManager:: QueueUserWorkItem 메서드'
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
ms.openlocfilehash: edfbf5cfb34473a5fd920307981237fd5deab9aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753785"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="95c4c-103">IHostThreadPoolManager::QueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="95c4c-103">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>

<span data-ttu-id="95c4c-104">실행을 위해 함수를 큐에 대기 시키고 해당 함수에서 사용할 데이터가 포함 된 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-104">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="95c4c-105">이 함수는 스레드를 사용할 수 있을 때 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-105">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c4c-106">구문</span><span class="sxs-lookup"><span data-stu-id="95c4c-106">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95c4c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95c4c-107">Parameters</span></span>  

 `Function`  
 <span data-ttu-id="95c4c-108">진행 실행할 함수를 나타내는 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-108">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="95c4c-109">진행 에서 사용할 데이터를 포함 하는 개체입니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="95c4c-109">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="95c4c-110">진행 Win32 메서드에 대해 정의 된 대로 `QueueUserWorkItem` 실행을 제어 하는 플래그 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-110">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95c4c-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="95c4c-111">Return Value</span></span>  
  
|<span data-ttu-id="95c4c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95c4c-112">HRESULT</span></span>|<span data-ttu-id="95c4c-113">설명</span><span class="sxs-lookup"><span data-stu-id="95c4c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95c4c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="95c4c-114">S_OK</span></span>|<span data-ttu-id="95c4c-115">`QueueUserWorkItem` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-115">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="95c4c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95c4c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95c4c-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95c4c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95c4c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95c4c-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-119">The call timed out.</span></span>|  
|<span data-ttu-id="95c4c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95c4c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95c4c-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95c4c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95c4c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95c4c-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95c4c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95c4c-124">E_FAIL</span></span>|<span data-ttu-id="95c4c-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95c4c-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95c4c-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95c4c-128">설명</span><span class="sxs-lookup"><span data-stu-id="95c4c-128">Remarks</span></span>  

 <span data-ttu-id="95c4c-129">`QueueUserWorkItem` 스레드 풀의 작업자 스레드에 작업 항목을 큐에 대기 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-129">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="95c4c-130">해당 시그니처와 매개 변수 형식은 동일한 이름을 가진 해당 Win32 함수의 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-130">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="95c4c-131">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95c4c-131">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c4c-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95c4c-132">Requirements</span></span>  

 <span data-ttu-id="95c4c-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95c4c-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c4c-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="95c4c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95c4c-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95c4c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95c4c-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c4c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c4c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95c4c-137">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="95c4c-138">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95c4c-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)

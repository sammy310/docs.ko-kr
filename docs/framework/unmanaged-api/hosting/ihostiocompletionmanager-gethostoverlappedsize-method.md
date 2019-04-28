---
title: IHostIoCompletionManager::GetHostOverlappedSize 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4a5661128765cc058417fef6373767d46a4bd7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796905"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="3124e-102">IHostIoCompletionManager::GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="3124e-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="3124e-103">호스트에서 I/O 요청에 추가 하려는 모든 사용자 지정 데이터의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3124e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3124e-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3124e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3124e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="3124e-106">[out] Win32의 크기 외에도 공용 언어 런타임 (CLR)를 할당 해야 하는 바이트 수에 대 한 포인터 `OVERLAPPED` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3124e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3124e-107">Return Value</span></span>  
  
|<span data-ttu-id="3124e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3124e-108">HRESULT</span></span>|<span data-ttu-id="3124e-109">설명</span><span class="sxs-lookup"><span data-stu-id="3124e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3124e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3124e-110">S_OK</span></span>|<span data-ttu-id="3124e-111">`GetHostOverlappedSize` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="3124e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3124e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3124e-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3124e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3124e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3124e-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-115">The call timed out.</span></span>|  
|<span data-ttu-id="3124e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3124e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3124e-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3124e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3124e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3124e-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3124e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3124e-120">E_FAIL</span></span>|<span data-ttu-id="3124e-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3124e-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3124e-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3124e-124">설명</span><span class="sxs-lookup"><span data-stu-id="3124e-124">Remarks</span></span>  
 <span data-ttu-id="3124e-125">Windows 플랫폼 Api에 있는 모든 비동기 I/O 호출 수행 Win32 `OVERLAPPED` 파일 포인터 위치 등의 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="3124e-126">상태를 유지 하려면 일반적으로 비동기 I/O 호출을 수행 하는 응용 프로그램 구조에 사용자 지정 데이터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="3124e-127">`GetHostOverlappedSize` 및 [ihostiocompletionmanager:: Initializehostoverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) 호스트가 이러한 사용자 지정 데이터를 포함 하는 데 사용할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="3124e-128">CLR 호출을 `GetHostOverlappedSize` 호스트를 추가 하는 사용자 지정 데이터의 크기를 결정 하는 메서드는 `OVERLAPPED` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3124e-129">`GetHostOverlappedSize` 한 번만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="3124e-130">호스트의 사용자 지정 데이터에는 모든 I/O 요청에 대해 동일한 크기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3124e-131">크기를 `OVERLAPPED` 개체 자체의 값에 포함 되지 않은 `pcbSize`합니다.</span><span class="sxs-lookup"><span data-stu-id="3124e-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="3124e-132">에 대 한 자세한 내용은 `OVERLAPPED` 구조 (Windows 플랫폼 설명서 참조).</span><span class="sxs-lookup"><span data-stu-id="3124e-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3124e-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3124e-133">Requirements</span></span>  
 <span data-ttu-id="3124e-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3124e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3124e-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3124e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3124e-136">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3124e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3124e-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3124e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3124e-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="3124e-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="3124e-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3124e-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3124e-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3124e-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

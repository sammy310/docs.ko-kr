---
title: IHostIoCompletionManager::InitializeHostOverlapped 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dea19a13cd2c741a24695b293ae1c8621ad5688
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157672"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="8b706-102">IHostIoCompletionManager::InitializeHostOverlapped 메서드</span><span class="sxs-lookup"><span data-stu-id="8b706-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="8b706-103">호스트 Win32에 추가할 사용자 지정 데이터를 초기화할 수 있도록 제공 `OVERLAPPED` 비동기 I/O 요청에 사용 되는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b706-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b706-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b706-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b706-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="8b706-106">[in] Win32에 대 한 포인터 `OVERLAPPED` I/O 요청에 포함 되어야 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b706-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8b706-107">Return Value</span></span>  
  
|<span data-ttu-id="8b706-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b706-108">HRESULT</span></span>|<span data-ttu-id="8b706-109">설명</span><span class="sxs-lookup"><span data-stu-id="8b706-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b706-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b706-110">S_OK</span></span>|<span data-ttu-id="8b706-111">`InitializeHostOverlapped` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="8b706-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b706-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b706-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b706-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b706-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b706-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-115">The call timed out.</span></span>|  
|<span data-ttu-id="8b706-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b706-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b706-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b706-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b706-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b706-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8b706-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b706-120">E_FAIL</span></span>|<span data-ttu-id="8b706-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b706-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b706-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8b706-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8b706-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8b706-125">요청된 된 리소스를 할당할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b706-126">설명</span><span class="sxs-lookup"><span data-stu-id="8b706-126">Remarks</span></span>  
 <span data-ttu-id="8b706-127">Windows 플랫폼을 사용 하 여 함수를 `OVERLAPPED` 비동기 I/O 요청에 대 한 상태를 저장 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="8b706-128">CLR 호출 합니다 `InitializeHostOverlapped` 호스트에 사용자 지정 데이터를 추가할 수 있는 기회를 제공 하는 메서드는 `OVERLAPPED` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8b706-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b706-129">해당 사용자 지정 데이터 블록의 시작 부분에 연결할 호스트 설정 해야 오프셋의 크기를 `OVERLAPPED` 구조 (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="8b706-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="8b706-130">반환 값 e_outofmemory가 호스트에 해당 사용자 지정 데이터를 초기화 하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="8b706-131">이 경우 CLR 오류를 보고 하 고 호출에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b706-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b706-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b706-132">Requirements</span></span>  
 <span data-ttu-id="8b706-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b706-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b706-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b706-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b706-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8b706-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b706-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b706-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b706-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="8b706-137">See also</span></span>

- [<span data-ttu-id="8b706-138">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b706-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="8b706-139">GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="8b706-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="8b706-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b706-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

---
description: '자세히 알아보기: IHostIoCompletionManager:: InitializeHostOverlapped 메서드'
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
ms.openlocfilehash: 10be7edb67143937dec6efc6e35466466374d32d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708465"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="c2835-103">IHostIoCompletionManager::InitializeHostOverlapped 메서드</span><span class="sxs-lookup"><span data-stu-id="c2835-103">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>

<span data-ttu-id="c2835-104">호스트에 `OVERLAPPED` 비동기 i/o 요청에 사용 되는 Win32 구조에 추가할 사용자 지정 데이터를 초기화할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-104">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2835-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2835-105">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2835-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2835-106">Parameters</span></span>  

 `pvOverlapped`  
 <span data-ttu-id="c2835-107">진행 I/o 요청에 포함 될 Win32 구조체에 대 한 포인터 `OVERLAPPED` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-107">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2835-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="c2835-108">Return Value</span></span>  
  
|<span data-ttu-id="c2835-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2835-109">HRESULT</span></span>|<span data-ttu-id="c2835-110">설명</span><span class="sxs-lookup"><span data-stu-id="c2835-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2835-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2835-111">S_OK</span></span>|<span data-ttu-id="c2835-112">`InitializeHostOverlapped` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-112">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="c2835-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2835-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2835-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2835-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2835-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2835-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-116">The call timed out.</span></span>|  
|<span data-ttu-id="c2835-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2835-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2835-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2835-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2835-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2835-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2835-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2835-121">E_FAIL</span></span>|<span data-ttu-id="c2835-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2835-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2835-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c2835-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c2835-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c2835-126">요청한 리소스를 할당 하는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-126">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2835-127">설명</span><span class="sxs-lookup"><span data-stu-id="c2835-127">Remarks</span></span>  

 <span data-ttu-id="c2835-128">Windows 플랫폼 함수는 구조체를 사용 `OVERLAPPED` 하 여 비동기 i/o 요청에 대 한 상태를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-128">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="c2835-129">CLR은 메서드를 호출 `InitializeHostOverlapped` 하 여 호스트에 사용자 지정 데이터를 인스턴스에 추가할 수 있는 기회를 제공 합니다 `OVERLAPPED` .</span><span class="sxs-lookup"><span data-stu-id="c2835-129">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c2835-130">사용자 지정 데이터 블록의 시작 부분을 가져오려면 호스트에서 구조체의 크기 ()로 오프셋을 설정 해야 합니다 `OVERLAPPED` `sizeof(OVERLAPPED)` .</span><span class="sxs-lookup"><span data-stu-id="c2835-130">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="c2835-131">E_OUTOFMEMORY의 반환 값은 호스트가 사용자 지정 데이터를 초기화 하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-131">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="c2835-132">이 경우 CLR은 오류를 보고 하 고 호출에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-132">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2835-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2835-133">Requirements</span></span>  

 <span data-ttu-id="c2835-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2835-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2835-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c2835-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2835-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2835-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2835-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2835-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2835-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2835-138">See also</span></span>

- [<span data-ttu-id="c2835-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2835-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c2835-140">GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="c2835-140">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="c2835-141">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2835-141">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

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
ms.openlocfilehash: 612a5f08982b1db5c940a7cca93166480b21e612
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724860"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="ce68c-102">IHostIoCompletionManager::GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="ce68c-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>

<span data-ttu-id="ce68c-103">호스트가 i/o 요청에 추가 하려는 사용자 지정 데이터의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce68c-104">구문</span><span class="sxs-lookup"><span data-stu-id="ce68c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce68c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce68c-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="ce68c-106">제한이 CLR (공용 언어 런타임)에서 Win32 개체의 크기와 함께 할당 해야 하는 바이트 수에 대 한 포인터입니다 `OVERLAPPED` .</span><span class="sxs-lookup"><span data-stu-id="ce68c-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce68c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ce68c-107">Return Value</span></span>  
  
|<span data-ttu-id="ce68c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce68c-108">HRESULT</span></span>|<span data-ttu-id="ce68c-109">설명</span><span class="sxs-lookup"><span data-stu-id="ce68c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce68c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce68c-110">S_OK</span></span>|<span data-ttu-id="ce68c-111">`GetHostOverlappedSize` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="ce68c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce68c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce68c-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce68c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce68c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce68c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-115">The call timed out.</span></span>|  
|<span data-ttu-id="ce68c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce68c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce68c-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce68c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce68c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce68c-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce68c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce68c-120">E_FAIL</span></span>|<span data-ttu-id="ce68c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce68c-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce68c-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce68c-124">설명</span><span class="sxs-lookup"><span data-stu-id="ce68c-124">Remarks</span></span>  

 <span data-ttu-id="ce68c-125">Windows 플랫폼 Api에 대 한 모든 비동기 i/o 호출은 `OVERLAPPED` 파일 포인터 위치와 같은 정보를 제공 하는 Win32 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="ce68c-126">상태를 유지 하기 위해 비동기 i/o 호출을 수행 하는 응용 프로그램은 일반적으로 사용자 지정 데이터를 구조체에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="ce68c-127">`GetHostOverlappedSize` 및 [IHostIoCompletionManager:: InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md) 는 호스트에 이러한 사용자 지정 데이터를 포함할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="ce68c-128">CLR은 메서드를 호출 `GetHostOverlappedSize` 하 여 호스트가 개체에 추가 하려는 사용자 지정 데이터의 크기를 확인 합니다 `OVERLAPPED` .</span><span class="sxs-lookup"><span data-stu-id="ce68c-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce68c-129">`GetHostOverlappedSize` 는 한 번만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="ce68c-130">호스트의 사용자 지정 데이터는 모든 i/o 요청에 대해 동일한 크기 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ce68c-131">개체 자체의 크기는 `OVERLAPPED` 의 값에 포함 되지 않습니다 `pcbSize` .</span><span class="sxs-lookup"><span data-stu-id="ce68c-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="ce68c-132">구조에 대 한 자세한 내용은 `OVERLAPPED` Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ce68c-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce68c-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce68c-133">Requirements</span></span>  

 <span data-ttu-id="ce68c-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce68c-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce68c-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ce68c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce68c-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce68c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce68c-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce68c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce68c-138">참조</span><span class="sxs-lookup"><span data-stu-id="ce68c-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="ce68c-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce68c-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ce68c-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce68c-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

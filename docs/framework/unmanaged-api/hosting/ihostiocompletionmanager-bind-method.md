---
title: IHostIoCompletionManager::Bind 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
ms.openlocfilehash: 84fc99f6a5feb7ec73ee16942ba2794fc082dc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133907"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="4fe71-102">IHostIoCompletionManager::Bind 메서드</span><span class="sxs-lookup"><span data-stu-id="4fe71-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="4fe71-103">[Createio완성도 포트](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)에 대 한 이전 호출에 의해 만들어진 i/o 완료 포트에 지정 된 핸들을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fe71-104">구문</span><span class="sxs-lookup"><span data-stu-id="4fe71-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fe71-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4fe71-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="4fe71-106">진행 `hHandle`바인딩할 i/o 완료 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="4fe71-107">`hPort`의 값이 null 이면 `hHandle`는 기본 i/o 완료 포트에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="4fe71-108">진행 `hPort`바인딩할 운영 체제 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fe71-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="4fe71-109">Return Value</span></span>  
  
|<span data-ttu-id="4fe71-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4fe71-110">HRESULT</span></span>|<span data-ttu-id="4fe71-111">설명</span><span class="sxs-lookup"><span data-stu-id="4fe71-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4fe71-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4fe71-112">S_OK</span></span>|<span data-ttu-id="4fe71-113">`Bind` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="4fe71-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4fe71-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4fe71-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4fe71-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4fe71-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4fe71-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-117">The call timed out.</span></span>|  
|<span data-ttu-id="4fe71-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4fe71-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4fe71-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4fe71-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4fe71-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4fe71-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4fe71-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4fe71-122">E_FAIL</span></span>|<span data-ttu-id="4fe71-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4fe71-124">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4fe71-125">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fe71-126">주의</span><span class="sxs-lookup"><span data-stu-id="4fe71-126">Remarks</span></span>  
 <span data-ttu-id="4fe71-127">I/o 완료 포트는 `CreateIoCompletionPort`에 대 한 호출을 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="4fe71-128">CLR은 `Bind`를 호출 하 여 해당 포트에 핸들을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4fe71-129">I/o 요청이 완료 되 면 호스트는 [IclrioOnComplete manager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fe71-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4fe71-130">Requirements</span></span>  
 <span data-ttu-id="4fe71-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fe71-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fe71-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4fe71-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fe71-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fe71-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fe71-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fe71-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fe71-135">참조</span><span class="sxs-lookup"><span data-stu-id="4fe71-135">See also</span></span>

- [<span data-ttu-id="4fe71-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fe71-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)

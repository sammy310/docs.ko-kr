---
description: '자세히 알아보기: IHostIoCompletionManager:: Createio Port 메서드'
title: IHostIoCompletionManager::CreateIoCompletionPort 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
ms.openlocfilehash: da4cd595e84c341eb15837ff97f4ba23cac23210
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789439"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="3cbfe-103">IHostIoCompletionManager::CreateIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="3cbfe-103">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>

<span data-ttu-id="3cbfe-104">호스트가 새 i/o 완료 포트를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-104">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbfe-105">구문</span><span class="sxs-lookup"><span data-stu-id="3cbfe-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cbfe-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3cbfe-106">Parameters</span></span>  

 `phPort`  
 <span data-ttu-id="3cbfe-107">제한이 새로 만든 i/o 완료 포트의 핸들에 대 한 포인터 이거나, 포트를 만들 수 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-107">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cbfe-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="3cbfe-108">Return Value</span></span>  
  
|<span data-ttu-id="3cbfe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cbfe-109">HRESULT</span></span>|<span data-ttu-id="3cbfe-110">설명</span><span class="sxs-lookup"><span data-stu-id="3cbfe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cbfe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cbfe-111">S_OK</span></span>|<span data-ttu-id="3cbfe-112">`CreateIoCompletionPort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-112">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="3cbfe-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3cbfe-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3cbfe-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3cbfe-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3cbfe-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3cbfe-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-116">The call timed out.</span></span>|  
|<span data-ttu-id="3cbfe-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3cbfe-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3cbfe-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3cbfe-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3cbfe-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3cbfe-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3cbfe-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3cbfe-121">E_FAIL</span></span>|<span data-ttu-id="3cbfe-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3cbfe-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3cbfe-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3cbfe-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3cbfe-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3cbfe-126">요청한 리소스를 할당 하는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-126">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cbfe-127">설명</span><span class="sxs-lookup"><span data-stu-id="3cbfe-127">Remarks</span></span>  

 <span data-ttu-id="3cbfe-128">CLR은 메서드를 호출 `CreateIoCompletionPort` 하 여 호스트가 새 i/o 완료 포트를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-128">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="3cbfe-129">[IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 i/o 작업을이 포트에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-129">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="3cbfe-130">호스트는 [IclrioOnComplete manager::](iclriocompletionmanager-oncomplete-method.md)를 호출 하 여 CLR에 상태를 다시 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-130">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cbfe-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3cbfe-131">Requirements</span></span>  

 <span data-ttu-id="3cbfe-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cbfe-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3cbfe-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cbfe-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cbfe-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbfe-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbfe-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cbfe-136">See also</span></span>

- [<span data-ttu-id="3cbfe-137">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3cbfe-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3cbfe-138">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3cbfe-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

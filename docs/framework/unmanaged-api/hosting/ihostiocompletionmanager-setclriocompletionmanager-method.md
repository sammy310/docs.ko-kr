---
description: '자세히 알아보기: IHostIoCompletionManager:: Setclrio Manager 메서드'
title: IHostIoCompletionManager::SetCLRIoCompletionManager 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
ms.openlocfilehash: 1075c33d6de4f5edf34364d67cbc0a21c4f19802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708296"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="0b265-103">IHostIoCompletionManager::SetCLRIoCompletionManager 메서드</span><span class="sxs-lookup"><span data-stu-id="0b265-103">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>

<span data-ttu-id="0b265-104">호스트에 CLR (공용 언어 런타임)에 의해 구현 된 [Iclriocompletionmanager](iclriocompletionmanager-interface.md) 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-104">Provides the host with an interface pointer to the [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b265-105">구문</span><span class="sxs-lookup"><span data-stu-id="0b265-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b265-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b265-106">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="0b265-107">진행 CLR에서 제공 하는 인스턴스에 대 한 인터페이스 포인터 `ICLRIoCompletionManager` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-107">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b265-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="0b265-108">Return Value</span></span>  
  
|<span data-ttu-id="0b265-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b265-109">HRESULT</span></span>|<span data-ttu-id="0b265-110">설명</span><span class="sxs-lookup"><span data-stu-id="0b265-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b265-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b265-111">S_OK</span></span>|<span data-ttu-id="0b265-112">`SetCLRIoCompletionManager` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-112">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="0b265-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b265-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b265-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b265-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b265-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b265-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-116">The call timed out.</span></span>|  
|<span data-ttu-id="0b265-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b265-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b265-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b265-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b265-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b265-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b265-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b265-121">E_FAIL</span></span>|<span data-ttu-id="0b265-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b265-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b265-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b265-125">설명</span><span class="sxs-lookup"><span data-stu-id="0b265-125">Remarks</span></span>  

 <span data-ttu-id="0b265-126">CLR이 호출 된 후에 `SetCLRIoCompletionManager` 호스트는 [IclrioOnComplete manager::](iclriocompletionmanager-oncomplete-method.md) 를 호출 하 여 i/o 요청이 완료 되었을 때 clr에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-126">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b265-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b265-127">Requirements</span></span>  

 <span data-ttu-id="0b265-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b265-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b265-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0b265-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b265-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b265-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b265-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b265-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b265-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b265-132">See also</span></span>

- [<span data-ttu-id="0b265-133">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b265-133">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0b265-134">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b265-134">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

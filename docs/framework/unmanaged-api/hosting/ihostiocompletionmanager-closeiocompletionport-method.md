---
description: '자세히 알아보기: IHostIoCompletionManager:: Closeio Port 메서드'
title: IHostIoCompletionManager::CloseIoCompletionPort 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
ms.openlocfilehash: 987b9f4e0fa22fa977fa1b14c77c8c0381e3e399
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728511"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="678aa-103">IHostIoCompletionManager::CloseIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="678aa-103">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>

<span data-ttu-id="678aa-104">호스트에서 [Createio이상 포트](ihostiocompletionmanager-createiocompletionport-method.md)에 대 한 이전 호출을 통해 열린 포트를 닫도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-104">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="678aa-105">구문</span><span class="sxs-lookup"><span data-stu-id="678aa-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="678aa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="678aa-106">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="678aa-107">진행 닫을 포트의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-107">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="678aa-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="678aa-108">Return Value</span></span>  
  
|<span data-ttu-id="678aa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="678aa-109">HRESULT</span></span>|<span data-ttu-id="678aa-110">설명</span><span class="sxs-lookup"><span data-stu-id="678aa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="678aa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="678aa-111">S_OK</span></span>|<span data-ttu-id="678aa-112">`CloseIoCompletionPort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-112">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="678aa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="678aa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="678aa-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="678aa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="678aa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="678aa-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-116">The call timed out.</span></span>|  
|<span data-ttu-id="678aa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="678aa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="678aa-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="678aa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="678aa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="678aa-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="678aa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="678aa-121">E_FAIL</span></span>|<span data-ttu-id="678aa-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="678aa-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="678aa-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="678aa-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="678aa-125">E_INVALIDARG</span></span>|<span data-ttu-id="678aa-126">잘못 된 포트 핸들이 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-126">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="678aa-127">설명</span><span class="sxs-lookup"><span data-stu-id="678aa-127">Remarks</span></span>  

 <span data-ttu-id="678aa-128">`hPort` 는에 대 한 이전 호출에 의해 생성 된 포트에 대 한 핸들 이어야 합니다 `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="678aa-128">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="678aa-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="678aa-129">Requirements</span></span>  

 <span data-ttu-id="678aa-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="678aa-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="678aa-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="678aa-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="678aa-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="678aa-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="678aa-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="678aa-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678aa-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="678aa-134">See also</span></span>

- [<span data-ttu-id="678aa-135">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="678aa-135">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="678aa-136">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="678aa-136">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)

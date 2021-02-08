---
description: '자세히 알아보기: ICLRDebugManager:: IsDebuggerAttached 메서드'
title: ICLRDebugManager::IsDebuggerAttached 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: 74305989797bcb553feb727a133e24bd308ac715
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772135"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="1364e-103">ICLRDebugManager::IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="1364e-103">ICLRDebugManager::IsDebuggerAttached Method</span></span>

<span data-ttu-id="1364e-104">디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-104">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1364e-105">구문</span><span class="sxs-lookup"><span data-stu-id="1364e-105">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1364e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1364e-106">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="1364e-107">[out] `true` 디버거가 프로세스에 연결 되어 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-107">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1364e-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="1364e-108">Return Value</span></span>  
  
|<span data-ttu-id="1364e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1364e-109">HRESULT</span></span>|<span data-ttu-id="1364e-110">설명</span><span class="sxs-lookup"><span data-stu-id="1364e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1364e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1364e-111">S_OK</span></span>|<span data-ttu-id="1364e-112">`IsDebuggerAttached` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-112">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="1364e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1364e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1364e-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1364e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1364e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1364e-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-116">The call timed out.</span></span>|  
|<span data-ttu-id="1364e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1364e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1364e-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1364e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1364e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1364e-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1364e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1364e-121">E_FAIL</span></span>|<span data-ttu-id="1364e-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1364e-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1364e-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1364e-125">설명</span><span class="sxs-lookup"><span data-stu-id="1364e-125">Remarks</span></span>  

 <span data-ttu-id="1364e-126">`IsDebuggerAttached` 호스트가 CLR을 쿼리하여 디버거가 프로세스에 연결 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-126">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1364e-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1364e-127">Requirements</span></span>  

 <span data-ttu-id="1364e-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1364e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1364e-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1364e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1364e-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1364e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1364e-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1364e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1364e-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1364e-132">See also</span></span>

- [<span data-ttu-id="1364e-133">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1364e-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="1364e-134">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1364e-134">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="1364e-135">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1364e-135">IHostControl Interface</span></span>](ihostcontrol-interface.md)

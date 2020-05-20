---
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
ms.openlocfilehash: a21391f52a27e7f7a3abe533499c6b2581ec4a73
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615755"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="eaea2-102">ICLRDebugManager::IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="eaea2-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="eaea2-103">디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaea2-104">구문</span><span class="sxs-lookup"><span data-stu-id="eaea2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaea2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eaea2-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="eaea2-106">[out] `true` 디버거가 프로세스에 연결 되어 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eaea2-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="eaea2-107">Return Value</span></span>  
  
|<span data-ttu-id="eaea2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eaea2-108">HRESULT</span></span>|<span data-ttu-id="eaea2-109">설명</span><span class="sxs-lookup"><span data-stu-id="eaea2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eaea2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eaea2-110">S_OK</span></span>|<span data-ttu-id="eaea2-111">`IsDebuggerAttached`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="eaea2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eaea2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eaea2-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eaea2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eaea2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eaea2-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-115">The call timed out.</span></span>|  
|<span data-ttu-id="eaea2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eaea2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eaea2-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eaea2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eaea2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eaea2-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eaea2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eaea2-120">E_FAIL</span></span>|<span data-ttu-id="eaea2-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eaea2-122">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eaea2-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaea2-124">설명</span><span class="sxs-lookup"><span data-stu-id="eaea2-124">Remarks</span></span>  
 <span data-ttu-id="eaea2-125">`IsDebuggerAttached`호스트가 CLR을 쿼리하여 디버거가 프로세스에 연결 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaea2-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eaea2-126">Requirements</span></span>  
 <span data-ttu-id="eaea2-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eaea2-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaea2-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eaea2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eaea2-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaea2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eaea2-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaea2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaea2-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaea2-131">See also</span></span>

- [<span data-ttu-id="eaea2-132">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eaea2-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="eaea2-133">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eaea2-133">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="eaea2-134">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eaea2-134">IHostControl Interface</span></span>](ihostcontrol-interface.md)

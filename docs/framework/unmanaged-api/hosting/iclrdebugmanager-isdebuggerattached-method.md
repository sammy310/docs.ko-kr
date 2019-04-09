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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d6c071b3ac68cb38fc85aff65fff49a71ea4275
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095389"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="56c21-102">ICLRDebugManager::IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="56c21-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="56c21-103">디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56c21-104">구문</span><span class="sxs-lookup"><span data-stu-id="56c21-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56c21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56c21-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="56c21-106">[out] `true` 디버거 고, 그렇지 않으면 프로세스에 연결 된 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56c21-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="56c21-107">Return Value</span></span>  
  
|<span data-ttu-id="56c21-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56c21-108">HRESULT</span></span>|<span data-ttu-id="56c21-109">설명</span><span class="sxs-lookup"><span data-stu-id="56c21-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56c21-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="56c21-110">S_OK</span></span>|`IsDebuggerAttached` <span data-ttu-id="56c21-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-111">returned successfully.</span></span>|  
|<span data-ttu-id="56c21-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56c21-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56c21-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="56c21-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="56c21-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="56c21-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-115">The call timed out.</span></span>|  
|<span data-ttu-id="56c21-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="56c21-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="56c21-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="56c21-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="56c21-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="56c21-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="56c21-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56c21-120">E_FAIL</span></span>|<span data-ttu-id="56c21-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56c21-122">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="56c21-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56c21-124">설명</span><span class="sxs-lookup"><span data-stu-id="56c21-124">Remarks</span></span>  
 `IsDebuggerAttached` <span data-ttu-id="56c21-125">호스트 프로세스에 디버거가 연결 되어 있는지 여부를 확인 하려면 CLR 쿼리를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="56c21-125">allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56c21-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56c21-126">Requirements</span></span>  
 <span data-ttu-id="56c21-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="56c21-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56c21-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56c21-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56c21-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="56c21-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="56c21-130">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="56c21-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56c21-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="56c21-131">See also</span></span>

- [<span data-ttu-id="56c21-132">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56c21-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="56c21-133">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56c21-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="56c21-134">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56c21-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)

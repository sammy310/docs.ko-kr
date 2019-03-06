---
title: IHostSecurityContext::Capture 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92b593248a7a196247a5b4c71a90cd8944665bbe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485280"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="c3384-102">IHostSecurityContext::Capture 메서드</span><span class="sxs-lookup"><span data-stu-id="c3384-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="c3384-103">복제본을 가져옵니다 합니다 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 호출에서 반환 되는 인스턴스 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3384-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3384-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3384-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3384-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="c3384-106">[out] 복제본 주소에 대 한 포인터를 `IHostSecurityContext` 캡처할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3384-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3384-107">Return Value</span></span>  
  
|<span data-ttu-id="c3384-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3384-108">HRESULT</span></span>|<span data-ttu-id="c3384-109">설명</span><span class="sxs-lookup"><span data-stu-id="c3384-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3384-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3384-110">S_OK</span></span>|<span data-ttu-id="c3384-111">`Capture` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="c3384-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3384-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3384-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3384-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3384-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3384-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-115">The call timed out.</span></span>|  
|<span data-ttu-id="c3384-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3384-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3384-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3384-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3384-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3384-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3384-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3384-120">E_FAIL</span></span>|<span data-ttu-id="c3384-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3384-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3384-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3384-124">설명</span><span class="sxs-lookup"><span data-stu-id="c3384-124">Remarks</span></span>  
 <span data-ttu-id="c3384-125">반환 된 인터페이스 포인터를 `Capture` 캡처된 컨텍스트를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="c3384-126">이 정보는 비동기 코드 지점에서 이동 될 때 호출 된 기준이 포인터의 수명을 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="c3384-127">따라서 원래 포인터를 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3384-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3384-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3384-128">Requirements</span></span>  
 <span data-ttu-id="c3384-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3384-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3384-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3384-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3384-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c3384-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3384-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3384-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3384-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3384-133">See also</span></span>
- [<span data-ttu-id="c3384-134">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3384-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c3384-135">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3384-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)

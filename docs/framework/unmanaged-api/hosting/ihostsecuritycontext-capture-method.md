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
ms.openlocfilehash: e1df31ed8b652837a33b360b1378f99e6800cbea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501523"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="4cade-102">IHostSecurityContext::Capture 메서드</span><span class="sxs-lookup"><span data-stu-id="4cade-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="4cade-103">[IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)에 대 한 호출에서 반환 된 [IHostSecurityContext](ihostsecuritycontext-interface.md) 인스턴스의 복제본을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-103">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cade-104">구문</span><span class="sxs-lookup"><span data-stu-id="4cade-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cade-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cade-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="4cade-106">제한이 캡처할 개체의 복제본 주소에 대 한 포인터 `IHostSecurityContext` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cade-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="4cade-107">Return Value</span></span>  
  
|<span data-ttu-id="4cade-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cade-108">HRESULT</span></span>|<span data-ttu-id="4cade-109">설명</span><span class="sxs-lookup"><span data-stu-id="4cade-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cade-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cade-110">S_OK</span></span>|<span data-ttu-id="4cade-111">`Capture`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="4cade-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cade-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cade-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cade-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cade-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cade-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-115">The call timed out.</span></span>|  
|<span data-ttu-id="4cade-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cade-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cade-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cade-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cade-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cade-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cade-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cade-120">E_FAIL</span></span>|<span data-ttu-id="4cade-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cade-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cade-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cade-124">설명</span><span class="sxs-lookup"><span data-stu-id="4cade-124">Remarks</span></span>  
 <span data-ttu-id="4cade-125">에서 반환 된 인터페이스 포인터는 `Capture` 캡처된 컨텍스트의 복제본입니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="4cade-126">비동기 코드 지점에서이 정보를 이동 하는 경우이 정보는 호출이 수행 된 포인터의 수명과 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="4cade-127">따라서 원래 포인터를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cade-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cade-128">Requirements</span></span>  
 <span data-ttu-id="4cade-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cade-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cade-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4cade-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cade-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cade-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cade-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cade-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cade-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cade-133">See also</span></span>

- [<span data-ttu-id="4cade-134">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cade-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4cade-135">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cade-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)

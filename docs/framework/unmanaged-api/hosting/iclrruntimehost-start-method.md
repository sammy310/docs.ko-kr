---
title: ICLRRuntimeHost::Start 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
ms.openlocfilehash: a599e754202309a2b61d1761150f3f570fd0dc76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120417"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="7d9cb-102">ICLRRuntimeHost::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="7d9cb-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="7d9cb-103">CLR (공용 언어 런타임)을 프로세스로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d9cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d9cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7d9cb-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d9cb-105">Return Value</span></span>  
  
|<span data-ttu-id="7d9cb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d9cb-106">HRESULT</span></span>|<span data-ttu-id="7d9cb-107">설명</span><span class="sxs-lookup"><span data-stu-id="7d9cb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d9cb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d9cb-108">S_OK</span></span>|<span data-ttu-id="7d9cb-109">`Start` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="7d9cb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d9cb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d9cb-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d9cb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d9cb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d9cb-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-113">The call timed out.</span></span>|  
|<span data-ttu-id="7d9cb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d9cb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d9cb-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d9cb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d9cb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d9cb-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d9cb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d9cb-118">E_FAIL</span></span>|<span data-ttu-id="7d9cb-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d9cb-120">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d9cb-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d9cb-122">주의</span><span class="sxs-lookup"><span data-stu-id="7d9cb-122">Remarks</span></span>  
 <span data-ttu-id="7d9cb-123">대부분의 시나리오에서는 관리 코드를 실행 하는 첫 번째 요청 시 런타임이 자동으로 초기화 되기 때문에 `Start`를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="7d9cb-124">그러나 `Start`를 사용 하 여 런타임을 초기화 해야 하는 시기를 정확 하 게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d9cb-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d9cb-125">Requirements</span></span>  
 <span data-ttu-id="7d9cb-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d9cb-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7d9cb-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d9cb-128">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9cb-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d9cb-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d9cb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d9cb-130">참조</span><span class="sxs-lookup"><span data-stu-id="7d9cb-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="7d9cb-131">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d9cb-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)

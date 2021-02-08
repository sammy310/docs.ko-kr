---
description: '자세히 알아보기: ICLRRuntimeHost:: Start 메서드'
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
ms.openlocfilehash: 0ada729c9a90b23fb1573a2101845028e5e2fe76
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785083"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="5f467-103">ICLRRuntimeHost::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="5f467-103">ICLRRuntimeHost::Start Method</span></span>

<span data-ttu-id="5f467-104">CLR (공용 언어 런타임)을 프로세스로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-104">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f467-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f467-105">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5f467-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="5f467-106">Return Value</span></span>  
  
|<span data-ttu-id="5f467-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f467-107">HRESULT</span></span>|<span data-ttu-id="5f467-108">설명</span><span class="sxs-lookup"><span data-stu-id="5f467-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f467-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f467-109">S_OK</span></span>|<span data-ttu-id="5f467-110">`Start` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-110">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="5f467-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f467-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f467-112">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f467-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f467-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f467-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-114">The call timed out.</span></span>|  
|<span data-ttu-id="5f467-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f467-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f467-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f467-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f467-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f467-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f467-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f467-119">E_FAIL</span></span>|<span data-ttu-id="5f467-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f467-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-121">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f467-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f467-123">설명</span><span class="sxs-lookup"><span data-stu-id="5f467-123">Remarks</span></span>  

 <span data-ttu-id="5f467-124">대부분의 시나리오에서는 `Start` 런타임이 관리 코드를 실행 하는 첫 번째 요청 시 자동으로 초기화 되기 때문에를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-124">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="5f467-125">그러나를 사용 `Start` 하 여 런타임을 초기화 해야 하는 시기를 정확 하 게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-125">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f467-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f467-126">Requirements</span></span>  

 <span data-ttu-id="5f467-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f467-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f467-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5f467-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f467-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f467-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f467-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f467-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f467-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f467-131">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="5f467-132">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f467-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)

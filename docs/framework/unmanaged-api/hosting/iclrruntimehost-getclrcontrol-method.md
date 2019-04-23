---
title: ICLRRuntimeHost::GetCLRControl 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83b029c24321946f777966daa7a486f9e8e7b7a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073150"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="d2299-102">ICLRRuntimeHost::GetCLRControl 메서드</span><span class="sxs-lookup"><span data-stu-id="d2299-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="d2299-103">형식의 인터페이스 포인터를 가져옵니다 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 호스트의 CLR (공용 언어 런타임)의 측면을 사용자 지정 하는 데 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2299-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2299-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2299-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2299-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="d2299-106">[out] 형식의 인터페이스 포인터 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) CLR의 추가 측면을 구성 하는 호스트 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2299-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d2299-107">Return Value</span></span>  
  
|<span data-ttu-id="d2299-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2299-108">HRESULT</span></span>|<span data-ttu-id="d2299-109">설명</span><span class="sxs-lookup"><span data-stu-id="d2299-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2299-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2299-110">S_OK</span></span>|<span data-ttu-id="d2299-111">`GetCLRControl` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="d2299-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d2299-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d2299-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d2299-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d2299-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d2299-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-115">The call timed out.</span></span>|  
|<span data-ttu-id="d2299-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d2299-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d2299-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d2299-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d2299-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d2299-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d2299-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d2299-120">E_FAIL</span></span>|<span data-ttu-id="d2299-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d2299-122">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d2299-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d2299-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="d2299-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="d2299-125">CLR 이미 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2299-126">설명</span><span class="sxs-lookup"><span data-stu-id="d2299-126">Remarks</span></span>  
 <span data-ttu-id="d2299-127">`ICLRControl` 제공 된 [GetCLRManager 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드를 통해 관리자 형식 중 하나에 대 한 인터페이스 포인터를 가져오려면 호스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2299-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2299-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2299-128">Requirements</span></span>  
 <span data-ttu-id="d2299-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2299-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2299-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2299-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2299-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d2299-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2299-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2299-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2299-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2299-133">See also</span></span>

- [<span data-ttu-id="d2299-134">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2299-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d2299-135">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2299-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)

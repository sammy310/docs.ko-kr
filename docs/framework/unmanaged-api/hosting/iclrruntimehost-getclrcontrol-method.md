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
ms.openlocfilehash: 478e07f18d40043de4e800c36647ac4a32499635
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120426"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="b60d7-102">ICLRRuntimeHost::GetCLRControl 메서드</span><span class="sxs-lookup"><span data-stu-id="b60d7-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="b60d7-103">에서 CLR (공용 언어 런타임)의 측면을 사용자 지정 하는 데 사용할 수 있는 [ICLRControl interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="b60d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b60d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b60d7-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="b60d7-106">제한이 호스트가 CLR의 추가 측면을 구성할 수 있도록 하는 [ICLRControl interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 형식의 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b60d7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="b60d7-107">Return Value</span></span>  
  
|<span data-ttu-id="b60d7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b60d7-108">HRESULT</span></span>|<span data-ttu-id="b60d7-109">설명</span><span class="sxs-lookup"><span data-stu-id="b60d7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b60d7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b60d7-110">S_OK</span></span>|<span data-ttu-id="b60d7-111">`GetCLRControl` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="b60d7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b60d7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b60d7-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b60d7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b60d7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b60d7-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-115">The call timed out.</span></span>|  
|<span data-ttu-id="b60d7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b60d7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b60d7-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b60d7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b60d7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b60d7-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b60d7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b60d7-120">E_FAIL</span></span>|<span data-ttu-id="b60d7-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b60d7-122">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b60d7-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b60d7-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="b60d7-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="b60d7-125">CLR이 이미 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b60d7-126">주의</span><span class="sxs-lookup"><span data-stu-id="b60d7-126">Remarks</span></span>  
 <span data-ttu-id="b60d7-127">`ICLRControl`는 호스트에서 관리자 형식 중 하나에 대 한 인터페이스 포인터를 가져올 수 있도록 하는 [Getclrmanager 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b60d7-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b60d7-128">Requirements</span></span>  
 <span data-ttu-id="b60d7-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b60d7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b60d7-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b60d7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b60d7-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b60d7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b60d7-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b60d7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60d7-133">참조</span><span class="sxs-lookup"><span data-stu-id="b60d7-133">See also</span></span>

- [<span data-ttu-id="b60d7-134">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b60d7-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b60d7-135">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b60d7-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)

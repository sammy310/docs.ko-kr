---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab00ccd85481f1c6d37e1132e0ecab5e0e86be90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768882"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="d668f-102">ICLRPolicyManager::SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="d668f-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="d668f-103">처리 되지 않은 예외가 발생 하는 경우는 CLR (공용 언어 런타임)의 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d668f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d668f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d668f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d668f-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="d668f-106">[in] 중 하나는 [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) CLR 또는 호스트 동작 설정 되었는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d668f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d668f-107">Return Value</span></span>  
  
|<span data-ttu-id="d668f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d668f-108">HRESULT</span></span>|<span data-ttu-id="d668f-109">설명</span><span class="sxs-lookup"><span data-stu-id="d668f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d668f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d668f-110">S_OK</span></span>|<span data-ttu-id="d668f-111">`SetUnhandledExceptionPolicy` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="d668f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d668f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d668f-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d668f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d668f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d668f-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-115">The call timed out.</span></span>|  
|<span data-ttu-id="d668f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d668f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d668f-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d668f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d668f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d668f-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d668f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d668f-120">E_FAIL</span></span>|<span data-ttu-id="d668f-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d668f-122">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d668f-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d668f-124">설명</span><span class="sxs-lookup"><span data-stu-id="d668f-124">Remarks</span></span>  
 <span data-ttu-id="d668f-125">기본적으로 CLR은 처리 되지 않은 모든 예외에 대 한 최종 처리기 및 기본 동작은 해당 프로세스를 종료 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="d668f-126">호스트 설정 하 여이 동작을 변경할 수는 `policy` eHostDeterminedPolicy 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="d668f-127">이 값을 CLR의 이전 버전과 마찬가지로 자체 기본 동작을 구현 하는 호스트를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d668f-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d668f-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d668f-128">Requirements</span></span>  
 <span data-ttu-id="d668f-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d668f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d668f-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d668f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d668f-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d668f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d668f-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d668f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d668f-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="d668f-133">See also</span></span>

- [<span data-ttu-id="d668f-134">EClrUnhandledException 열거형</span><span class="sxs-lookup"><span data-stu-id="d668f-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="d668f-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d668f-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d668f-136">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d668f-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="d668f-137">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d668f-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)

---
description: '자세히 알아보기: IHostPolicyManager:: OnFailure 메서드'
title: IHostPolicyManager::OnFailure 메서드
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
ms.openlocfilehash: 9fb359d4ba1b1b89e029a0772a0f67a49b2b380b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671843"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="8dc1a-103">IHostPolicyManager::OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="8dc1a-103">IHostPolicyManager::OnFailure Method</span></span>

<span data-ttu-id="8dc1a-104">리소스 할당 또는 재사용 실패에 대 한 응답으로 CLR (공용 언어 런타임)이 [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) 메서드 호출에 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-104">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc1a-105">구문</span><span class="sxs-lookup"><span data-stu-id="8dc1a-105">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dc1a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8dc1a-106">Parameters</span></span>  

 `failure`  
 <span data-ttu-id="8dc1a-107">진행 CLR이 응답 하는 오류 종류를 나타내는 [EClrFailure](eclrfailure-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-107">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="8dc1a-108">진행 CLR이 응답 하는 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나 `failure` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dc1a-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="8dc1a-109">Return Value</span></span>  
  
|<span data-ttu-id="8dc1a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8dc1a-110">HRESULT</span></span>|<span data-ttu-id="8dc1a-111">설명</span><span class="sxs-lookup"><span data-stu-id="8dc1a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8dc1a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8dc1a-112">S_OK</span></span>|<span data-ttu-id="8dc1a-113">`OnFailure` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-113">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="8dc1a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8dc1a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8dc1a-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8dc1a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8dc1a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8dc1a-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-117">The call timed out.</span></span>|  
|<span data-ttu-id="8dc1a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8dc1a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8dc1a-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8dc1a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8dc1a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8dc1a-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8dc1a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8dc1a-122">E_FAIL</span></span>|<span data-ttu-id="8dc1a-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8dc1a-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8dc1a-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8dc1a-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8dc1a-126">Requirements</span></span>  

 <span data-ttu-id="8dc1a-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc1a-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8dc1a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8dc1a-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc1a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dc1a-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc1a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc1a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dc1a-131">See also</span></span>

- [<span data-ttu-id="8dc1a-132">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="8dc1a-132">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="8dc1a-133">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="8dc1a-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="8dc1a-134">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8dc1a-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="8dc1a-135">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8dc1a-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)

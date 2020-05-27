---
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
ms.openlocfilehash: 8ad4943aa9bf1b66b34bcd83a5422a977b16518d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804225"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="671e1-102">IHostPolicyManager::OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="671e1-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="671e1-103">리소스 할당 또는 재사용 실패에 대 한 응답으로 CLR (공용 언어 런타임)이 [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) 메서드 호출에 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="671e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="671e1-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="671e1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="671e1-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="671e1-106">진행 CLR이 응답 하는 오류 종류를 나타내는 [EClrFailure](eclrfailure-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="671e1-107">진행 CLR이 응답 하는 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나 `failure` 입니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="671e1-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="671e1-108">Return Value</span></span>  
  
|<span data-ttu-id="671e1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="671e1-109">HRESULT</span></span>|<span data-ttu-id="671e1-110">Description</span><span class="sxs-lookup"><span data-stu-id="671e1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="671e1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="671e1-111">S_OK</span></span>|<span data-ttu-id="671e1-112">`OnFailure`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="671e1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="671e1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="671e1-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="671e1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="671e1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="671e1-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-116">The call timed out.</span></span>|  
|<span data-ttu-id="671e1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="671e1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="671e1-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="671e1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="671e1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="671e1-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="671e1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="671e1-121">E_FAIL</span></span>|<span data-ttu-id="671e1-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="671e1-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="671e1-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="671e1-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="671e1-125">Requirements</span></span>  
 <span data-ttu-id="671e1-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="671e1-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="671e1-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="671e1-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="671e1-128">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="671e1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="671e1-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="671e1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671e1-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="671e1-130">See also</span></span>

- [<span data-ttu-id="671e1-131">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="671e1-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="671e1-132">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="671e1-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="671e1-133">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="671e1-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="671e1-134">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="671e1-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)

---
title: IHostPolicyManager::OnTimeout 메서드
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: e3f2dc7ff9beaf417184f3d09db76e611982118a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690670"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="d9fa0-102">IHostPolicyManager::OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="d9fa0-102">IHostPolicyManager::OnTimeout Method</span></span>

<span data-ttu-id="d9fa0-103">시간 제한에 대 한 응답으로 CLR (공용 언어 런타임)이 [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) 메서드 호출에 지정 된 작업을 수행 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fa0-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9fa0-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9fa0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9fa0-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="d9fa0-106">진행 시간 초과 된 작업의 종류를 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="d9fa0-107">진행 CLR이 제한 시간에 대 한 응답으로 수행 하는 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9fa0-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d9fa0-108">Return Value</span></span>  
  
|<span data-ttu-id="d9fa0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9fa0-109">HRESULT</span></span>|<span data-ttu-id="d9fa0-110">설명</span><span class="sxs-lookup"><span data-stu-id="d9fa0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9fa0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9fa0-111">S_OK</span></span>|<span data-ttu-id="d9fa0-112">`OnTimeout` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="d9fa0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9fa0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9fa0-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9fa0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9fa0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9fa0-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-116">The call timed out.</span></span>|  
|<span data-ttu-id="d9fa0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9fa0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9fa0-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9fa0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9fa0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9fa0-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9fa0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9fa0-121">E_FAIL</span></span>|<span data-ttu-id="d9fa0-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9fa0-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9fa0-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9fa0-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9fa0-125">Requirements</span></span>  

 <span data-ttu-id="d9fa0-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9fa0-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d9fa0-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9fa0-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa0-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9fa0-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9fa0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fa0-130">참조</span><span class="sxs-lookup"><span data-stu-id="d9fa0-130">See also</span></span>

- [<span data-ttu-id="d9fa0-131">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="d9fa0-131">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="d9fa0-132">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="d9fa0-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="d9fa0-133">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9fa0-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="d9fa0-134">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9fa0-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)

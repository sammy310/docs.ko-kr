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
ms.openlocfilehash: 1088374c9df18ded38b44384be44de245f0bd403
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728955"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="9f75c-102">ICLRPolicyManager::SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="9f75c-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>

<span data-ttu-id="9f75c-103">처리 되지 않은 예외가 발생할 때 CLR (공용 언어 런타임)의 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f75c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f75c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f75c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9f75c-105">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="9f75c-106">진행 동작이 CLR 또는 호스트에 의해 설정 되는지 여부를 나타내는 [EClrUnhandledException](eclrunhandledexception-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-106">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f75c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9f75c-107">Return Value</span></span>  
  
|<span data-ttu-id="9f75c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f75c-108">HRESULT</span></span>|<span data-ttu-id="9f75c-109">설명</span><span class="sxs-lookup"><span data-stu-id="9f75c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f75c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f75c-110">S_OK</span></span>|<span data-ttu-id="9f75c-111">`SetUnhandledExceptionPolicy` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="9f75c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f75c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f75c-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f75c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f75c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f75c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-115">The call timed out.</span></span>|  
|<span data-ttu-id="9f75c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f75c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f75c-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f75c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f75c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f75c-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f75c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f75c-120">E_FAIL</span></span>|<span data-ttu-id="9f75c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f75c-122">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f75c-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f75c-124">설명</span><span class="sxs-lookup"><span data-stu-id="9f75c-124">Remarks</span></span>  

 <span data-ttu-id="9f75c-125">기본적으로 CLR은 처리 되지 않은 모든 예외에 대 한 최종 처리기 이며 기본 동작은 프로세스를 중단 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="9f75c-126">호스트는 값을 eHostDeterminedPolicy로 설정 하 여이 동작을 변경할 수 있습니다 `policy` .</span><span class="sxs-lookup"><span data-stu-id="9f75c-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="9f75c-127">이 값을 사용 하면 호스트에서 이전 버전의 CLR과 마찬가지로 자체 기본 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f75c-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f75c-128">Requirements</span></span>  

 <span data-ttu-id="9f75c-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f75c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f75c-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9f75c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f75c-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f75c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f75c-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f75c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f75c-133">참조</span><span class="sxs-lookup"><span data-stu-id="9f75c-133">See also</span></span>

- [<span data-ttu-id="9f75c-134">EClrUnhandledException 열거형</span><span class="sxs-lookup"><span data-stu-id="9f75c-134">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="9f75c-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f75c-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="9f75c-136">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f75c-136">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="9f75c-137">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f75c-137">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)

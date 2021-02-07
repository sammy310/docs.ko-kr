---
description: '자세히 알아보기: ICLRPolicyManager:: SetUnhandledExceptionPolicy 메서드'
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
ms.openlocfilehash: 489127bb00b2b65466460baa3cfd31439672cd1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716551"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="75e2c-103">ICLRPolicyManager::SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="75e2c-103">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>

<span data-ttu-id="75e2c-104">처리 되지 않은 예외가 발생할 때 CLR (공용 언어 런타임)의 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-104">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e2c-105">구문</span><span class="sxs-lookup"><span data-stu-id="75e2c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75e2c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75e2c-106">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="75e2c-107">진행 동작이 CLR 또는 호스트에 의해 설정 되는지 여부를 나타내는 [EClrUnhandledException](eclrunhandledexception-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-107">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75e2c-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="75e2c-108">Return Value</span></span>  
  
|<span data-ttu-id="75e2c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75e2c-109">HRESULT</span></span>|<span data-ttu-id="75e2c-110">설명</span><span class="sxs-lookup"><span data-stu-id="75e2c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75e2c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="75e2c-111">S_OK</span></span>|<span data-ttu-id="75e2c-112">`SetUnhandledExceptionPolicy` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-112">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="75e2c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="75e2c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="75e2c-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="75e2c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="75e2c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="75e2c-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-116">The call timed out.</span></span>|  
|<span data-ttu-id="75e2c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="75e2c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="75e2c-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="75e2c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="75e2c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="75e2c-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="75e2c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75e2c-121">E_FAIL</span></span>|<span data-ttu-id="75e2c-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="75e2c-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="75e2c-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75e2c-125">설명</span><span class="sxs-lookup"><span data-stu-id="75e2c-125">Remarks</span></span>  

 <span data-ttu-id="75e2c-126">기본적으로 CLR은 처리 되지 않은 모든 예외에 대 한 최종 처리기 이며 기본 동작은 프로세스를 중단 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-126">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="75e2c-127">호스트는 값을 eHostDeterminedPolicy로 설정 하 여이 동작을 변경할 수 있습니다 `policy` .</span><span class="sxs-lookup"><span data-stu-id="75e2c-127">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="75e2c-128">이 값을 사용 하면 호스트에서 이전 버전의 CLR과 마찬가지로 자체 기본 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-128">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e2c-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75e2c-129">Requirements</span></span>  

 <span data-ttu-id="75e2c-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75e2c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e2c-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="75e2c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75e2c-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e2c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75e2c-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e2c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e2c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75e2c-134">See also</span></span>

- [<span data-ttu-id="75e2c-135">EClrUnhandledException 열거형</span><span class="sxs-lookup"><span data-stu-id="75e2c-135">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="75e2c-136">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75e2c-136">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="75e2c-137">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75e2c-137">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="75e2c-138">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75e2c-138">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)

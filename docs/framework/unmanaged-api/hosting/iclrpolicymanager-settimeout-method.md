---
description: '자세히 알아보기: ICLRPolicyManager:: SetTimeout 메서드'
title: ICLRPolicyManager::SetTimeout 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: 5fb65e93cc6eea7826498ff6b03147773f06e0b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781898"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="d3ca5-103">ICLRPolicyManager::SetTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="d3ca5-103">ICLRPolicyManager::SetTimeout Method</span></span>

<span data-ttu-id="d3ca5-104">지정 된 작업에 대 한 시간 제한 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-104">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ca5-105">구문</span><span class="sxs-lookup"><span data-stu-id="d3ca5-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3ca5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3ca5-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="d3ca5-107">진행 시간 제한을 설정할 CLR (공용 언어 런타임) 작업을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="d3ca5-108">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="d3ca5-109">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d3ca5-109">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="d3ca5-110">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d3ca5-110">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="d3ca5-111">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d3ca5-111">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="d3ca5-112">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d3ca5-112">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="d3ca5-113">진행 새 시간 제한 값 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-113">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="d3ca5-114">값이 INFINITE 이면 작업이 시간 초과 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-114">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3ca5-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="d3ca5-115">Return Value</span></span>  
  
|<span data-ttu-id="d3ca5-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3ca5-116">HRESULT</span></span>|<span data-ttu-id="d3ca5-117">설명</span><span class="sxs-lookup"><span data-stu-id="d3ca5-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3ca5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3ca5-118">S_OK</span></span>|<span data-ttu-id="d3ca5-119">`SetTimeout` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-119">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="d3ca5-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3ca5-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3ca5-121">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3ca5-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3ca5-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3ca5-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-123">The call timed out.</span></span>|  
|<span data-ttu-id="d3ca5-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3ca5-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3ca5-125">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3ca5-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3ca5-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3ca5-127">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3ca5-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3ca5-128">E_FAIL</span></span>|<span data-ttu-id="d3ca5-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3ca5-130">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3ca5-131">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d3ca5-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d3ca5-132">E_INVALIDARG</span></span>|<span data-ttu-id="d3ca5-133">지정 된에 대 한 제한 시간을 설정할 수 `operation` 없거나에 잘못 된 값이 제공 `operation` 된 경우</span><span class="sxs-lookup"><span data-stu-id="d3ca5-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3ca5-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3ca5-134">Requirements</span></span>  

 <span data-ttu-id="d3ca5-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ca5-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d3ca5-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3ca5-137">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca5-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3ca5-138">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ca5-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ca5-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3ca5-139">See also</span></span>

- [<span data-ttu-id="d3ca5-140">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="d3ca5-140">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="d3ca5-141">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3ca5-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="d3ca5-142">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3ca5-142">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)

---
description: '자세히 알아보기: IHostPolicyManager:: OnDefaultAction 메서드'
title: IHostPolicyManager::OnDefaultAction 메서드
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: ea474734f7bc0a5210c5aecf605452909b261a87
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671925"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="53a43-103">IHostPolicyManager::OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="53a43-103">IHostPolicyManager::OnDefaultAction Method</span></span>

<span data-ttu-id="53a43-104">CLR (공용 언어 런타임)이 스레드 abort 또는 unload에 대 한 응답으로 [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) 메서드 호출에 의해 설정 된 기본 작업을 수행 하려고 함을 호스트에 알립니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="53a43-104">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a43-105">구문</span><span class="sxs-lookup"><span data-stu-id="53a43-105">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53a43-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="53a43-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="53a43-107">진행 CLR이 응답 하는 이벤트의 종류를 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="53a43-108">진행 CLR이 이벤트에 대 한 응답으로 수행 하는 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53a43-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="53a43-109">Return Value</span></span>  
  
|<span data-ttu-id="53a43-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53a43-110">HRESULT</span></span>|<span data-ttu-id="53a43-111">설명</span><span class="sxs-lookup"><span data-stu-id="53a43-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53a43-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="53a43-112">S_OK</span></span>|<span data-ttu-id="53a43-113">`OnDefaultAction` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-113">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="53a43-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53a43-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53a43-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="53a43-116">성공할</span><span class="sxs-lookup"><span data-stu-id="53a43-116">successfully</span></span>|  
|<span data-ttu-id="53a43-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53a43-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53a43-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-118">The call timed out.</span></span>|  
|<span data-ttu-id="53a43-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53a43-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53a43-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53a43-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53a43-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53a43-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53a43-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53a43-123">E_FAIL</span></span>|<span data-ttu-id="53a43-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53a43-125">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53a43-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53a43-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53a43-127">Requirements</span></span>  

 <span data-ttu-id="53a43-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53a43-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a43-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="53a43-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53a43-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a43-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53a43-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a43-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a43-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53a43-132">See also</span></span>

- [<span data-ttu-id="53a43-133">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="53a43-133">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="53a43-134">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="53a43-134">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="53a43-135">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53a43-135">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="53a43-136">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53a43-136">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)

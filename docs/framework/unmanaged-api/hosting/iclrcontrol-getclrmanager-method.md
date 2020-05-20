---
title: ICLRControl::GetCLRManager 메서드
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: 04cb45cd021532b6cb3d74a195cbd62e1ab8d31d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615854"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="6fbf3-102">ICLRControl::GetCLRManager 메서드</span><span class="sxs-lookup"><span data-stu-id="6fbf3-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="6fbf3-103">호스트가 CLR (공용 언어 런타임)을 구성 하는 데 사용할 수 있는 관리자 형식의 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fbf3-104">구문</span><span class="sxs-lookup"><span data-stu-id="6fbf3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fbf3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6fbf3-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="6fbf3-106">진행 `IID`반환할 관리자 형식의입니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="6fbf3-107">`IID`지원 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="6fbf3-108">IID_ICLRDebugManager:를 `ppObject` [ICLRDebugManager](iclrdebugmanager-interface.md)형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6fbf3-109">IID_ICLRErrorReportingManager:를 `ppObject` [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6fbf3-110">IID_ICLRGCManager:를 `ppObject` [ICLRGCManager](iclrgcmanager-interface.md)형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6fbf3-111">IID_ICLRHostProtectionManager:를 `ppObject` [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6fbf3-112">IID_ICLROnEventManager:를 `ppObject` [ICLROnEventManager](iclroneventmanager-interface.md)형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6fbf3-113">IID_ICLRPolicyManager:를 `ppObject` [ICLRPolicyManager](iclrpolicymanager-interface.md)형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="6fbf3-114">IID_ICLRTaskManager:를 `ppObject` [ICLRTaskManager](iclrtaskmanager-interface.md)형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="6fbf3-115">제한이 요청 된 관리자에 대 한 인터페이스 포인터 이거나, 잘못 된 관리자 형식이 요청 된 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fbf3-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="6fbf3-116">Return Value</span></span>  
  
|<span data-ttu-id="6fbf3-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fbf3-117">HRESULT</span></span>|<span data-ttu-id="6fbf3-118">설명</span><span class="sxs-lookup"><span data-stu-id="6fbf3-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fbf3-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fbf3-119">S_OK</span></span>|<span data-ttu-id="6fbf3-120">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="6fbf3-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6fbf3-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6fbf3-122">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6fbf3-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6fbf3-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6fbf3-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-124">The call timed out.</span></span>|  
|<span data-ttu-id="6fbf3-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6fbf3-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6fbf3-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6fbf3-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6fbf3-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6fbf3-128">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6fbf3-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6fbf3-129">E_FAIL</span></span>|<span data-ttu-id="6fbf3-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6fbf3-131">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6fbf3-132">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6fbf3-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="6fbf3-133">E_NOINTERFACE</span></span>|<span data-ttu-id="6fbf3-134">인터페이스 유형이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fbf3-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fbf3-135">Requirements</span></span>  
 <span data-ttu-id="6fbf3-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fbf3-137">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6fbf3-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fbf3-138">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fbf3-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fbf3-139">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fbf3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fbf3-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fbf3-140">See also</span></span>

- [<span data-ttu-id="6fbf3-141">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fbf3-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="6fbf3-142">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fbf3-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)

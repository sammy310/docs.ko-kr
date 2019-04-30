---
title: IHostControl::SetAppDomainManager 메서드
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118e75cb28a4e474427f35f4516ec41850ebe99f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967715"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="df37b-102">IHostControl::SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="df37b-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="df37b-103">응용 프로그램 도메인이 만들어졌는지 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df37b-104">구문</span><span class="sxs-lookup"><span data-stu-id="df37b-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df37b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df37b-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="df37b-106">[in] 선택 된 숫자 식별자 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="df37b-107">[in] 에 대 한 포인터를 <xref:System.AppDomainManager> 로 호스트를 구현 하는 개체 `IUnknown`합니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df37b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="df37b-108">Return Value</span></span>  
  
|<span data-ttu-id="df37b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df37b-109">HRESULT</span></span>|<span data-ttu-id="df37b-110">설명</span><span class="sxs-lookup"><span data-stu-id="df37b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df37b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="df37b-111">S_OK</span></span>|<span data-ttu-id="df37b-112">`SetAppDomainManager` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="df37b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df37b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df37b-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df37b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df37b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df37b-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-116">The call timed out.</span></span>|  
|<span data-ttu-id="df37b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df37b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df37b-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df37b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df37b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df37b-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df37b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df37b-121">E_FAIL</span></span>|<span data-ttu-id="df37b-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df37b-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df37b-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df37b-125">설명</span><span class="sxs-lookup"><span data-stu-id="df37b-125">Remarks</span></span>  
 <span data-ttu-id="df37b-126">합니다 <xref:System.AppDomainManager> 관리 코드를 부트스트랩 하 고 만들기 및 각 설정을 제어 하는 메커니즘을 사용 하 여 호스트 제공 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="df37b-127">합니다 <xref:System.AppDomainManager> 각각에 로드 됩니다 <xref:System.AppDomain> 경우는 <xref:System.AppDomain> 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="df37b-128">CLR 호스트를 응용 프로그램 도메인의 값을 설정 하 여 만들어졌는지에 알립니다, 선택 하는 경우는 `pUnkAppDomainManager` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="df37b-129">구현에는 `SetAppDomainManager` 메서드를 호스트 수 설정 된 어셈블리 이름 및 형식을 응용 프로그램 도메인 관리자에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="df37b-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df37b-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df37b-130">Requirements</span></span>  
 <span data-ttu-id="df37b-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="df37b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df37b-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df37b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df37b-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="df37b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df37b-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df37b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df37b-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="df37b-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="df37b-136">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df37b-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)

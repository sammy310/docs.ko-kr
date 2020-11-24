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
ms.openlocfilehash: 2f4c004db39c14e7a71b0caa55a6089e8f69ca3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680661"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="5059e-102">IHostControl::SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="5059e-102">IHostControl::SetAppDomainManager Method</span></span>

<span data-ttu-id="5059e-103">응용 프로그램 도메인이 생성 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5059e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5059e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5059e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5059e-105">Parameters</span></span>  

 `dwAppDomainID`  
 <span data-ttu-id="5059e-106">진행 선택한의 숫자 식별자입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="5059e-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="5059e-107">진행 <xref:System.AppDomainManager> 호스트가 구현 하는 개체에 대 한 포인터 `IUnknown` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5059e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5059e-108">Return Value</span></span>  
  
|<span data-ttu-id="5059e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5059e-109">HRESULT</span></span>|<span data-ttu-id="5059e-110">설명</span><span class="sxs-lookup"><span data-stu-id="5059e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5059e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5059e-111">S_OK</span></span>|<span data-ttu-id="5059e-112">`SetAppDomainManager` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="5059e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5059e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5059e-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5059e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5059e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5059e-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-116">The call timed out.</span></span>|  
|<span data-ttu-id="5059e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5059e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5059e-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5059e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5059e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5059e-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5059e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5059e-121">E_FAIL</span></span>|<span data-ttu-id="5059e-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5059e-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5059e-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5059e-125">설명</span><span class="sxs-lookup"><span data-stu-id="5059e-125">Remarks</span></span>  

 <span data-ttu-id="5059e-126">는 <xref:System.AppDomainManager> 관리 코드를 부트스트랩 하 고 각각의 생성 및 설정을 제어 하는 메커니즘을 호스트에 제공 합니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="5059e-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="5059e-127">는 <xref:System.AppDomainManager> 만들어질 때 각각에 로드 됩니다 <xref:System.AppDomain> <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="5059e-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="5059e-128">선택 하는 경우 CLR은 매개 변수 값을 설정 하 여 응용 프로그램 도메인이 생성 되었음을 호스트에 알립니다 `pUnkAppDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="5059e-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="5059e-129">메서드를 구현 `SetAppDomainManager` 하는 경우 호스트는 응용 프로그램 도메인 관리자에 대 한 어셈블리 이름 및 유형을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5059e-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5059e-130">Requirements</span></span>  

 <span data-ttu-id="5059e-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5059e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5059e-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5059e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5059e-133">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5059e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5059e-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5059e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5059e-135">참조</span><span class="sxs-lookup"><span data-stu-id="5059e-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="5059e-136">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5059e-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)

---
title: ICLRHostProtectionManager::SetProtectedCategories 메서드
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141044"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="7f5cb-102">ICLRHostProtectionManager::SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="7f5cb-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="7f5cb-103">부분적으로 신뢰할 수 있는 코드에서 실행이 차단 되는 관리 되는 형식 및 멤버의 범주를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f5cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f5cb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f5cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f5cb-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="7f5cb-106">진행 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 해야 하는 관리 되는 형식 및 멤버의 범주를 나타내는 [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f5cb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7f5cb-107">Return Value</span></span>  
  
|<span data-ttu-id="7f5cb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f5cb-108">HRESULT</span></span>|<span data-ttu-id="7f5cb-109">설명</span><span class="sxs-lookup"><span data-stu-id="7f5cb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f5cb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f5cb-110">S_OK</span></span>|<span data-ttu-id="7f5cb-111">`SetProtectedCategories` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="7f5cb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7f5cb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7f5cb-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7f5cb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7f5cb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7f5cb-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-115">The call timed out.</span></span>|  
|<span data-ttu-id="7f5cb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7f5cb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7f5cb-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7f5cb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7f5cb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7f5cb-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7f5cb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f5cb-120">E_FAIL</span></span>|<span data-ttu-id="7f5cb-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7f5cb-122">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7f5cb-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f5cb-124">주의</span><span class="sxs-lookup"><span data-stu-id="7f5cb-124">Remarks</span></span>  
 <span data-ttu-id="7f5cb-125">각 `EApiCategories` 값은 관리 되는 형식 및 멤버 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="7f5cb-126">`EApiCategories` 열거형 및 `SetProtectedCategories` 메서드는 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute> 클래스와 직접 관련 되며, `EApiCategories`에서 설명 하는 범주에 해당 하는 기능을 노출 하는 관리 되는 형식 및 멤버를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="7f5cb-127">자세한 내용은 <xref:System.Security.Permissions.HostProtectionAttribute> 및 <xref:System.Security.Permissions.HostProtectionResource> 열거형 (`EApiCategories`에 직접 해당)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f5cb-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f5cb-128">Requirements</span></span>  
 <span data-ttu-id="7f5cb-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f5cb-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7f5cb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f5cb-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5cb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f5cb-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f5cb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f5cb-133">참조</span><span class="sxs-lookup"><span data-stu-id="7f5cb-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="7f5cb-134">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="7f5cb-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="7f5cb-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f5cb-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7f5cb-136">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f5cb-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)

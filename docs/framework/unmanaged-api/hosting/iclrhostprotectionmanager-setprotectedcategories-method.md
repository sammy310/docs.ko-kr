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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63b6e85b6abe20e9e1f0b00648a06a31735e63c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944640"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="bb553-102">ICLRHostProtectionManager::SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="bb553-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="bb553-103">관리 되는 형식 및 멤버의 범주에서 부분적으로 신뢰할 수 있는 코드 실행에서 차단 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb553-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb553-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb553-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb553-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="bb553-106">[in] 조합을 [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) 값을 나타내는 관리 되는 형식 및 멤버의 범주에서 부분적으로 신뢰할 수 있는 코드 실행에서 차단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb553-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="bb553-107">Return Value</span></span>  
  
|<span data-ttu-id="bb553-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb553-108">HRESULT</span></span>|<span data-ttu-id="bb553-109">설명</span><span class="sxs-lookup"><span data-stu-id="bb553-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb553-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb553-110">S_OK</span></span>|<span data-ttu-id="bb553-111">`SetProtectedCategories` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="bb553-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bb553-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bb553-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bb553-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bb553-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bb553-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-115">The call timed out.</span></span>|  
|<span data-ttu-id="bb553-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bb553-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bb553-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bb553-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bb553-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bb553-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bb553-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb553-120">E_FAIL</span></span>|<span data-ttu-id="bb553-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bb553-122">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bb553-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb553-124">설명</span><span class="sxs-lookup"><span data-stu-id="bb553-124">Remarks</span></span>  
 <span data-ttu-id="bb553-125">각 `EApiCategories` 값은 관리 되는 형식 및 멤버의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="bb553-126">`EApiCategories` 열거형 및 `SetProtectedCategories` 메서드는 직접 관련 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute> 에 설명 된 범주에 해당 하는 기능을 제공 하는 관리 되는 형식 및 멤버를 표시 하는 데 사용 되는 클래스 `EApiCategories`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="bb553-127">자세한 내용은 <xref:System.Security.Permissions.HostProtectionAttribute> 하며 <xref:System.Security.Permissions.HostProtectionResource> 직접 해당 하는 열거형 `EApiCategories`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb553-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb553-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb553-128">Requirements</span></span>  
 <span data-ttu-id="bb553-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb553-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb553-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bb553-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb553-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bb553-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb553-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb553-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb553-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="bb553-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="bb553-134">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="bb553-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="bb553-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb553-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="bb553-136">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb553-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)

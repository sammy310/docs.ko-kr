---
description: '자세히 알아보기: ICLRHostProtectionManager:: SetProtectedCategories 메서드'
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
ms.openlocfilehash: 9138c31ea1a2d9b7ebeaeac8ef5ef9305eabef8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637536"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="4cc0b-103">ICLRHostProtectionManager::SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="4cc0b-103">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>

<span data-ttu-id="4cc0b-104">부분적으로 신뢰할 수 있는 코드에서 실행이 차단 되는 관리 되는 형식 및 멤버의 범주를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-104">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc0b-105">구문</span><span class="sxs-lookup"><span data-stu-id="4cc0b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cc0b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cc0b-106">Parameters</span></span>  

 `categories`  
 <span data-ttu-id="4cc0b-107">진행 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 해야 하는 관리 되는 형식 및 멤버의 범주를 나타내는 [EApiCategories](eapicategories-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-107">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cc0b-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="4cc0b-108">Return Value</span></span>  
  
|<span data-ttu-id="4cc0b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cc0b-109">HRESULT</span></span>|<span data-ttu-id="4cc0b-110">설명</span><span class="sxs-lookup"><span data-stu-id="4cc0b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cc0b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cc0b-111">S_OK</span></span>|<span data-ttu-id="4cc0b-112">`SetProtectedCategories` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-112">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="4cc0b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cc0b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cc0b-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cc0b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cc0b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cc0b-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-116">The call timed out.</span></span>|  
|<span data-ttu-id="4cc0b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cc0b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cc0b-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cc0b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cc0b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cc0b-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cc0b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cc0b-121">E_FAIL</span></span>|<span data-ttu-id="4cc0b-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cc0b-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cc0b-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cc0b-125">설명</span><span class="sxs-lookup"><span data-stu-id="4cc0b-125">Remarks</span></span>  

 <span data-ttu-id="4cc0b-126">각 `EApiCategories` 값은 관리 되는 형식 및 멤버 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-126">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="4cc0b-127">열거형 및 메서드는 관리 되는 `EApiCategories` `SetProtectedCategories` 클래스와 직접 관련 되어 있으며 <xref:System.Security.Permissions.HostProtectionAttribute> ,이 클래스는에서 설명 하는 범주에 해당 하는 기능을 노출 하는 관리 되는 형식과 멤버를 표시 하는 데 사용 됩니다 `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="4cc0b-127">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="4cc0b-128">자세한 내용은 <xref:System.Security.Permissions.HostProtectionAttribute> 및 <xref:System.Security.Permissions.HostProtectionResource> 에 직접 해당 하는 열거형을 참조 하세요 `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="4cc0b-128">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc0b-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cc0b-129">Requirements</span></span>  

 <span data-ttu-id="4cc0b-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc0b-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4cc0b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cc0b-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc0b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cc0b-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc0b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc0b-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cc0b-134">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="4cc0b-135">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="4cc0b-135">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="4cc0b-136">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cc0b-136">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="4cc0b-137">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cc0b-137">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)

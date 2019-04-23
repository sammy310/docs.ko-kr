---
title: EApiCategories 열거형
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3debd3f13d78841188dd8c900f51c0110e1d4c67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086457"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="58502-102">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="58502-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="58502-103">부분적으로 신뢰할 수 있는 코드에서 실행 되는 호스트를 차단할 수 있는 기능의 범주를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58502-104">구문</span><span class="sxs-lookup"><span data-stu-id="58502-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="58502-105">멤버</span><span class="sxs-lookup"><span data-stu-id="58502-105">Members</span></span>  
  
|<span data-ttu-id="58502-106">멤버</span><span class="sxs-lookup"><span data-stu-id="58502-106">Member</span></span>|<span data-ttu-id="58502-107">설명</span><span class="sxs-lookup"><span data-stu-id="58502-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="58502-108">관리 되는 모든 클래스 및 기타 적용 되는 멤버 지정 `EApiCategories` 필드에서 부분적으로 신뢰할 수 있는 코드 실행에서 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="58502-109">관리 되는 클래스 및 멤버를 생성, 조작 및 외부 프로세스의 소멸을 사용 하면 부분적으로 신뢰할 수 있는 코드에서 실행 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="58502-110">관리 되는 클래스 및 멤버를 생성, 조작 및 외부 스레드 소멸을 사용 하면 부분적으로 신뢰할 수 있는 코드에서 실행 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="58502-111">부분적으로 신뢰할 수 있는 코드에서 실행 중단 시 메모리 누수가 발생할 수 있는 관리 되는 형식 및 멤버는 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="58502-112">관리 코드 범주가 수 부분적으로 신뢰할 수 있는 코드에서 실행 되는 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="58502-113">공용 언어 런타임 (CLR) 보안 인프라에서 부분적으로 신뢰할 수 있는 코드에서 사용 하 고 차단를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="58502-114">관리 되는 클래스 및 멤버 호스팅된 프로세스 영향을 줄 수 있는 기능이 부분적으로 신뢰할 수 있는 코드에서 실행 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="58502-115">관리 되는 클래스 및 멤버 호스트 프로세스의 스레드 영향을 줄 수 있는 기능이 부분적으로 신뢰할 수 있는 코드에서 실행 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="58502-116">공유 상태를 노출 하는 관리 되는 클래스와 멤버 부분적으로 신뢰할 수 있는 코드에서 실행 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="58502-117">공용 언어 런타임 클래스 및 멤버를 잠금을 유지 하기 위해 사용자 코드를 사용 하면 부분적으로 신뢰할 수 있는 코드에서 실행 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="58502-118">관리 되는 클래스 및 멤버 허용 하거나 사용자 상호 작용을 필요로 하는 부분적으로 신뢰할 수 있는 코드에서 실행 차단 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58502-119">설명</span><span class="sxs-lookup"><span data-stu-id="58502-119">Remarks</span></span>  
 <span data-ttu-id="58502-120">합니다 [iclrhostprotectionmanager:: Setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) 형식의 매개 변수를 사용 하는 메서드 `EApiCategories`합니다.</span><span class="sxs-lookup"><span data-stu-id="58502-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="58502-121">`EApiCategories` 열거형 및 `SetProtectedCategories` 메서드 직접적으로 관련 된 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> 클래스.</span><span class="sxs-lookup"><span data-stu-id="58502-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="58502-122">관리 되는 클래스를 사용 합니다 <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> 열거형 값에 직접적으로 해당 합니다 `EApiCategories` 에 설명 된 범주에 해당 하는 기능을 제공 하는 관리 되는 형식 및 멤버를 표시 하려면 값을 `EApiCategories`입니다.</span><span class="sxs-lookup"><span data-stu-id="58502-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58502-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58502-123">Requirements</span></span>  
 <span data-ttu-id="58502-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58502-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58502-125">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58502-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58502-126">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58502-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58502-127">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58502-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58502-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="58502-128">See also</span></span>

- [<span data-ttu-id="58502-129">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58502-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="58502-130">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="58502-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

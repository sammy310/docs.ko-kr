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
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131207"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="d9173-102">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="d9173-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="d9173-103">호스트에서 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 차단할 수 있는 기능의 범주를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9173-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9173-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="d9173-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d9173-105">Members</span></span>  
  
|<span data-ttu-id="d9173-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d9173-106">Member</span></span>|<span data-ttu-id="d9173-107">설명</span><span class="sxs-lookup"><span data-stu-id="d9173-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="d9173-108">다른 `EApiCategories` 필드가 적용 되는 모든 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="d9173-109">외부 프로세스의 생성, 조작 및 소멸을 허용 하는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="d9173-110">외부 스레드의 생성, 조작 및 소멸을 허용 하는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="d9173-111">중단 시 메모리 누수가 발생할 수 있는 관리 되는 형식 및 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="d9173-112">관리 코드 범주가 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="d9173-113">부분적으로 신뢰할 수 있는 코드에서 CLR (공용 언어 런타임) 보안 인프라를 사용 하지 못하도록 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="d9173-114">기능이 호스팅된 프로세스에 영향을 줄 수 있는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="d9173-115">기능이 호스팅된 프로세스의 스레드에 영향을 줄 수 있는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="d9173-116">공유 상태를 노출 하는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="d9173-117">사용자 코드에서 잠금을 유지할 수 있도록 하는 공용 언어 런타임 클래스 및 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="d9173-118">사용자 상호 작용을 허용 하거나 필요로 하는 관리 되는 클래스 및 멤버를 부분적으로 신뢰할 수 있는 코드에서 실행 하지 못하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9173-119">주의</span><span class="sxs-lookup"><span data-stu-id="d9173-119">Remarks</span></span>  
 <span data-ttu-id="d9173-120">[ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) 메서드는 `EApiCategories`형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="d9173-121">`EApiCategories` 열거형 및 `SetProtectedCategories` 메서드는 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> 클래스와 직접 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="d9173-122">관리 되는 클래스는 <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> 열거형과 함께 사용 됩니다. 값은 `EApiCategories` 값에 직접 해당 하므로 `EApiCategories`에서 설명 하는 범주에 해당 하는 기능을 노출 하는 관리 되는 형식 및 멤버를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9173-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9173-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9173-123">Requirements</span></span>  
 <span data-ttu-id="d9173-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9173-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9173-125">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d9173-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9173-126">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d9173-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9173-127">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9173-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9173-128">참조</span><span class="sxs-lookup"><span data-stu-id="d9173-128">See also</span></span>

- [<span data-ttu-id="d9173-129">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9173-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="d9173-130">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="d9173-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

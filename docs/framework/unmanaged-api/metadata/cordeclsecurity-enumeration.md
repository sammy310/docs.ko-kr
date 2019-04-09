---
title: CorDeclSecurity 열거형
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5409d1b89ba3e50c4ae17ed5aa6bf063cf6c93cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136970"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="4a9e6-102">CorDeclSecurity 열거형</span><span class="sxs-lookup"><span data-stu-id="4a9e6-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="4a9e6-103">선언적 보안을 사용하여 수행할 수 있는 보안 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a9e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a9e6-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="4a9e6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4a9e6-105">Members</span></span>  
  
|<span data-ttu-id="4a9e6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4a9e6-106">Member</span></span>|<span data-ttu-id="4a9e6-107">설명</span><span class="sxs-lookup"><span data-stu-id="4a9e6-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="4a9e6-108">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="4a9e6-109">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="4a9e6-110">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="4a9e6-111">호출 스택의 상위에 있는 모든 호출자에게 현재 사용 권한 개체가 지정한 사용 권한이 부여되었어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="4a9e6-112">스택의 상위 호출자가 리소스에 액세스할 권한이 하는 경우에 호출 코드에서 현재 사용 권한 개체로 식별 되는 리소스를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="4a9e6-113">현재 권한 개체에 의해 지정 된 리소스에 액세스할 수 있도록 권한이 부여 된 액세스 권한이 있는 경우에 호출자에 게 액세스가 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="4a9e6-114">코드에 다른 리소스에 액세스할 수 있는 권한이 부여되더라도 이 권한 개체가 지정한 리소스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="4a9e6-115">직접 실행 호출자는 지정 된 기간에 대 한 지정 된 권한을 부여 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="4a9e6-116">다른 클래스를 상속 하거나 메서드를 재정의 하는 파생된 클래스는 지정 된 권한을 부여 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="4a9e6-117">호출자가 코드를 실행 하는 데 필요한 최소 사용 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="4a9e6-118">이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="4a9e6-119">호출자는 선택 사항 (실행 하려면 필요 없음)는 추가 사용 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="4a9e6-120">이 요청은 특별히 요청되지 않은 다른 모든 사용 권한을 암시적으로 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="4a9e6-121">이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="4a9e6-122">호출자의 요청을 잘못 사용 될 수 있는 권한이 부여 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="4a9e6-123">이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="4a9e6-124">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="4a9e6-125">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="4a9e6-126">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="4a9e6-127">직접 실행 호출자에게 지정된 사용 권한이 부여되었어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="4a9e6-128">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="4a9e6-129">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="4a9e6-130">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="4a9e6-131">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="4a9e6-132">예약됨.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a9e6-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a9e6-133">Requirements</span></span>  
 <span data-ttu-id="4a9e6-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a9e6-135">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4a9e6-135">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="4a9e6-136">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="4a9e6-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a9e6-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a9e6-137">See also</span></span>

- [<span data-ttu-id="4a9e6-138">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="4a9e6-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

---
description: '자세한 정보: EBindPolicyLevels 열거형'
title: EBindPolicyLevels 열거형
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
ms.openlocfilehash: 00e10cff79cdd782e8d9ab8e9b7e1e3f388fb1ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785616"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="39f85-103">EBindPolicyLevels 열거형</span><span class="sxs-lookup"><span data-stu-id="39f85-103">EBindPolicyLevels Enumeration</span></span>

<span data-ttu-id="39f85-104">어셈블리 정책을 적용 하거나 수정할 수준을 지정 하는 플래그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-104">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f85-105">구문</span><span class="sxs-lookup"><span data-stu-id="39f85-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="39f85-106">구성원</span><span class="sxs-lookup"><span data-stu-id="39f85-106">Members</span></span>  
  
|<span data-ttu-id="39f85-107">멤버</span><span class="sxs-lookup"><span data-stu-id="39f85-107">Member</span></span>|<span data-ttu-id="39f85-108">설명</span><span class="sxs-lookup"><span data-stu-id="39f85-108">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="39f85-109">정책을 관리자 수준에서 적용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-109">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="39f85-110">응용 프로그램 수준에서 정책을 적용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-110">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="39f85-111">정책을 호스트 수준에서 적용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-111">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="39f85-112">정책 수준 플래그를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-112">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="39f85-113">정책을 게시자 수준에서 적용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-113">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="39f85-114">정책을 변수 수준에서 적용할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-114">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="39f85-115">정책이 .NET Framework 어셈블리 구현 간의 이식성을 지원 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-115">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="39f85-116">[\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md)구성 파일 요소를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39f85-116">See the [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="39f85-117">정책을 CLR (공용 언어 런타임)과 통합 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-117">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39f85-118">설명</span><span class="sxs-lookup"><span data-stu-id="39f85-118">Remarks</span></span>  

 <span data-ttu-id="39f85-119">이 열거형은 응용 프로그램 정책에서 변경 내용을 지정 하기 위해 [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) 인터페이스의 메서드에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39f85-119">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39f85-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39f85-120">Requirements</span></span>  

 <span data-ttu-id="39f85-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39f85-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f85-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="39f85-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39f85-123">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39f85-123">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39f85-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39f85-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f85-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39f85-125">See also</span></span>

- [<span data-ttu-id="39f85-126">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39f85-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="39f85-127">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="39f85-127">Hosting Enumerations</span></span>](hosting-enumerations.md)

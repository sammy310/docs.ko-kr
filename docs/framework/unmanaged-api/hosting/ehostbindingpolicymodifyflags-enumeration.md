---
title: EHostBindingPolicyModifyFlags 열거형
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129442"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="84870-102">EHostBindingPolicyModifyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="84870-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="84870-103">호스트에서 소스 어셈블리의 정책 수정을 대상 어셈블리에 적용할 때 CLR (공용 언어 런타임)이 수행 해야 하는 리디렉션 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84870-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84870-104">구문</span><span class="sxs-lookup"><span data-stu-id="84870-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="84870-105">멤버</span><span class="sxs-lookup"><span data-stu-id="84870-105">Members</span></span>  
  
|<span data-ttu-id="84870-106">멤버</span><span class="sxs-lookup"><span data-stu-id="84870-106">Member</span></span>|<span data-ttu-id="84870-107">설명</span><span class="sxs-lookup"><span data-stu-id="84870-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="84870-108">CLR이 소스 어셈블리의 정책 값을 대상 어셈블리의 정책 값에 연결 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84870-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="84870-109">CLR에서 기본 작업을 수행 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84870-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="84870-110">CLR이 대상 어셈블리의 정책 값을 최대 값으로 설정 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84870-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="84870-111">CLR이 대상 어셈블리의 정책 값을 소스 어셈블리의 정책 값으로 바꾸도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84870-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84870-112">주의</span><span class="sxs-lookup"><span data-stu-id="84870-112">Remarks</span></span>  
 <span data-ttu-id="84870-113">[ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) 메서드는 `EHostBindingPolicyModifyFlags`형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84870-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84870-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84870-114">Requirements</span></span>  
 <span data-ttu-id="84870-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84870-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84870-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="84870-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84870-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="84870-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84870-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84870-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84870-119">참조</span><span class="sxs-lookup"><span data-stu-id="84870-119">See also</span></span>

- [<span data-ttu-id="84870-120">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84870-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="84870-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="84870-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

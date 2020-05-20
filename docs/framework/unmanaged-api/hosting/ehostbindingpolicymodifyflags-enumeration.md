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
ms.openlocfilehash: 256c362ae0aea51fea16ce799db243b105dee81a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616244"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="79328-102">EHostBindingPolicyModifyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="79328-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="79328-103">호스트에서 소스 어셈블리의 정책 수정을 대상 어셈블리에 적용할 때 CLR (공용 언어 런타임)이 수행 해야 하는 리디렉션 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79328-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79328-104">구문</span><span class="sxs-lookup"><span data-stu-id="79328-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="79328-105">멤버</span><span class="sxs-lookup"><span data-stu-id="79328-105">Members</span></span>  
  
|<span data-ttu-id="79328-106">멤버</span><span class="sxs-lookup"><span data-stu-id="79328-106">Member</span></span>|<span data-ttu-id="79328-107">설명</span><span class="sxs-lookup"><span data-stu-id="79328-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="79328-108">CLR이 소스 어셈블리의 정책 값을 대상 어셈블리의 정책 값에 연결 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79328-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="79328-109">CLR에서 기본 작업을 수행 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79328-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="79328-110">CLR이 대상 어셈블리의 정책 값을 최대 값으로 설정 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79328-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="79328-111">CLR이 대상 어셈블리의 정책 값을 소스 어셈블리의 정책 값으로 바꾸도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79328-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79328-112">설명</span><span class="sxs-lookup"><span data-stu-id="79328-112">Remarks</span></span>  
 <span data-ttu-id="79328-113">[ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EHostBindingPolicyModifyFlags` .</span><span class="sxs-lookup"><span data-stu-id="79328-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79328-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79328-114">Requirements</span></span>  
 <span data-ttu-id="79328-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79328-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79328-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="79328-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79328-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="79328-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79328-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79328-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79328-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79328-119">See also</span></span>

- [<span data-ttu-id="79328-120">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79328-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="79328-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="79328-121">Hosting Enumerations</span></span>](hosting-enumerations.md)

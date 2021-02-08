---
description: '자세히 알아보기: EHostBindingPolicyModifyFlags 열거형'
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
ms.openlocfilehash: be8a15cad49097d1ea2e206e01da2d5d5dcb165a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785486"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="58931-103">EHostBindingPolicyModifyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="58931-103">EHostBindingPolicyModifyFlags Enumeration</span></span>

<span data-ttu-id="58931-104">호스트에서 소스 어셈블리의 정책 수정을 대상 어셈블리에 적용할 때 CLR (공용 언어 런타임)이 수행 해야 하는 리디렉션 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58931-104">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58931-105">구문</span><span class="sxs-lookup"><span data-stu-id="58931-105">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="58931-106">구성원</span><span class="sxs-lookup"><span data-stu-id="58931-106">Members</span></span>  
  
|<span data-ttu-id="58931-107">멤버</span><span class="sxs-lookup"><span data-stu-id="58931-107">Member</span></span>|<span data-ttu-id="58931-108">설명</span><span class="sxs-lookup"><span data-stu-id="58931-108">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="58931-109">CLR이 소스 어셈블리의 정책 값을 대상 어셈블리의 정책 값에 연결 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58931-109">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="58931-110">CLR에서 기본 작업을 수행 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58931-110">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="58931-111">CLR이 대상 어셈블리의 정책 값을 최대 값으로 설정 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58931-111">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="58931-112">CLR이 대상 어셈블리의 정책 값을 소스 어셈블리의 정책 값으로 바꾸도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58931-112">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58931-113">설명</span><span class="sxs-lookup"><span data-stu-id="58931-113">Remarks</span></span>  

 <span data-ttu-id="58931-114">[ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EHostBindingPolicyModifyFlags` .</span><span class="sxs-lookup"><span data-stu-id="58931-114">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58931-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58931-115">Requirements</span></span>  

 <span data-ttu-id="58931-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58931-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58931-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="58931-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58931-118">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58931-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58931-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58931-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58931-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58931-120">See also</span></span>

- [<span data-ttu-id="58931-121">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58931-121">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="58931-122">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="58931-122">Hosting Enumerations</span></span>](hosting-enumerations.md)

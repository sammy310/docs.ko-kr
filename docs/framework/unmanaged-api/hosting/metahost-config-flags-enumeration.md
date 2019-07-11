---
title: METAHOST_CONFIG_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13a7ad5b59dd318f823645d28f9c3ccbec8a8cb0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781082"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="489d6-102">METAHOST_CONFIG_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="489d6-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="489d6-103">반환 가능한 플래그를 설명 합니다는 `pdwConfigFlags` 의 매개 변수를 [iclrmetahostpolicy:: Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 의 설정과 유무를 나타내는 메서드를 `useLegacyV2RuntimeActivationPolicy` 특성는 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="489d6-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="489d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="489d6-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="489d6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="489d6-105">Members</span></span>  
  
|<span data-ttu-id="489d6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="489d6-106">Member</span></span>|<span data-ttu-id="489d6-107">Description</span><span class="sxs-lookup"><span data-stu-id="489d6-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="489d6-108">합니다 `useLegacyV2RuntimeActivationPolicy` 특성에서 제공 되지 않았습니다. 합니다 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="489d6-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="489d6-109">합니다 `useLegacyV2RuntimeActivationPolicy` 특성이 있고 설정 된에 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="489d6-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="489d6-110">합니다 `useLegacyV2RuntimeActivationPolicy` 특성이 있고 설정 된에 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="489d6-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="489d6-111">반환 된 값이 마스크 적용 `pdwConfigFlags` 관련 값을 가져오려면 `useLegacyV2RuntimeActivationPolicy`합니다.</span><span class="sxs-lookup"><span data-stu-id="489d6-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="489d6-112">설명</span><span class="sxs-lookup"><span data-stu-id="489d6-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="489d6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="489d6-113">Requirements</span></span>  
 <span data-ttu-id="489d6-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="489d6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="489d6-115">**헤더:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="489d6-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="489d6-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="489d6-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="489d6-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="489d6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489d6-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="489d6-118">See also</span></span>

- [<span data-ttu-id="489d6-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="489d6-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="489d6-120">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="489d6-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="489d6-121">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="489d6-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)

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
ms.openlocfilehash: 07cab119810c4da25d16a4ad7c13f2d2bda16455
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140315"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="ea3c2-102">METAHOST_CONFIG_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="ea3c2-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="ea3c2-103">[ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 메서드의 `pdwConfigFlags` 매개 변수에 반환 되는 가능한 플래그에 대해 설명 합니다. [\<](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) `useLegacyV2RuntimeActivationPolicy`이 매개 변수는 구성 파일.</span><span class="sxs-lookup"><span data-stu-id="ea3c2-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea3c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea3c2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="ea3c2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ea3c2-105">Members</span></span>  
  
|<span data-ttu-id="ea3c2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ea3c2-106">Member</span></span>|<span data-ttu-id="ea3c2-107">설명</span><span class="sxs-lookup"><span data-stu-id="ea3c2-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="ea3c2-108">`useLegacyV2RuntimeActivationPolicy` 특성이 [\<startup > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c2-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="ea3c2-109">`useLegacyV2RuntimeActivationPolicy` 특성이 있으며 `true`로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c2-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="ea3c2-110">`useLegacyV2RuntimeActivationPolicy` 특성이 있으며 `false`로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c2-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="ea3c2-111">`pdwConfigFlags`에서 반환 된 값에이 마스크를 적용 하 여 `useLegacyV2RuntimeActivationPolicy`와 관련 된 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c2-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea3c2-112">주의</span><span class="sxs-lookup"><span data-stu-id="ea3c2-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea3c2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea3c2-113">Requirements</span></span>  
 <span data-ttu-id="ea3c2-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea3c2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea3c2-115">**헤더:** Metahost</span><span class="sxs-lookup"><span data-stu-id="ea3c2-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="ea3c2-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea3c2-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea3c2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea3c2-118">참조</span><span class="sxs-lookup"><span data-stu-id="ea3c2-118">See also</span></span>

- [<span data-ttu-id="ea3c2-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="ea3c2-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="ea3c2-120">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ea3c2-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="ea3c2-121">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="ea3c2-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)

---
description: '다음에 대 한 자세한 정보: 열거형 METAHOST_CONFIG_FLAGS'
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
ms.openlocfilehash: 56d70f50d3b4c48b7fbf1aa3be6fc11cda904638
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679643"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="c3bbc-103">METAHOST_CONFIG_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="c3bbc-103">METAHOST_CONFIG_FLAGS Enumeration</span></span>

<span data-ttu-id="c3bbc-104">`pdwConfigFlags`구성 파일의 요소에 있는 특성의 존재 여부 및 설정을 나타내는 [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) 메서드의 매개 변수에 반환 되는 가능한 플래그를 설명 합니다 `useLegacyV2RuntimeActivationPolicy` . [ \<startup> ](../../configure-apps/file-schema/startup/startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3bbc-104">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bbc-105">구문</span><span class="sxs-lookup"><span data-stu-id="c3bbc-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c3bbc-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c3bbc-106">Members</span></span>  
  
|<span data-ttu-id="c3bbc-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c3bbc-107">Member</span></span>|<span data-ttu-id="c3bbc-108">설명</span><span class="sxs-lookup"><span data-stu-id="c3bbc-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="c3bbc-109">`useLegacyV2RuntimeActivationPolicy`특성이 [ \<startup> 요소](../../configure-apps/file-schema/startup/startup-element.md)에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3bbc-109">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="c3bbc-110">`useLegacyV2RuntimeActivationPolicy`특성이 표시 되 고가로 설정 된 `true` 경우</span><span class="sxs-lookup"><span data-stu-id="c3bbc-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="c3bbc-111">`useLegacyV2RuntimeActivationPolicy`특성이 표시 되 고가로 설정 된 `false` 경우</span><span class="sxs-lookup"><span data-stu-id="c3bbc-111">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="c3bbc-112">이 마스크를에 반환 된 값에 적용 하 여 `pdwConfigFlags` 와 관련 된 값을 가져옵니다 `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="c3bbc-112">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3bbc-113">설명</span><span class="sxs-lookup"><span data-stu-id="c3bbc-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3bbc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3bbc-114">Requirements</span></span>  

 <span data-ttu-id="c3bbc-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3bbc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3bbc-116">**헤더:** Metahost</span><span class="sxs-lookup"><span data-stu-id="c3bbc-116">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="c3bbc-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3bbc-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3bbc-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3bbc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bbc-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3bbc-119">See also</span></span>

- [<span data-ttu-id="c3bbc-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="c3bbc-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="c3bbc-121">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="c3bbc-121">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="c3bbc-122">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="c3bbc-122">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)

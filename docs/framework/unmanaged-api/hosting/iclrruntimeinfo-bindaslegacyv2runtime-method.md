---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: d37ec8e17e62f58212a5f79f4d6b6aa75f57bf7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120265"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="18f10-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime 메서드</span><span class="sxs-lookup"><span data-stu-id="18f10-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="18f10-103">모든 레거시 CLR (공용 언어 런타임) 버전 2 활성화 정책 결정에 대 한 현재 런타임을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="18f10-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f10-104">구문</span><span class="sxs-lookup"><span data-stu-id="18f10-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="18f10-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="18f10-105">Return Value</span></span>  
 <span data-ttu-id="18f10-106">이 메서드는 다음과 같은 특정 Hresult를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f10-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="18f10-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18f10-107">HRESULT</span></span>|<span data-ttu-id="18f10-108">설명</span><span class="sxs-lookup"><span data-stu-id="18f10-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18f10-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="18f10-109">S_OK</span></span>|<span data-ttu-id="18f10-110">바인딩이 성공 했거나이 런타임이 이미 레거시 CLR 버전 2 활성화 정책 런타임으로 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f10-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="18f10-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="18f10-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="18f10-112">다른 런타임이 이미 레거시 CLR 버전 2 활성화 정책에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f10-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f10-113">주의</span><span class="sxs-lookup"><span data-stu-id="18f10-113">Remarks</span></span>  
 <span data-ttu-id="18f10-114">현재 런타임이 모든 레거시 CLR 버전 2 활성화 정책 결정에 이미 바인딩되어 있는 경우 (예: 구성 파일에서 [\<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 에 `useLegacyV2RuntimeActivationPolicy` 특성 사용)이 메서드는 오류 결과를 반환 하지 않습니다. 대신, 메서드가 레거시 활성화 정책을 성공적으로 바인딩한 경우와 마찬가지로 결과는 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="18f10-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f10-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18f10-115">Requirements</span></span>  
 <span data-ttu-id="18f10-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18f10-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f10-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="18f10-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="18f10-118">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f10-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18f10-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f10-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f10-120">참조</span><span class="sxs-lookup"><span data-stu-id="18f10-120">See also</span></span>

- [<span data-ttu-id="18f10-121">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18f10-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="18f10-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18f10-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="18f10-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="18f10-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="18f10-124">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="18f10-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)

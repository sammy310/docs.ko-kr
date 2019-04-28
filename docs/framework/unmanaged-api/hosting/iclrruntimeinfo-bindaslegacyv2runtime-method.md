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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 647c87b6f42b01922a385d502d72410af3140cd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771789"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="ee5f8-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime 메서드</span><span class="sxs-lookup"><span data-stu-id="ee5f8-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="ee5f8-103">모든 레거시 공용 언어 런타임 (CLR) 버전 2 정품 인증 정책 결정에 대 한 현재 런타임에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5f8-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee5f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee5f8-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ee5f8-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="ee5f8-105">Return Value</span></span>  
 <span data-ttu-id="ee5f8-106">이 메서드는 다음과 같은 특정 Hresult를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5f8-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="ee5f8-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee5f8-107">HRESULT</span></span>|<span data-ttu-id="ee5f8-108">설명</span><span class="sxs-lookup"><span data-stu-id="ee5f8-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee5f8-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee5f8-109">S_OK</span></span>|<span data-ttu-id="ee5f8-110">바인딩 성공 하거나 레거시 CLR 버전 2 정품 인증 정책 런타임이 이미이 런타임 바인딩 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5f8-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="ee5f8-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="ee5f8-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="ee5f8-112">다양 한 런타임 이미 레거시 CLR 버전 2 정품 인증 정책에 바인딩 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5f8-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee5f8-113">설명</span><span class="sxs-lookup"><span data-stu-id="ee5f8-113">Remarks</span></span>  
 <span data-ttu-id="ee5f8-114">모든 레거시 CLR 버전 2 정품 인증 정책 결정에 대 한 현재 런타임에 이미 바인딩되어 있으면 (사용 하 여 예를 들어,를 `useLegacyV2RuntimeActivationPolicy` 특성을 합니다 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 구성 파일에서),이 메서드 오류 결과;를 반환 하지 않습니다. 대신, 결과 S_OK를 메서드가 레거시 활성화 정책이 성공적으로 바인딩할 경우 것 처럼입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5f8-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee5f8-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee5f8-115">Requirements</span></span>  
 <span data-ttu-id="ee5f8-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee5f8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee5f8-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ee5f8-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ee5f8-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ee5f8-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee5f8-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee5f8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5f8-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee5f8-120">See also</span></span>

- [<span data-ttu-id="ee5f8-121">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee5f8-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ee5f8-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee5f8-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ee5f8-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="ee5f8-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="ee5f8-124">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="ee5f8-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)

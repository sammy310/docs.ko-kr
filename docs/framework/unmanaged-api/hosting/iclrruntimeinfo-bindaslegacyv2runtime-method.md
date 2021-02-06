---
description: '자세히 알아보기: ICLRRuntimeInfo:: BindAsLegacyV2Runtime 메서드'
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
ms.openlocfilehash: 77b340cba18ea86546e1a8f4a17933f09289b1de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637182"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="f096a-103">ICLRRuntimeInfo::BindAsLegacyV2Runtime 메서드</span><span class="sxs-lookup"><span data-stu-id="f096a-103">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>

<span data-ttu-id="f096a-104">모든 레거시 CLR (공용 언어 런타임) 버전 2 활성화 정책 결정에 대 한 현재 런타임을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="f096a-104">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f096a-105">구문</span><span class="sxs-lookup"><span data-stu-id="f096a-105">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f096a-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="f096a-106">Return Value</span></span>  

 <span data-ttu-id="f096a-107">이 메서드는 다음과 같은 특정 Hresult를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f096a-107">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="f096a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f096a-108">HRESULT</span></span>|<span data-ttu-id="f096a-109">설명</span><span class="sxs-lookup"><span data-stu-id="f096a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f096a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f096a-110">S_OK</span></span>|<span data-ttu-id="f096a-111">바인딩이 성공 했거나이 런타임이 이미 레거시 CLR 버전 2 활성화 정책 런타임으로 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f096a-111">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="f096a-112">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="f096a-112">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="f096a-113">다른 런타임이 이미 레거시 CLR 버전 2 활성화 정책에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f096a-113">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f096a-114">설명</span><span class="sxs-lookup"><span data-stu-id="f096a-114">Remarks</span></span>  

 <span data-ttu-id="f096a-115">구성 파일의 요소에서 특성을 사용 하는 등의 방법으로 현재 런타임이 모든 레거시 CLR 버전 2 활성화 정책 결정에 이미 바인딩되어 있는 경우 `useLegacyV2RuntimeActivationPolicy` 이 메서드는 오류 결과를 반환 하지 않습니다. 대신 메서드가 레거시 활성화 정책을 성공적으로 바인딩한 경우와 마찬가지로 결과가 S_OK 됩니다 [ \<startup> ](../../configure-apps/file-schema/startup/startup-element.md) .</span><span class="sxs-lookup"><span data-stu-id="f096a-115">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f096a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f096a-116">Requirements</span></span>  

 <span data-ttu-id="f096a-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f096a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f096a-118">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="f096a-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f096a-119">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f096a-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f096a-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f096a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f096a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f096a-121">See also</span></span>

- [<span data-ttu-id="f096a-122">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f096a-122">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f096a-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f096a-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f096a-124">호스팅</span><span class="sxs-lookup"><span data-stu-id="f096a-124">Hosting</span></span>](index.md)
- [<span data-ttu-id="f096a-125">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="f096a-125">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)

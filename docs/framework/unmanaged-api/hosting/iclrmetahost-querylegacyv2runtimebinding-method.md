---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: b270a6691d4e4ee4a5d0b42f424694eb7993e4e7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504149"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="b324b-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding 메서드</span><span class="sxs-lookup"><span data-stu-id="b324b-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="b324b-103">레거시 정품 인증 정책이 바인딩된 런타임을 나타내는 인터페이스를 반환 합니다. 예를 들어, `useLegacyV2RuntimeActivationPolicy` 레거시 활성화 api를 직접 사용 하거나 [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) 메서드를 호출 하 여 [ \<startup> 요소](../../configure-apps/file-schema/startup/startup-element.md) 구성 파일 항목의 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b324b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b324b-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b324b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b324b-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="b324b-106">진행 필수입니다. 현재이 매개 변수에 유효한 값은 뿐 `IID_ICLRRuntimeInfo` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="b324b-107">[out] 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-107">[out] Required.</span></span> <span data-ttu-id="b324b-108">이 메서드는 반환 될 때 레거시 활성화 정책에 바인딩된 런타임을 나타내는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b324b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="b324b-109">Return Value</span></span>  
 <span data-ttu-id="b324b-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b324b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b324b-111">HRESULT</span></span>|<span data-ttu-id="b324b-112">설명</span><span class="sxs-lookup"><span data-stu-id="b324b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b324b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b324b-113">S_OK</span></span>|<span data-ttu-id="b324b-114">메서드가 성공적으로 완료되고 레거시 활성화 정책에 바인딩된 런타임을 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="b324b-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b324b-115">S_FALSE</span></span>|<span data-ttu-id="b324b-116">메서드가 성공적으로 완료되지만 레거시 런타임이 아직 바인딩되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="b324b-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="b324b-117">E_NOINTERFACE</span></span>|<span data-ttu-id="b324b-118">메서드가 레거시 활성화 정책에 바인딩된 런타임을 찾았지만 `riid`는 해당 런타임에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b324b-119">설명</span><span class="sxs-lookup"><span data-stu-id="b324b-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b324b-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b324b-120">Requirements</span></span>  
 <span data-ttu-id="b324b-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b324b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b324b-122">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="b324b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b324b-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b324b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b324b-124">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b324b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b324b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b324b-125">See also</span></span>

- [<span data-ttu-id="b324b-126">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b324b-126">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="b324b-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="b324b-127">Hosting</span></span>](index.md)

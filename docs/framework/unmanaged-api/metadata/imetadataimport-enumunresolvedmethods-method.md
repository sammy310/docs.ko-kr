---
title: IMetaDataImport::EnumUnresolvedMethods 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a91c8de67a095a2f89a69f43375c9ebdd4fc767c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491297"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="945ed-102">IMetaDataImport::EnumUnresolvedMethods 메서드</span><span class="sxs-lookup"><span data-stu-id="945ed-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="945ed-103">현재 메타데이터 범위에서 확인되지 않은 메서드를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="945ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="945ed-104">Syntax</span></span>  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="945ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="945ed-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="945ed-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="945ed-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="945ed-108">[out] MemberDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="945ed-109">[in] `rMethods` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="945ed-110">[out] MemberDef 토큰에서 반환 된 수가 `rMethods`합니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="945ed-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="945ed-111">Return Value</span></span>  
  
|<span data-ttu-id="945ed-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="945ed-112">HRESULT</span></span>|<span data-ttu-id="945ed-113">설명</span><span class="sxs-lookup"><span data-stu-id="945ed-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="945ed-114">`EnumUnresolvedMethods` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="945ed-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="945ed-116">이런 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="945ed-117">설명</span><span class="sxs-lookup"><span data-stu-id="945ed-117">Remarks</span></span>  
 <span data-ttu-id="945ed-118">확인 되지 않은 메서드는 선언 되었지만 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="945ed-119">메서드는 메서드가 표시 하는 경우 열거형에 포함 됩니다 `miForwardRef` 고 `mdPinvokeImpl` 또는 `miRuntime` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="945ed-120">즉,는 확인 되지 않은 메서드는 표시 된 클래스 메서드를 `miForwardRef` (PInvoke를 통해 도달 함) 관리 되지 않는 코드로 구현 하지 않으며 런타임 자체에서 내부적으로 구현 하는 있지만</span><span class="sxs-lookup"><span data-stu-id="945ed-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="945ed-121">열거형 모듈 범위 (전역)에서 또는 인터페이스 또는 추상 클래스에 정의 된 모든 메서드를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="945ed-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="945ed-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="945ed-122">Requirements</span></span>  
 <span data-ttu-id="945ed-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="945ed-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="945ed-124">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="945ed-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="945ed-125">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="945ed-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="945ed-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="945ed-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945ed-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="945ed-127">See also</span></span>
- [<span data-ttu-id="945ed-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="945ed-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="945ed-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="945ed-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

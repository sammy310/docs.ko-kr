---
title: IMetaDataImport::EnumSignatures 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 193abe173b259ff2679642e229fce96151e37872
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179685"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="5e176-102">IMetaDataImport::EnumSignatures 메서드</span><span class="sxs-lookup"><span data-stu-id="5e176-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="5e176-103">현재 범위의 독립 실행형 서명을 나타내는 Signature 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e176-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e176-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e176-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5e176-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5e176-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5e176-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="5e176-108">[out] 서명 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5e176-109">[in] `rSignatures` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="5e176-110">[out] 서명 토큰에서 반환 된 수가 `rSignatures`합니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e176-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="5e176-111">Return Value</span></span>  
  
|<span data-ttu-id="5e176-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e176-112">HRESULT</span></span>|<span data-ttu-id="5e176-113">설명</span><span class="sxs-lookup"><span data-stu-id="5e176-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures` <span data-ttu-id="5e176-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5e176-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="5e176-116">이런 경우 `pcSignatures` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5e176-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e176-117">설명</span><span class="sxs-lookup"><span data-stu-id="5e176-117">Remarks</span></span>  
 <span data-ttu-id="5e176-118">서명 토큰에 의해 만들어집니다 합니다 [imetadataemit:: Gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5e176-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e176-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e176-119">Requirements</span></span>  
 <span data-ttu-id="5e176-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5e176-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e176-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5e176-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e176-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5e176-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5e176-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="5e176-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e176-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="5e176-124">See also</span></span>

- [<span data-ttu-id="5e176-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e176-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5e176-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e176-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

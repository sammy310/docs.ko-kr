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
ms.openlocfilehash: 9dbbdcc9d0fb9f0a8d2a64edfa4a0ad92570933c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450013"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="7e4ed-102">IMetaDataImport::EnumSignatures 메서드</span><span class="sxs-lookup"><span data-stu-id="7e4ed-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="7e4ed-103">현재 범위의 독립 실행형 서명을 나타내는 Signature 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e4ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e4ed-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e4ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e4ed-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7e4ed-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7e4ed-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="7e4ed-108">[out] The array used to store the Signature tokens.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7e4ed-109">[in] `rSignatures` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="7e4ed-110">[out] The number of Signature tokens returned in `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e4ed-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7e4ed-111">Return Value</span></span>  
  
|<span data-ttu-id="7e4ed-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e4ed-112">HRESULT</span></span>|<span data-ttu-id="7e4ed-113">설명</span><span class="sxs-lookup"><span data-stu-id="7e4ed-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7e4ed-114">`EnumSignatures` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7e4ed-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7e4ed-116">In that case, `pcSignatures` is zero.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e4ed-117">주의</span><span class="sxs-lookup"><span data-stu-id="7e4ed-117">Remarks</span></span>  
 <span data-ttu-id="7e4ed-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e4ed-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e4ed-119">Requirements</span></span>  
 <span data-ttu-id="7e4ed-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e4ed-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e4ed-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e4ed-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e4ed-122">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e4ed-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e4ed-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e4ed-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4ed-124">참조</span><span class="sxs-lookup"><span data-stu-id="7e4ed-124">See also</span></span>

- [<span data-ttu-id="7e4ed-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e4ed-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7e4ed-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e4ed-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

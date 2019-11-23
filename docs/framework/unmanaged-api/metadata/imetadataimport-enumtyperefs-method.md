---
title: IMetaDataImport::EnumTypeRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: 778ebf1d4fad0c8703964be88fdc3ff8c033bc28
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449989"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="0286f-102">IMetaDataImport::EnumTypeRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="0286f-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="0286f-103">현재 메타데이터 범위에서 정의된 TypeRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="0286f-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0286f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0286f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0286f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0286f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0286f-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="0286f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0286f-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="0286f-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="0286f-108">[out] The array used to store the TypeRef tokens.</span><span class="sxs-lookup"><span data-stu-id="0286f-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0286f-109">[in] `rTypeRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0286f-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="0286f-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="0286f-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0286f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="0286f-111">Return Value</span></span>  
  
|<span data-ttu-id="0286f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0286f-112">HRESULT</span></span>|<span data-ttu-id="0286f-113">설명</span><span class="sxs-lookup"><span data-stu-id="0286f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0286f-114">`EnumTypeRefs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="0286f-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0286f-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="0286f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0286f-116">In that case, `pcTypeRefs` is zero.</span><span class="sxs-lookup"><span data-stu-id="0286f-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0286f-117">주의</span><span class="sxs-lookup"><span data-stu-id="0286f-117">Remarks</span></span>  
 <span data-ttu-id="0286f-118">A TypeRef token represents a reference to a type.</span><span class="sxs-lookup"><span data-stu-id="0286f-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0286f-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0286f-119">Requirements</span></span>  
 <span data-ttu-id="0286f-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0286f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0286f-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0286f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0286f-122">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0286f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0286f-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0286f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0286f-124">참조</span><span class="sxs-lookup"><span data-stu-id="0286f-124">See also</span></span>

- [<span data-ttu-id="0286f-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0286f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0286f-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0286f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

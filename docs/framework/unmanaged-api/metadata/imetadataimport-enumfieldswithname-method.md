---
title: IMetaDataImport::EnumFieldsWithName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf624695136a9397937f05b28dec18493c8e12d7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153662"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="2f824-102">IMetaDataImport::EnumFieldsWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="2f824-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="2f824-103">지정한 이름을 가진 지정한 형식의 FieldDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f824-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f824-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f824-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f824-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2f824-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="2f824-107">[in] 토큰 필드가 포함 된 열거 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="2f824-108">[in] 열거형의 범위를 제한 하는 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="2f824-109">[out] FieldDef 토큰을 저장 하는 데 사용 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2f824-110">[in] `rFields` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2f824-111">[out] 실제 FieldDef 토큰에서 반환 된 수가 `rFields`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f824-112">설명</span><span class="sxs-lookup"><span data-stu-id="2f824-112">Remarks</span></span>  
 <span data-ttu-id="2f824-113">와 달리 [imetadataimport:: Enumfields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` 지정 된 이름이 없는 모든 필드 토큰을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f824-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="2f824-114">Return Value</span></span>  
  
|<span data-ttu-id="2f824-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f824-115">HRESULT</span></span>|<span data-ttu-id="2f824-116">설명</span><span class="sxs-lookup"><span data-stu-id="2f824-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumFieldsWithName` <span data-ttu-id="2f824-117">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-117">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2f824-118">열거 하는 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-118">There are no fields to enumerate.</span></span> <span data-ttu-id="2f824-119">이런 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="2f824-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f824-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f824-120">Requirements</span></span>  
 <span data-ttu-id="2f824-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f824-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f824-122">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f824-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f824-123">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2f824-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2f824-124">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2f824-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f824-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f824-125">See also</span></span>

- [<span data-ttu-id="2f824-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f824-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2f824-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f824-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

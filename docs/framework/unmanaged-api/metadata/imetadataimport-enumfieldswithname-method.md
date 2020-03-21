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
ms.openlocfilehash: bb8b531a884c9d3c2f33aa4aec5c4dbeaafe2b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177351"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="da272-102">IMetaDataImport::EnumFieldsWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="da272-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="da272-103">지정한 이름을 가진 지정한 형식의 FieldDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="da272-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da272-104">구문</span><span class="sxs-lookup"><span data-stu-id="da272-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da272-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da272-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="da272-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da272-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="da272-107">【인】 필드를 들어야 하는 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="da272-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="da272-108">【인】 열거형의 범위를 제한하는 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="da272-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="da272-109">【아웃】 FieldDef 토큰을 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="da272-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="da272-110">[in] `rFields` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="da272-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="da272-111">【아웃】 에서 반환되는 FieldDef 토큰의 `rFields`실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="da272-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da272-112">설명</span><span class="sxs-lookup"><span data-stu-id="da272-112">Remarks</span></span>  
 <span data-ttu-id="da272-113">[IMetaDataImport::EnumFields와](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md) `EnumFieldsWithName` 달리 지정된 이름이 없는 모든 필드 토큰은 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="da272-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da272-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="da272-114">Return Value</span></span>  
  
|<span data-ttu-id="da272-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da272-115">HRESULT</span></span>|<span data-ttu-id="da272-116">Description</span><span class="sxs-lookup"><span data-stu-id="da272-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="da272-117">`EnumFieldsWithName`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="da272-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="da272-118">입력할 필드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da272-118">There are no fields to enumerate.</span></span> <span data-ttu-id="da272-119">이 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="da272-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da272-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da272-120">Requirements</span></span>  
 <span data-ttu-id="da272-121">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da272-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da272-122">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="da272-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da272-123">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="da272-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da272-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da272-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da272-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da272-125">See also</span></span>

- [<span data-ttu-id="da272-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da272-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="da272-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da272-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

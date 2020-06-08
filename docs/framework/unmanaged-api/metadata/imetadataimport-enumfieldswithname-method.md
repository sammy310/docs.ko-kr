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
ms.openlocfilehash: 68261b165847a5c3ee29adbc4908451fb00c5443
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492267"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="6f9a8-102">IMetaDataImport::EnumFieldsWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="6f9a8-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="6f9a8-103">지정한 이름을 가진 지정한 형식의 FieldDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f9a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f9a8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6f9a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f9a8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6f9a8-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="6f9a8-107">진행 해당 필드를 열거할 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="6f9a8-108">진행 열거형의 범위를 제한 하는 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="6f9a8-109">제한이 FieldDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6f9a8-110">[in] `rFields` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6f9a8-111">제한이 에서 반환 되는 실제 FieldDef 토큰 수입니다 `rFields` .</span><span class="sxs-lookup"><span data-stu-id="6f9a8-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f9a8-112">설명</span><span class="sxs-lookup"><span data-stu-id="6f9a8-112">Remarks</span></span>  
 <span data-ttu-id="6f9a8-113">[IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md)와 달리는 `EnumFieldsWithName` 지정 된 이름이 없는 필드 토큰을 모두 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-113">Unlike [IMetaDataImport::EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f9a8-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="6f9a8-114">Return Value</span></span>  
  
|<span data-ttu-id="6f9a8-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f9a8-115">HRESULT</span></span>|<span data-ttu-id="6f9a8-116">설명</span><span class="sxs-lookup"><span data-stu-id="6f9a8-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6f9a8-117">`EnumFieldsWithName`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6f9a8-118">열거할 필드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-118">There are no fields to enumerate.</span></span> <span data-ttu-id="6f9a8-119">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f9a8-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f9a8-120">Requirements</span></span>  
 <span data-ttu-id="6f9a8-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f9a8-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6f9a8-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f9a8-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f9a8-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6f9a8-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f9a8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9a8-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f9a8-125">See also</span></span>

- [<span data-ttu-id="6f9a8-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f9a8-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6f9a8-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f9a8-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

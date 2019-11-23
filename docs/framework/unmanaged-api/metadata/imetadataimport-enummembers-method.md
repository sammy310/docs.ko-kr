---
title: IMetaDataImport::EnumMembers 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: acb772a64c8f13405f2836bb5f4f308986dce414
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447662"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="8936e-102">IMetaDataImport::EnumMembers 메서드</span><span class="sxs-lookup"><span data-stu-id="8936e-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="8936e-103">지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="8936e-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8936e-104">구문</span><span class="sxs-lookup"><span data-stu-id="8936e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8936e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8936e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8936e-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="8936e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="8936e-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="8936e-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="8936e-108">[out] The array used to hold the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="8936e-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8936e-109">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8936e-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8936e-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="8936e-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8936e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="8936e-111">Return Value</span></span>  
  
|<span data-ttu-id="8936e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8936e-112">HRESULT</span></span>|<span data-ttu-id="8936e-113">설명</span><span class="sxs-lookup"><span data-stu-id="8936e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8936e-114">`EnumMembers` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="8936e-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8936e-115">There are no MemberDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="8936e-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="8936e-116">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="8936e-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8936e-117">주의</span><span class="sxs-lookup"><span data-stu-id="8936e-117">Remarks</span></span>  
 <span data-ttu-id="8936e-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span><span class="sxs-lookup"><span data-stu-id="8936e-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="8936e-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span><span class="sxs-lookup"><span data-stu-id="8936e-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="8936e-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span><span class="sxs-lookup"><span data-stu-id="8936e-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="8936e-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span><span class="sxs-lookup"><span data-stu-id="8936e-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="8936e-122">Properties and events are not enumerated by `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="8936e-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="8936e-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="8936e-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="8936e-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8936e-124">Requirements</span></span>  
 <span data-ttu-id="8936e-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8936e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8936e-126">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8936e-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8936e-127">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8936e-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8936e-128">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8936e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8936e-129">참조</span><span class="sxs-lookup"><span data-stu-id="8936e-129">See also</span></span>

- [<span data-ttu-id="8936e-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8936e-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8936e-131">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8936e-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

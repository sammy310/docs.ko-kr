---
title: IMetaDataImport::EnumMembersWithName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: ed193aab8beb0de1321aa1d52ec9f963b08b316c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441667"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="8307f-102">IMetaDataImport::EnumMembersWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="8307f-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="8307f-103">지정한 이름을 가진 지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8307f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8307f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8307f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8307f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8307f-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="8307f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="8307f-107">[in] A TypeDef token representing the type with members to enumerate.</span><span class="sxs-lookup"><span data-stu-id="8307f-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="8307f-108">[in] The member name that limits the scope of the enumerator.</span><span class="sxs-lookup"><span data-stu-id="8307f-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="8307f-109">[out] The array used to store the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="8307f-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8307f-110">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8307f-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="8307f-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8307f-112">주의</span><span class="sxs-lookup"><span data-stu-id="8307f-112">Remarks</span></span>  
 <span data-ttu-id="8307f-113">This method enumerates fields and methods, but not properties or events.</span><span class="sxs-lookup"><span data-stu-id="8307f-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="8307f-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span><span class="sxs-lookup"><span data-stu-id="8307f-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8307f-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="8307f-115">Return Value</span></span>  
  
|<span data-ttu-id="8307f-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8307f-116">HRESULT</span></span>|<span data-ttu-id="8307f-117">설명</span><span class="sxs-lookup"><span data-stu-id="8307f-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8307f-118">`EnumTypeDefs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="8307f-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8307f-119">There are no MemberDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="8307f-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="8307f-120">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="8307f-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8307f-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8307f-121">Requirements</span></span>  
 <span data-ttu-id="8307f-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8307f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8307f-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8307f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8307f-124">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8307f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8307f-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8307f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8307f-126">참조</span><span class="sxs-lookup"><span data-stu-id="8307f-126">See also</span></span>

- [<span data-ttu-id="8307f-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8307f-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8307f-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8307f-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

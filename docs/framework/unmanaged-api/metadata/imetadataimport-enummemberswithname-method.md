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
ms.openlocfilehash: ea451bdd645d2d4dea4c5dd00408e0bc51804803
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492072"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="923b9-102">IMetaDataImport::EnumMembersWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="923b9-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="923b9-103">지정한 이름을 가진 지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="923b9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="923b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="923b9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="923b9-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="923b9-107">진행 열거할 멤버가 포함 된 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="923b9-108">진행 열거자의 범위를 제한 하는 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="923b9-109">제한이 MemberDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="923b9-110">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="923b9-111">제한이 에서 반환 된 실제 MemberDef 토큰 수입니다 `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="923b9-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="923b9-112">설명</span><span class="sxs-lookup"><span data-stu-id="923b9-112">Remarks</span></span>  
 <span data-ttu-id="923b9-113">이 메서드는 필드 및 메서드를 열거 하지만 속성이 나 이벤트는 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="923b9-114">[IMetaDataImport:: EnumMembers](imetadataimport-enummembers-method.md)와 달리는 `EnumMembersWithName` 지정 된 이름이 없는 모든 필드 및 멤버 토큰을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-114">Unlike [IMetaDataImport::EnumMembers](imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="923b9-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="923b9-115">Return Value</span></span>  
  
|<span data-ttu-id="923b9-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="923b9-116">HRESULT</span></span>|<span data-ttu-id="923b9-117">설명</span><span class="sxs-lookup"><span data-stu-id="923b9-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="923b9-118">`EnumTypeDefs`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="923b9-119">열거할 MemberDef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="923b9-120">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="923b9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="923b9-121">Requirements</span></span>  
 <span data-ttu-id="923b9-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="923b9-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923b9-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="923b9-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="923b9-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="923b9-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="923b9-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923b9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="923b9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="923b9-126">See also</span></span>

- [<span data-ttu-id="923b9-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="923b9-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="923b9-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="923b9-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

---
title: IMetaDataImport::EnumMemberRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: 743b6bed1a5d62f5214b8366b1a3c6e4ebecb98b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441709"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="26939-102">IMetaDataImport::EnumMemberRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="26939-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="26939-103">지정한 형식의 멤버를 나타내는 MemberRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="26939-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26939-104">구문</span><span class="sxs-lookup"><span data-stu-id="26939-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26939-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26939-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="26939-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="26939-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="26939-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="26939-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="26939-108">[out] The array used to store MemberRef tokens.</span><span class="sxs-lookup"><span data-stu-id="26939-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="26939-109">[in] `rMemberRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="26939-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="26939-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="26939-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26939-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="26939-111">Return Value</span></span>  
  
|<span data-ttu-id="26939-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="26939-112">HRESULT</span></span>|<span data-ttu-id="26939-113">설명</span><span class="sxs-lookup"><span data-stu-id="26939-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="26939-114">`EnumMemberRefs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="26939-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="26939-115">There are no MemberRef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="26939-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="26939-116">In that case, `pcTokens` is to zero.</span><span class="sxs-lookup"><span data-stu-id="26939-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26939-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26939-117">Requirements</span></span>  
 <span data-ttu-id="26939-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26939-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26939-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="26939-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26939-120">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26939-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26939-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26939-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26939-122">참조</span><span class="sxs-lookup"><span data-stu-id="26939-122">See also</span></span>

- [<span data-ttu-id="26939-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26939-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="26939-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26939-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

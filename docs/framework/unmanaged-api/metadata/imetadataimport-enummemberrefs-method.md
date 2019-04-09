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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08577f15a6fab0e630d40032a23c273ee935faa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072997"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="e3be0-102">IMetaDataImport::EnumMemberRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="e3be0-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="e3be0-103">지정한 형식의 멤버를 나타내는 MemberRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3be0-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3be0-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3be0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3be0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e3be0-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="e3be0-107">[in] 멤버를 열거할 수 형식에 대 한 형식 정의 TypeRef, MethodDef, 또는 ModuleRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="e3be0-108">[out] MemberRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e3be0-109">[in] `rMemberRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e3be0-110">[out] MemberRef 토큰에서 반환 된 수가 실제 `rMemberRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3be0-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="e3be0-111">Return Value</span></span>  
  
|<span data-ttu-id="e3be0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3be0-112">HRESULT</span></span>|<span data-ttu-id="e3be0-113">설명</span><span class="sxs-lookup"><span data-stu-id="e3be0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs` <span data-ttu-id="e3be0-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e3be0-115">열거할 MemberRef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="e3be0-116">이런 경우 `pcTokens` 는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e3be0-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3be0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3be0-117">Requirements</span></span>  
 <span data-ttu-id="e3be0-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3be0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3be0-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e3be0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3be0-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e3be0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e3be0-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e3be0-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3be0-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3be0-122">See also</span></span>

- [<span data-ttu-id="e3be0-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3be0-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e3be0-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3be0-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

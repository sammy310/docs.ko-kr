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
ms.openlocfilehash: b8a65b0748fec0e474d8b3b5dc03473fbd716108
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177328"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="3b612-102">IMetaDataImport::EnumMemberRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="3b612-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="3b612-103">지정한 형식의 멤버를 나타내는 MemberRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b612-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b612-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b612-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b612-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3b612-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="3b612-107">【인】 멤버를 개명할 형식에 대한 TypeDef, TypeRef, MethodDef 또는 ModuleRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="3b612-108">【아웃】 MemberRef 토큰을 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3b612-109">[in] `rMemberRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3b612-110">【아웃】 에서 반환된 MemberRef 토큰의 `rMemberRefs`실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b612-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="3b612-111">Return Value</span></span>  
  
|<span data-ttu-id="3b612-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b612-112">HRESULT</span></span>|<span data-ttu-id="3b612-113">Description</span><span class="sxs-lookup"><span data-stu-id="3b612-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3b612-114">`EnumMemberRefs`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3b612-115">등록할 MemberRef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="3b612-116">이 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="3b612-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b612-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b612-117">Requirements</span></span>  
 <span data-ttu-id="3b612-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b612-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b612-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="3b612-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b612-120">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3b612-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b612-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b612-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b612-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b612-122">See also</span></span>

- [<span data-ttu-id="3b612-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b612-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3b612-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b612-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

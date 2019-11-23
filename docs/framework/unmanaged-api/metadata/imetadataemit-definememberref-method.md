---
title: IMetaDataEmit::DefineMemberRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 696389b51328e167212fb2292a873c34b9263811
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431825"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="114f6-102">IMetaDataEmit::DefineMemberRef 메서드</span><span class="sxs-lookup"><span data-stu-id="114f6-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="114f6-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span><span class="sxs-lookup"><span data-stu-id="114f6-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="114f6-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="114f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="114f6-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="114f6-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span><span class="sxs-lookup"><span data-stu-id="114f6-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="114f6-107">[in] The name of the target member.</span><span class="sxs-lookup"><span data-stu-id="114f6-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="114f6-108">[in] The signature of the target member.</span><span class="sxs-lookup"><span data-stu-id="114f6-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="114f6-109">[in] The count of bytes in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="114f6-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="114f6-110">[out] The `mdMemberRef` token assigned.</span><span class="sxs-lookup"><span data-stu-id="114f6-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="114f6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="114f6-111">Requirements</span></span>  
 <span data-ttu-id="114f6-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="114f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="114f6-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="114f6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="114f6-114">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="114f6-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="114f6-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="114f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114f6-116">참조</span><span class="sxs-lookup"><span data-stu-id="114f6-116">See also</span></span>

- [<span data-ttu-id="114f6-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="114f6-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="114f6-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="114f6-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

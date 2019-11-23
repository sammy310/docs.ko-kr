---
title: IMetaDataEmit2::DefineMethodSpec 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: 7547d7557169b1279125141afb5b05e22341942a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432746"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="9559b-102">IMetaDataEmit2::DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="9559b-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="9559b-103">Creates a generic instance of a method, and gets a token to the definition.</span><span class="sxs-lookup"><span data-stu-id="9559b-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9559b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9559b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9559b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9559b-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="9559b-106">[in] A token for the method of which to create the generic instance.</span><span class="sxs-lookup"><span data-stu-id="9559b-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="9559b-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="9559b-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9559b-108">[in] A pointer to the binary COM+ signature of the method.</span><span class="sxs-lookup"><span data-stu-id="9559b-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="9559b-109">[in] The size, in bytes, of `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="9559b-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="9559b-110">[out] A token to the metadata signature definition of the method.</span><span class="sxs-lookup"><span data-stu-id="9559b-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9559b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9559b-111">Requirements</span></span>  
 <span data-ttu-id="9559b-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9559b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9559b-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9559b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9559b-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9559b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9559b-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9559b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9559b-116">참조</span><span class="sxs-lookup"><span data-stu-id="9559b-116">See also</span></span>

- [<span data-ttu-id="9559b-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9559b-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="9559b-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9559b-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

---
title: IMetaDataEmit::DefineMethodImpl 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 184ae0aee6947aa686e80541ab3ba36e0f4e1647
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66424011"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="d0a6d-102">IMetaDataEmit::DefineMethodImpl 메서드</span><span class="sxs-lookup"><span data-stu-id="d0a6d-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="d0a6d-103">인터페이스에서 상속 된 메서드 구현에 대 한 정의 만들고 해당 메서드 구현을 정의에 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6d-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a6d-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0a6d-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0a6d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0a6d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d0a6d-106">[in] `mdTypedef` 토큰 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6d-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="d0a6d-107">[in] 합니다 `mdMethodDef` 또는 `mdMemberRef` 코드 본문의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6d-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="d0a6d-108">[in] 합니다 `mdMethodDef` 또는 `mdMemberRef` 구현 되는 인터페이스 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a6d-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0a6d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0a6d-109">Requirements</span></span>  
 <span data-ttu-id="d0a6d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0a6d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0a6d-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0a6d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0a6d-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d0a6d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0a6d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0a6d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a6d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0a6d-114">See also</span></span>

- [<span data-ttu-id="d0a6d-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0a6d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d0a6d-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0a6d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

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
ms.openlocfilehash: 05b2530bde2f4532e94610a683e7bbc2f59540aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178388"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="812eb-102">IMetaDataEmit::DefineMethodImpl 메서드</span><span class="sxs-lookup"><span data-stu-id="812eb-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="812eb-103">인터페이스에서 상속 된 메서드 구현에 대 한 정의 만들고 해당 메서드 구현을 정의에 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="812eb-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="812eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="812eb-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="812eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="812eb-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="812eb-106">[in] `mdTypedef` 토큰 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="812eb-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="812eb-107">[in] 합니다 `mdMethodDef` 또는 `mdMethodRef` 코드 본문의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="812eb-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="812eb-108">[in] 합니다 `mdMethodDef` 또는 `mdMethodRef` 구현 되는 인터페이스 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="812eb-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="812eb-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="812eb-109">Requirements</span></span>  
 <span data-ttu-id="812eb-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="812eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="812eb-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="812eb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="812eb-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="812eb-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="812eb-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="812eb-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="812eb-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="812eb-114">See also</span></span>

- [<span data-ttu-id="812eb-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="812eb-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="812eb-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="812eb-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

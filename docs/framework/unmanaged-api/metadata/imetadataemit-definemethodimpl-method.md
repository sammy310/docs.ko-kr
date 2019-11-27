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
ms.openlocfilehash: 99f529a151a42cf4a9ee1f74bd3a76a5b6b1b35f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445269"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="cbad1-102">IMetaDataEmit::DefineMethodImpl 메서드</span><span class="sxs-lookup"><span data-stu-id="cbad1-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="cbad1-103">인터페이스에서 상속 된 메서드의 구현에 대 한 정의를 만들고 해당 메서드 구현 정의에 대 한 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbad1-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbad1-104">구문</span><span class="sxs-lookup"><span data-stu-id="cbad1-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbad1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cbad1-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="cbad1-106">진행 구현 하는 클래스의 `mdTypedef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cbad1-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="cbad1-107">진행 코드 본문의 `mdMethodDef` 또는 `mdMemberRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cbad1-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="cbad1-108">진행 구현 중인 인터페이스 메서드의 `mdMethodDef` 또는 `mdMemberRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cbad1-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbad1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cbad1-109">Requirements</span></span>  
 <span data-ttu-id="cbad1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbad1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbad1-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="cbad1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbad1-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbad1-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbad1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbad1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbad1-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="cbad1-114">See also</span></span>

- [<span data-ttu-id="cbad1-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbad1-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cbad1-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbad1-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

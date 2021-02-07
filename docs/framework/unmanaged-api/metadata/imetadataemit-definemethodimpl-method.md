---
description: IMetaDataEmit::D efineMethodImpl 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 9c79d713e61bfcc7b3191e570ed727b128422bf1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753408"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="35194-103">IMetaDataEmit::DefineMethodImpl 메서드</span><span class="sxs-lookup"><span data-stu-id="35194-103">IMetaDataEmit::DefineMethodImpl Method</span></span>

<span data-ttu-id="35194-104">인터페이스에서 상속 된 메서드의 구현에 대 한 정의를 만들고 해당 메서드 구현 정의에 대 한 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35194-104">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35194-105">구문</span><span class="sxs-lookup"><span data-stu-id="35194-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35194-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35194-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="35194-107">진행 `mdTypedef` 구현 하는 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35194-107">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="35194-108">진행 `mdMethodDef` `mdMemberRef` 코드 본문의 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35194-108">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="35194-109">진행 `mdMethodDef` `mdMemberRef` 구현 중인 인터페이스 메서드의 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35194-109">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35194-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35194-110">Requirements</span></span>  

 <span data-ttu-id="35194-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35194-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35194-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="35194-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35194-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35194-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35194-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35194-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35194-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35194-115">See also</span></span>

- [<span data-ttu-id="35194-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35194-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="35194-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35194-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

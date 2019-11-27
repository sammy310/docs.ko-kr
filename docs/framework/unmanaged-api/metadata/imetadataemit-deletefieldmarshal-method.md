---
title: IMetaDataEmit::DeleteFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 652169c67461c1663c005dd014290c4cf2d993ba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434374"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="53f94-102">IMetaDataEmit::DeleteFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="53f94-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="53f94-103">지정 된 토큰이 참조 하는 개체에 대 한 PInvoke 마샬링 메타 데이터 서명을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f94-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f94-104">구문</span><span class="sxs-lookup"><span data-stu-id="53f94-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53f94-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="53f94-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="53f94-106">진행 마샬링 메타 데이터 시그니처를 삭제할 필드 또는 매개 변수를 나타내는 `mdFieldDef` 또는 `mdParamDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="53f94-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f94-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53f94-107">Requirements</span></span>  
 <span data-ttu-id="53f94-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53f94-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53f94-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="53f94-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53f94-110">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53f94-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53f94-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53f94-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f94-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53f94-112">See also</span></span>

- [<span data-ttu-id="53f94-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53f94-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="53f94-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53f94-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

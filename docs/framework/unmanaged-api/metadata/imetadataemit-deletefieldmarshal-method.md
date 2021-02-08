---
description: IMetaDataEmit::D eleteFieldMarshal 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 966f2ae20ad9ff4b9c1c9eec32974bc89aa76d13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783965"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="986cf-103">IMetaDataEmit::DeleteFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="986cf-103">IMetaDataEmit::DeleteFieldMarshal Method</span></span>

<span data-ttu-id="986cf-104">지정 된 토큰이 참조 하는 개체에 대 한 PInvoke 마샬링 메타 데이터 서명을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="986cf-104">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="986cf-105">구문</span><span class="sxs-lookup"><span data-stu-id="986cf-105">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="986cf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="986cf-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="986cf-107">진행 `mdFieldDef` `mdParamDef` 마샬링 메타 데이터 시그니처를 삭제할 필드 또는 매개 변수를 나타내는 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="986cf-107">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="986cf-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="986cf-108">Requirements</span></span>  

 <span data-ttu-id="986cf-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="986cf-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="986cf-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="986cf-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="986cf-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="986cf-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="986cf-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="986cf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986cf-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="986cf-113">See also</span></span>

- [<span data-ttu-id="986cf-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="986cf-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="986cf-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="986cf-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

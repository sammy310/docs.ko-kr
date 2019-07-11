---
title: IMetaDataEmit::SetEventProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 271ecd7e757340becccb7bf52362487a2b277299
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737187"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="6e542-102">IMetaDataEmit::SetEventProps 메서드</span><span class="sxs-lookup"><span data-stu-id="6e542-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="6e542-103">설정 하거나 지정된 된 기능에 대 한 이전 호출에서 정의 된 이벤트의 업데이트 [imetadataemit:: Defineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e542-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e542-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,   
    [in]  DWORD       dwEventFlags,   
    [in]  mdToken     tkEventType,   
    [in]  mdMethodDef mdAddOn,   
    [in]  mdMethodDef mdRemoveOn,   
    [in]  mdMethodDef mdFire,   
    [in]  mdMethodDef rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e542-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e542-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="6e542-106">[in] 이벤트 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="6e542-107">[in] 이벤트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-107">[in] Event flags.</span></span> <span data-ttu-id="6e542-108">이 비트 마스크의 `CorEventAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="6e542-109">[in] 이벤트 클래스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-109">[in] The token for the event class.</span></span> <span data-ttu-id="6e542-110">이 값은 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="6e542-111">[in] 이벤트 또는 null을 구독 하는 데 사용 된 메서드.</span><span class="sxs-lookup"><span data-stu-id="6e542-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="6e542-112">[in] 이벤트 또는 null로 구독을 취소 하는 데 사용 된 메서드.</span><span class="sxs-lookup"><span data-stu-id="6e542-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="6e542-113">[in] 이벤트를 발생 시킬 (파생된 클래스)에 의해 사용 되는 방법</span><span class="sxs-lookup"><span data-stu-id="6e542-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="6e542-114">[in] 이벤트에 연결 된 다른 방법에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="6e542-115">배열의 마지막 요소 여야 합니다 `mdMethodDefNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="6e542-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e542-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e542-116">Requirements</span></span>  
 <span data-ttu-id="6e542-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e542-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e542-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e542-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e542-119">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6e542-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e542-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e542-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e542-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e542-121">See also</span></span>

- [<span data-ttu-id="6e542-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e542-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6e542-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e542-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

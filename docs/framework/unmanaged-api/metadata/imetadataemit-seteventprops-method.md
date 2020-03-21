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
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177522"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="378ae-102">IMetaDataEmit::SetEventProps 메서드</span><span class="sxs-lookup"><span data-stu-id="378ae-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="378ae-103">[IMetaDataEmit::DefineEvent에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)대한 사전 호출에 의해 정의된 이벤트의 지정된 기능을 설정하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="378ae-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="378ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="378ae-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="378ae-106">【인】 이벤트 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="378ae-107">【인】 이벤트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-107">[in] Event flags.</span></span> <span data-ttu-id="378ae-108">이것은 값의 `CorEventAttr` 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="378ae-109">【인】 이벤트 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-109">[in] The token for the event class.</span></span> <span data-ttu-id="378ae-110">이것은 또는 `mdTypeDef` 토큰입니다. `mdTypeRef`</span><span class="sxs-lookup"><span data-stu-id="378ae-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="378ae-111">【인】 이벤트를 구독하는 데 사용되는 메서드 또는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="378ae-112">【인】 이벤트 구독을 취소하거나 null에 사용되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="378ae-113">【인】 이벤트를 발생시키기 위해 파생 클래스에서 사용하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="378ae-114">【인】 이벤트와 연결된 다른 메서드에 대한 토큰 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="378ae-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="378ae-115">배열의 마지막 요소는 . `mdMethodDefNil`</span><span class="sxs-lookup"><span data-stu-id="378ae-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="378ae-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="378ae-116">Requirements</span></span>  
 <span data-ttu-id="378ae-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="378ae-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="378ae-118">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="378ae-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="378ae-119">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="378ae-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="378ae-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="378ae-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="378ae-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="378ae-121">See also</span></span>

- [<span data-ttu-id="378ae-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ae-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="378ae-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ae-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

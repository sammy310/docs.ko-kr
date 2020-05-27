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
ms.openlocfilehash: 720133e64c02aa09c9ff7e43a20630b0d55c1acf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008757"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="f2056-102">IMetaDataEmit::SetEventProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f2056-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="f2056-103">[IMetaDataEmit::D efineEvent](imetadataemit-defineevent-method.md)에 대 한 이전 호출에서 정의한 이벤트의 지정 된 기능을 설정 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2056-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2056-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f2056-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2056-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="f2056-106">진행 이벤트 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="f2056-107">진행 이벤트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-107">[in] Event flags.</span></span> <span data-ttu-id="f2056-108">값의 비트 마스크입니다 `CorEventAttr` .</span><span class="sxs-lookup"><span data-stu-id="f2056-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="f2056-109">진행 이벤트 클래스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-109">[in] The token for the event class.</span></span> <span data-ttu-id="f2056-110">`mdTypeDef`또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="f2056-111">진행 이벤트를 구독 하는 데 사용 되는 메서드 이거나 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="f2056-112">진행 이벤트를 구독 취소 하는 데 사용 되는 메서드 이거나 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="f2056-113">진행 파생 클래스에서 이벤트를 발생 시키는 데 사용 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="f2056-114">진행 이벤트와 연결 된 다른 메서드에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="f2056-115">배열의 마지막 요소는 이어야 합니다 `mdMethodDefNil` .</span><span class="sxs-lookup"><span data-stu-id="f2056-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2056-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2056-116">Requirements</span></span>  
 <span data-ttu-id="f2056-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2056-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2056-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f2056-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2056-119">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2056-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2056-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2056-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2056-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2056-121">See also</span></span>

- [<span data-ttu-id="f2056-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2056-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f2056-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2056-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

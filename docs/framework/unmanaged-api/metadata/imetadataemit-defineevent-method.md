---
title: IMetaDataEmit::DefineEvent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175852"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="99f5a-102">IMetaDataEmit::DefineEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="99f5a-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="99f5a-103">지정된 메타데이터 시그니처가 있는 이벤트에 대한 정의를 만들고 해당 이벤트 정의에 대한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f5a-104">구문</span><span class="sxs-lookup"><span data-stu-id="99f5a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f5a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99f5a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="99f5a-106">【인】 대상 클래스 또는 인터페이스에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="99f5a-107">이것은 또는 `mdTypeDefNil` `mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="99f5a-108">【인】 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="99f5a-109">【인】 이벤트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="99f5a-110">【인】 이벤트 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-110">[in] The token for the event class.</span></span> <span data-ttu-id="99f5a-111">이것은 `mdTypeDef`. `mdTypeRef` `mdTokenNil`</span><span class="sxs-lookup"><span data-stu-id="99f5a-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="99f5a-112">【인】 이벤트를 구독하는 데 사용되는 메서드 또는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="99f5a-113">【인】 이벤트 구독을 취소하거나 null에 사용되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="99f5a-114">【인】 이벤트를 발생시키기 위해 파생 클래스에서 사용하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="99f5a-115">【인】 이벤트와 연결된 다른 메서드에 대한 토큰 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="99f5a-116">배열은 토큰으로 `mdMethodDefNil` 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="99f5a-117">【아웃】 이벤트에 할당된 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5a-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f5a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99f5a-118">Requirements</span></span>  
 <span data-ttu-id="99f5a-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99f5a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f5a-120">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="99f5a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99f5a-121">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="99f5a-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99f5a-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99f5a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f5a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99f5a-123">See also</span></span>

- [<span data-ttu-id="99f5a-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99f5a-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="99f5a-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99f5a-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

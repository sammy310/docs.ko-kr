---
description: IMetaDataEmit::D efineEvent 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: f96f3a5b2ed16ba83223312af82cac7688cebfa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753473"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="9e8ba-103">IMetaDataEmit::DefineEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="9e8ba-103">IMetaDataEmit::DefineEvent Method</span></span>

<span data-ttu-id="9e8ba-104">지정 된 메타 데이터 시그니처를 사용 하 여 이벤트에 대 한 정의를 만들고 해당 이벤트 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-104">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e8ba-105">구문</span><span class="sxs-lookup"><span data-stu-id="9e8ba-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9e8ba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e8ba-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="9e8ba-107">진행 대상 클래스 또는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-107">[in] The token for the target class or interface.</span></span> <span data-ttu-id="9e8ba-108">이는 `mdTypeDef` 또는 토큰입니다 `mdTypeDefNil` .</span><span class="sxs-lookup"><span data-stu-id="9e8ba-108">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="9e8ba-109">진행 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-109">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="9e8ba-110">진행 이벤트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-110">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="9e8ba-111">진행 이벤트 클래스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-111">[in] The token for the event class.</span></span> <span data-ttu-id="9e8ba-112">`mdTypeDef`, `mdTypeRef` 또는 `mdTokenNil` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-112">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="9e8ba-113">진행 이벤트를 구독 하는 데 사용 되는 메서드 이거나 null입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-113">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="9e8ba-114">진행 이벤트를 구독 취소 하는 데 사용 되는 메서드 이거나 null입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-114">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="9e8ba-115">진행 파생 클래스에서 이벤트를 발생 시키는 데 사용 되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-115">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="9e8ba-116">진행 이벤트와 연결 된 다른 메서드에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-116">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="9e8ba-117">배열은 토큰과 함께 종료 됩니다 `mdMethodDefNil` .</span><span class="sxs-lookup"><span data-stu-id="9e8ba-117">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="9e8ba-118">제한이 이벤트에 할당 된 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-118">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e8ba-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e8ba-119">Requirements</span></span>  

 <span data-ttu-id="9e8ba-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e8ba-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="9e8ba-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e8ba-122">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e8ba-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e8ba-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8ba-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8ba-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e8ba-124">See also</span></span>

- [<span data-ttu-id="9e8ba-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e8ba-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9e8ba-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e8ba-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

---
description: '자세히 알아보기: IMetaDataImport:: EnumMethodSemantics 메서드'
title: IMetaDataImport::EnumMethodSemantics 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: 9819afb2d7974e9f705c6ff665d3414eade0ab90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728254"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="03a5b-103">IMetaDataImport::EnumMethodSemantics 메서드</span><span class="sxs-lookup"><span data-stu-id="03a5b-103">IMetaDataImport::EnumMethodSemantics Method</span></span>

<span data-ttu-id="03a5b-104">지정한 메서드와 관련된 속성 및 속성 변경 이벤트를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-104">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a5b-105">구문</span><span class="sxs-lookup"><span data-stu-id="03a5b-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03a5b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03a5b-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="03a5b-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="03a5b-108">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-108">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="03a5b-109">진행 열거형의 범위를 제한 하는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-109">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="03a5b-110">제한이 이벤트 또는 속성을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-110">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="03a5b-111">[in] `rEventProp` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-111">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="03a5b-112">제한이 에서 반환 되는 이벤트 또는 속성의 수입니다 `rEventProp` .</span><span class="sxs-lookup"><span data-stu-id="03a5b-112">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03a5b-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="03a5b-113">Return Value</span></span>  
  
|<span data-ttu-id="03a5b-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03a5b-114">HRESULT</span></span>|<span data-ttu-id="03a5b-115">설명</span><span class="sxs-lookup"><span data-stu-id="03a5b-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="03a5b-116">`EnumMethodSemantics` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-116">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="03a5b-117">열거할 이벤트 또는 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-117">There are no events or properties to enumerate.</span></span> <span data-ttu-id="03a5b-118">이 경우는 `pcEventProp` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-118">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03a5b-119">설명</span><span class="sxs-lookup"><span data-stu-id="03a5b-119">Remarks</span></span>  

 <span data-ttu-id="03a5b-120">대부분의 공용 언어 런타임 형식은  속성과 `Changed` 관련 된 속성 이벤트와 `On` *속성* `Changed` 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-120">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="03a5b-121">예를 들어 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 형식은 <xref:System.Windows.Forms.Control.Font%2A> 속성, <xref:System.Windows.Forms.Control.FontChanged> 이벤트 및 메서드를 정의 합니다 <xref:System.Windows.Forms.Control.OnFontChanged%2A> .</span><span class="sxs-lookup"><span data-stu-id="03a5b-121">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="03a5b-122">속성의 set 접근자 메서드가 <xref:System.Windows.Forms.Control.Font%2A> 메서드를 호출 하면이 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 메서드는 이벤트를 발생 시킵니다 <xref:System.Windows.Forms.Control.FontChanged> .</span><span class="sxs-lookup"><span data-stu-id="03a5b-122">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="03a5b-123">에서 MethodDef를 `EnumMethodSemantics` 사용 하 여를 호출 하 여 <xref:System.Windows.Forms.Control.OnFontChanged%2A> <xref:System.Windows.Forms.Control.Font%2A> 속성 및 이벤트에 대 한 참조를 가져옵니다 <xref:System.Windows.Forms.Control.FontChanged> .</span><span class="sxs-lookup"><span data-stu-id="03a5b-123">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03a5b-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03a5b-124">Requirements</span></span>  

 <span data-ttu-id="03a5b-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03a5b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03a5b-126">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="03a5b-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03a5b-127">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a5b-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03a5b-128">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03a5b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a5b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03a5b-129">See also</span></span>

- [<span data-ttu-id="03a5b-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03a5b-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="03a5b-131">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03a5b-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

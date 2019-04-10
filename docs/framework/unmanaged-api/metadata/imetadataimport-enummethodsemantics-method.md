---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16cfa6df6251cd67860155cb8092e77a835eaaef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223272"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="3efbe-102">IMetaDataImport::EnumMethodSemantics 메서드</span><span class="sxs-lookup"><span data-stu-id="3efbe-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="3efbe-103">지정한 메서드와 관련된 속성 및 속성 변경 이벤트를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3efbe-104">구문</span><span class="sxs-lookup"><span data-stu-id="3efbe-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3efbe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3efbe-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3efbe-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3efbe-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="3efbe-108">[in] 열거형의 범위를 제한 하는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="3efbe-109">[out] 이벤트 또는 속성을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3efbe-110">[in] `rEventProp` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="3efbe-111">[out] 이벤트 또는 속성에서 반환 된 수가 `rEventProp`합니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3efbe-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="3efbe-112">Return Value</span></span>  
  
|<span data-ttu-id="3efbe-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3efbe-113">HRESULT</span></span>|<span data-ttu-id="3efbe-114">설명</span><span class="sxs-lookup"><span data-stu-id="3efbe-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` <span data-ttu-id="3efbe-115">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3efbe-116">이벤트 또는 속성 열거에 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="3efbe-117">이런 경우 `pcEventProp` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3efbe-118">설명</span><span class="sxs-lookup"><span data-stu-id="3efbe-118">Remarks</span></span>  
 <span data-ttu-id="3efbe-119">여러 공용 언어 런타임 형식 정의 *속성* `Changed` 이벤트와 `On` *속성* `Changed` 해당 속성에 관련 된 메서드.</span><span class="sxs-lookup"><span data-stu-id="3efbe-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="3efbe-120">예를 들어, 합니다 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 형식 정의 <xref:System.Windows.Forms.Control.Font%2A> 속성을 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 및 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="3efbe-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="3efbe-121">set 접근자 메서드에 <xref:System.Windows.Forms.Control.Font%2A> 속성 호출 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 발생 하는 메서드는 <xref:System.Windows.Forms.Control.FontChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="3efbe-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="3efbe-122">호출 하는 것 `EnumMethodSemantics` 사용에 대 한 MethodDef <xref:System.Windows.Forms.Control.OnFontChanged%2A> 에 대 한 참조를 가져오려고 합니다 <xref:System.Windows.Forms.Control.Font%2A> 속성 및 <xref:System.Windows.Forms.Control.FontChanged> 이벤트.</span><span class="sxs-lookup"><span data-stu-id="3efbe-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3efbe-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3efbe-123">Requirements</span></span>  
 <span data-ttu-id="3efbe-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3efbe-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3efbe-125">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3efbe-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3efbe-126">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3efbe-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3efbe-127">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="3efbe-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3efbe-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="3efbe-128">See also</span></span>

- [<span data-ttu-id="3efbe-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3efbe-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3efbe-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3efbe-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

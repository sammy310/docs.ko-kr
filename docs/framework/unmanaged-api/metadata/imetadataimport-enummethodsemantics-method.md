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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175462"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="51970-102">IMetaDataImport::EnumMethodSemantics 메서드</span><span class="sxs-lookup"><span data-stu-id="51970-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="51970-103">지정한 메서드와 관련된 속성 및 속성 변경 이벤트를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="51970-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51970-104">구문</span><span class="sxs-lookup"><span data-stu-id="51970-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51970-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51970-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="51970-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51970-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="51970-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.</span><span class="sxs-lookup"><span data-stu-id="51970-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="51970-108">【인】 열거형의 범위를 제한하는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="51970-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="51970-109">【아웃】 이벤트 또는 속성을 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="51970-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="51970-110">[in] `rEventProp` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51970-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="51970-111">【아웃】 에서 반환되는 이벤트 또는 `rEventProp`속성 의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="51970-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51970-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="51970-112">Return Value</span></span>  
  
|<span data-ttu-id="51970-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51970-113">HRESULT</span></span>|<span data-ttu-id="51970-114">Description</span><span class="sxs-lookup"><span data-stu-id="51970-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="51970-115">`EnumMethodSemantics`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="51970-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="51970-116">등록할 이벤트 나 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51970-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="51970-117">이 경우 `pcEventProp` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="51970-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51970-118">설명</span><span class="sxs-lookup"><span data-stu-id="51970-118">Remarks</span></span>  
 <span data-ttu-id="51970-119">많은 공통 언어 런타임 형식은 *속성과* `Changed` 관련된 속성 이벤트 및 `On` *속성* `Changed` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51970-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="51970-120">예를 들어 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 형식은 <xref:System.Windows.Forms.Control.Font%2A> 속성, 이벤트 <xref:System.Windows.Forms.Control.FontChanged> 및 메서드를 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51970-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="51970-121"><xref:System.Windows.Forms.Control.Font%2A> 속성 호출 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 메서드의 설정 된 접근자 메서드차례로 이벤트를 발생 합니다. <xref:System.Windows.Forms.Control.FontChanged></span><span class="sxs-lookup"><span data-stu-id="51970-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="51970-122">속성 및 `EnumMethodSemantics` 이벤트에 대 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 한 참조를 얻으려면 MethodDef를 사용 하 여 호출 합니다. <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.Font%2A></span><span class="sxs-lookup"><span data-stu-id="51970-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51970-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51970-123">Requirements</span></span>  
 <span data-ttu-id="51970-124">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51970-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51970-125">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="51970-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51970-126">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="51970-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51970-127">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51970-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51970-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51970-128">See also</span></span>

- [<span data-ttu-id="51970-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51970-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="51970-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51970-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

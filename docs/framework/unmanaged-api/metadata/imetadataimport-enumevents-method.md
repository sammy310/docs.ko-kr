---
title: IMetaDataImport::EnumEvents 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
ms.openlocfilehash: bd50d63b1f7080f510c29f90979b7b36242af1c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177365"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="cd0ee-102">IMetaDataImport::EnumEvents 메서드</span><span class="sxs-lookup"><span data-stu-id="cd0ee-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="cd0ee-103">지정한 TypeDef 토큰에 대한 이벤트 정의 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd0ee-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd0ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd0ee-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cd0ee-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="cd0ee-107">【인】 이벤트 정의를 지글거칠 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="cd0ee-108">【아웃】 반환된 이벤트의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cd0ee-109">[in] `rEvents` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="cd0ee-110">【아웃】 에서 반환되는 이벤트의 `rEvents`실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd0ee-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="cd0ee-111">Return Value</span></span>  
  
|<span data-ttu-id="cd0ee-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd0ee-112">HRESULT</span></span>|<span data-ttu-id="cd0ee-113">Description</span><span class="sxs-lookup"><span data-stu-id="cd0ee-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cd0ee-114">`EnumEvents`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cd0ee-115">등록할 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-115">There are no events to enumerate.</span></span> <span data-ttu-id="cd0ee-116">이 경우 `pcEvents` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd0ee-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd0ee-117">Requirements</span></span>  
 <span data-ttu-id="cd0ee-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd0ee-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd0ee-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="cd0ee-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd0ee-120">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cd0ee-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd0ee-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd0ee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0ee-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd0ee-122">See also</span></span>

- [<span data-ttu-id="cd0ee-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd0ee-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cd0ee-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd0ee-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

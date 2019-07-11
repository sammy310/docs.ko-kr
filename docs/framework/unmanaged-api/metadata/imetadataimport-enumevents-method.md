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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f3d74830de0541ec789081c47352beca8d81d74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780706"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="84dbc-102">IMetaDataImport::EnumEvents 메서드</span><span class="sxs-lookup"><span data-stu-id="84dbc-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="84dbc-103">지정한 TypeDef 토큰에 대한 이벤트 정의 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84dbc-104">구문</span><span class="sxs-lookup"><span data-stu-id="84dbc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84dbc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84dbc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="84dbc-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="84dbc-107">[in] 열거할 수는 이벤트 정의가 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="84dbc-108">[out] 반환 된 이벤트의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="84dbc-109">[in] `rEvents` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="84dbc-110">[out] 반환 되는 이벤트 수가 실제 `rEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84dbc-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="84dbc-111">Return Value</span></span>  
  
|<span data-ttu-id="84dbc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84dbc-112">HRESULT</span></span>|<span data-ttu-id="84dbc-113">Description</span><span class="sxs-lookup"><span data-stu-id="84dbc-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="84dbc-114">`EnumEvents` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="84dbc-115">열거에 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-115">There are no events to enumerate.</span></span> <span data-ttu-id="84dbc-116">이런 경우 `pcEvents` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="84dbc-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84dbc-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84dbc-117">Requirements</span></span>  
 <span data-ttu-id="84dbc-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="84dbc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84dbc-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="84dbc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84dbc-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="84dbc-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84dbc-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84dbc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84dbc-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="84dbc-122">See also</span></span>

- [<span data-ttu-id="84dbc-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84dbc-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="84dbc-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84dbc-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

---
description: 'IMetaDataImport:: EnumEvents 메서드에 대해 자세히 알아보세요.'
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
ms.openlocfilehash: e944c15a19314b315e01493836ce078fccc917eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799410"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="75779-103">IMetaDataImport::EnumEvents 메서드</span><span class="sxs-lookup"><span data-stu-id="75779-103">IMetaDataImport::EnumEvents Method</span></span>

<span data-ttu-id="75779-104">지정한 TypeDef 토큰에 대한 이벤트 정의 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="75779-104">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75779-105">구문</span><span class="sxs-lookup"><span data-stu-id="75779-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75779-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75779-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="75779-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="75779-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="75779-108">진행 이벤트 정의가 열거 될 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="75779-108">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="75779-109">제한이 반환 된 이벤트의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="75779-109">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="75779-110">[in] `rEvents` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="75779-110">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="75779-111">제한이 에서 반환 되는 실제 이벤트 수 `rEvents` 입니다.</span><span class="sxs-lookup"><span data-stu-id="75779-111">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75779-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="75779-112">Return Value</span></span>  
  
|<span data-ttu-id="75779-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75779-113">HRESULT</span></span>|<span data-ttu-id="75779-114">설명</span><span class="sxs-lookup"><span data-stu-id="75779-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="75779-115">`EnumEvents` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75779-115">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="75779-116">열거할 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75779-116">There are no events to enumerate.</span></span> <span data-ttu-id="75779-117">이 경우는 `pcEvents` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="75779-117">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75779-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75779-118">Requirements</span></span>  

 <span data-ttu-id="75779-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75779-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75779-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="75779-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75779-121">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75779-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75779-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75779-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75779-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75779-123">See also</span></span>

- [<span data-ttu-id="75779-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75779-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="75779-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75779-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

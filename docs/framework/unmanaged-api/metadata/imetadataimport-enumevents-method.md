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
ms.openlocfilehash: 4faf8646b81f92ddf65eff15fdc610d275b37864
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440016"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="27121-102">IMetaDataImport::EnumEvents 메서드</span><span class="sxs-lookup"><span data-stu-id="27121-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="27121-103">지정한 TypeDef 토큰에 대한 이벤트 정의 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="27121-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27121-104">구문</span><span class="sxs-lookup"><span data-stu-id="27121-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27121-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27121-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="27121-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27121-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="27121-107">진행 이벤트 정의가 열거 될 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="27121-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="27121-108">제한이 반환 된 이벤트의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="27121-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="27121-109">[in] `rEvents` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="27121-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="27121-110">제한이 `rEvents`에서 반환 되는 실제 이벤트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="27121-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27121-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="27121-111">Return Value</span></span>  
  
|<span data-ttu-id="27121-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27121-112">HRESULT</span></span>|<span data-ttu-id="27121-113">설명</span><span class="sxs-lookup"><span data-stu-id="27121-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="27121-114">`EnumEvents` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27121-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="27121-115">열거할 이벤트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27121-115">There are no events to enumerate.</span></span> <span data-ttu-id="27121-116">이 경우 `pcEvents`은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="27121-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27121-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27121-117">Requirements</span></span>  
 <span data-ttu-id="27121-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27121-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27121-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="27121-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27121-120">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27121-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27121-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27121-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27121-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="27121-122">See also</span></span>

- [<span data-ttu-id="27121-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27121-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="27121-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27121-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

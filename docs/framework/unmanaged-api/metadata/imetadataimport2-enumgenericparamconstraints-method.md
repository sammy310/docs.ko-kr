---
title: IMetaDataImport2::EnumGenericParamConstraints 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f66b0145dbaece7292d2ccad169a97fbb10b6d11
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186684"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="ba81f-102">IMetaDataImport2::EnumGenericParamConstraints 메서드</span><span class="sxs-lookup"><span data-stu-id="ba81f-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="ba81f-103">제네릭 매개 변수 제약 조건이 지정된 된 토큰을 나타내는 제네릭 매개 변수를 사용 하 여 연결의 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba81f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba81f-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba81f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba81f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ba81f-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="ba81f-107">[in]   열거할 수 있는 제약 조건은 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="ba81f-108">[out] 제네릭 매개 변수 제약 조건 열거의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ba81f-109">[in]   에 배치 하는 토큰의 요청 된 최대 `rGenericParamConstraints`합니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="ba81f-110">[out] 토큰의 수에 대 한 포인터에 배치 `rGenericParamConstraints`합니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba81f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="ba81f-111">Return Value</span></span>  
  
|<span data-ttu-id="ba81f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba81f-112">HRESULT</span></span>|<span data-ttu-id="ba81f-113">설명</span><span class="sxs-lookup"><span data-stu-id="ba81f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba81f-114">`EnumGenericParameterConstraints` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ba81f-115">`phEnum` 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="ba81f-116">이 경우 `pcGenericParameterConstraints` 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba81f-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba81f-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba81f-117">Requirements</span></span>  
 <span data-ttu-id="ba81f-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba81f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba81f-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba81f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba81f-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ba81f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba81f-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba81f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba81f-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba81f-122">See also</span></span>

- [<span data-ttu-id="ba81f-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba81f-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="ba81f-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba81f-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

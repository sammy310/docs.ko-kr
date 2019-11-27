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
ms.openlocfilehash: d1683965193801dbdee038ab06366178891fd978
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426731"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="36685-102">IMetaDataImport2::EnumGenericParamConstraints 메서드</span><span class="sxs-lookup"><span data-stu-id="36685-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="36685-103">지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 제네릭 매개 변수 제약 조건의 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="36685-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36685-104">구문</span><span class="sxs-lookup"><span data-stu-id="36685-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36685-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36685-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="36685-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="36685-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="36685-107">진행   제약 조건이 열거 될 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="36685-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="36685-108">제한이 열거할 제네릭 매개 변수 제약 조건의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="36685-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="36685-109">진행   `rGenericParamConstraints`에 저장할 요청 된 최대 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="36685-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="36685-110">제한이 `rGenericParamConstraints`에 배치 된 토큰 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="36685-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36685-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="36685-111">Return Value</span></span>  
  
|<span data-ttu-id="36685-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36685-112">HRESULT</span></span>|<span data-ttu-id="36685-113">설명</span><span class="sxs-lookup"><span data-stu-id="36685-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="36685-114">`EnumGenericParameterConstraints` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36685-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="36685-115">`phEnum`에는 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36685-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="36685-116">이 경우 `pcGenericParameterConstraints`은 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36685-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36685-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36685-117">Requirements</span></span>  
 <span data-ttu-id="36685-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36685-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36685-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="36685-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36685-120">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36685-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36685-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36685-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36685-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36685-122">See also</span></span>

- [<span data-ttu-id="36685-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36685-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="36685-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36685-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

---
description: '자세히 알아보기: IMetaDataImport2:: EnumGenericParamConstraints 메서드'
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
ms.openlocfilehash: d7ee44059796a943411750b66f5b45034f871a0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677550"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="bc4e7-103">IMetaDataImport2::EnumGenericParamConstraints 메서드</span><span class="sxs-lookup"><span data-stu-id="bc4e7-103">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>

<span data-ttu-id="bc4e7-104">지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 제네릭 매개 변수 제약 조건의 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-104">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc4e7-105">구문</span><span class="sxs-lookup"><span data-stu-id="bc4e7-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc4e7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc4e7-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="bc4e7-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="bc4e7-108">진행   제약 조건이 열거 될 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-108">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="bc4e7-109">제한이 열거할 제네릭 매개 변수 제약 조건의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-109">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bc4e7-110">진행   에 저장할 요청 된 최대 토큰 수 `rGenericParamConstraints` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-110">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="bc4e7-111">제한이 에 배치 된 토큰 수에 대 한 포인터 `rGenericParamConstraints` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-111">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc4e7-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="bc4e7-112">Return Value</span></span>  
  
|<span data-ttu-id="bc4e7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc4e7-113">HRESULT</span></span>|<span data-ttu-id="bc4e7-114">설명</span><span class="sxs-lookup"><span data-stu-id="bc4e7-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bc4e7-115">`EnumGenericParameterConstraints` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-115">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bc4e7-116">`phEnum` 에는 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="bc4e7-117">이 경우 `pcGenericParameterConstraints` 은 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-117">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc4e7-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc4e7-118">Requirements</span></span>  

 <span data-ttu-id="bc4e7-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc4e7-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="bc4e7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc4e7-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc4e7-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc4e7-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc4e7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4e7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc4e7-123">See also</span></span>

- [<span data-ttu-id="bc4e7-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc4e7-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="bc4e7-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc4e7-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

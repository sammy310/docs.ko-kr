---
title: IMetaDataImport2::EnumGenericParams 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44e1dc93580c6c4190ca04826824b519c67ee4e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494932"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="0ddc1-102">IMetaDataImport2::EnumGenericParams 메서드</span><span class="sxs-lookup"><span data-stu-id="0ddc1-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="0ddc1-103">토큰 제네릭 매개 변수 토큰을 지정 된 형식 정의 또는 MethodDef 연결 된 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddc1-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ddc1-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ddc1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ddc1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0ddc1-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="0ddc1-107">[in] 제네릭 매개 변수를 가진 열거 하는 TypeDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="0ddc1-108">[out] 열거 하는 제네릭 매개 변수의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0ddc1-109">[in] 에 배치 하는 토큰의 요청 된 최대 `rGenericParams`합니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="0ddc1-110">[out] 반환 된 토큰 수 있는 `rGenericParams`합니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ddc1-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="0ddc1-111">Return Value</span></span>  
  
|<span data-ttu-id="0ddc1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ddc1-112">HRESULT</span></span>|<span data-ttu-id="0ddc1-113">설명</span><span class="sxs-lookup"><span data-stu-id="0ddc1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0ddc1-114">`EnumGenericParams` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0ddc1-115">`phEnum` 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="0ddc1-116">이 경우 `pcGenericParams` 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ddc1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ddc1-117">Requirements</span></span>  
 <span data-ttu-id="0ddc1-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ddc1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddc1-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ddc1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ddc1-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0ddc1-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ddc1-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddc1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddc1-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ddc1-122">See also</span></span>
- [<span data-ttu-id="0ddc1-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ddc1-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="0ddc1-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ddc1-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

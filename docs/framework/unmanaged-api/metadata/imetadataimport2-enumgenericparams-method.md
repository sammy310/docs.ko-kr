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
ms.openlocfilehash: 55709e79cd8bdb36fe1e32ee8a699fccb1b1bbc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175306"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="b9653-102">IMetaDataImport2::EnumGenericParams 메서드</span><span class="sxs-lookup"><span data-stu-id="b9653-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="b9653-103">지정된 TypeDef 또는 MethodDef 토큰과 연결된 일반 매개 변수 토큰 배열에 대한 열거기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9653-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9653-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9653-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9653-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b9653-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="b9653-107">【인】 제네릭 매개 변수를 개명할 TypeDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="b9653-108">【아웃】 열거할 제네릭 매개 변수의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b9653-109">【인】 에 배치할 요청된 최대 `rGenericParams`토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="b9653-110">【아웃】 에 `rGenericParams`배치된 토큰의 반환 된 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9653-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="b9653-111">Return Value</span></span>  
  
|<span data-ttu-id="b9653-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9653-112">HRESULT</span></span>|<span data-ttu-id="b9653-113">Description</span><span class="sxs-lookup"><span data-stu-id="b9653-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b9653-114">`EnumGenericParams`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b9653-115">`phEnum`멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="b9653-116">이 경우 `pcGenericParams` 0(0)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9653-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9653-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9653-117">Requirements</span></span>  
 <span data-ttu-id="b9653-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9653-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9653-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="b9653-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9653-120">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b9653-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9653-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9653-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9653-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9653-122">See also</span></span>

- [<span data-ttu-id="b9653-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9653-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="b9653-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9653-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

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
ms.openlocfilehash: 093e3edf0a3c06222ebc56a4876fca08d1b7578f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490731"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="40a76-102">IMetaDataImport2::EnumGenericParams 메서드</span><span class="sxs-lookup"><span data-stu-id="40a76-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="40a76-103">지정 된 TypeDef 또는 MethodDef 토큰과 연결 된 제네릭 매개 변수 토큰의 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a76-104">구문</span><span class="sxs-lookup"><span data-stu-id="40a76-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40a76-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40a76-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="40a76-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="40a76-107">진행 제네릭 매개 변수를 열거할 TypeDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="40a76-108">제한이 열거할 제네릭 매개 변수의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="40a76-109">진행 에 저장할 요청 된 최대 토큰 수 `rGenericParams` 입니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="40a76-110">제한이 에 배치 된 반환 된 토큰 수 `rGenericParams` 입니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40a76-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="40a76-111">Return Value</span></span>  
  
|<span data-ttu-id="40a76-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40a76-112">HRESULT</span></span>|<span data-ttu-id="40a76-113">설명</span><span class="sxs-lookup"><span data-stu-id="40a76-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="40a76-114">`EnumGenericParams`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="40a76-115">`phEnum`에는 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="40a76-116">이 경우 `pcGenericParams` 은 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40a76-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40a76-117">Requirements</span></span>  
 <span data-ttu-id="40a76-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40a76-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40a76-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="40a76-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40a76-120">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40a76-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40a76-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40a76-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a76-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40a76-122">See also</span></span>

- [<span data-ttu-id="40a76-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40a76-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="40a76-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40a76-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

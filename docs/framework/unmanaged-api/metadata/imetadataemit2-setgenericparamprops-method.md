---
title: IMetaDataEmit2::SetGenericParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 8858e692d66f7b34a66334bd4e8b906dd12962ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701993"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="fac43-102">IMetaDataEmit2::SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="fac43-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>

<span data-ttu-id="fac43-103">지정 된 토큰이 참조 하는 제네릭 매개 변수 정의에 대 한 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac43-104">구문</span><span class="sxs-lookup"><span data-stu-id="fac43-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fac43-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fac43-105">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="fac43-106">진행 값을 설정할 제네릭 매개 변수 정의에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="fac43-107">진행 제네릭 매개 변수의 형식을 설명 하는 [Corgenericparamattr](corgenericparamattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-107">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="fac43-108">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="fac43-108">[in] Optional.</span></span> <span data-ttu-id="fac43-109">값을 설정할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="fac43-110">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="fac43-111">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="fac43-111">[in] Optional.</span></span> <span data-ttu-id="fac43-112">0으로 끝나는 형식의 제약 조건 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="fac43-113">배열 멤버는 `mdTypeDef` , `mdTypeRef` 또는 `mdTypeSpec` 메타 데이터 토큰 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac43-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fac43-114">Requirements</span></span>  

 <span data-ttu-id="fac43-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fac43-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac43-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="fac43-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fac43-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac43-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fac43-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac43-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac43-119">참조</span><span class="sxs-lookup"><span data-stu-id="fac43-119">See also</span></span>

- [<span data-ttu-id="fac43-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac43-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="fac43-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac43-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)

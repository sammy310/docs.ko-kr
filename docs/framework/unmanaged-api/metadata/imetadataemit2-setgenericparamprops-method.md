---
description: '자세히 알아보기: IMetaDataEmit2:: SetGenericParamProps 메서드'
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
ms.openlocfilehash: 9c6946bbd301450203bc6fb2b1202352119dc792
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771654"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="efb2d-103">IMetaDataEmit2::SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="efb2d-103">IMetaDataEmit2::SetGenericParamProps Method</span></span>

<span data-ttu-id="efb2d-104">지정 된 토큰이 참조 하는 제네릭 매개 변수 정의에 대 한 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-104">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb2d-105">구문</span><span class="sxs-lookup"><span data-stu-id="efb2d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb2d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efb2d-106">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="efb2d-107">진행 값을 설정할 제네릭 매개 변수 정의에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-107">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="efb2d-108">진행 제네릭 매개 변수의 형식을 설명 하는 [Corgenericparamattr](corgenericparamattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-108">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="efb2d-109">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="efb2d-109">[in] Optional.</span></span> <span data-ttu-id="efb2d-110">값을 설정할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-110">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="efb2d-111">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-111">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="efb2d-112">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="efb2d-112">[in] Optional.</span></span> <span data-ttu-id="efb2d-113">0으로 끝나는 형식의 제약 조건 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-113">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="efb2d-114">배열 멤버는 `mdTypeDef` , `mdTypeRef` 또는 `mdTypeSpec` 메타 데이터 토큰 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-114">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb2d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efb2d-115">Requirements</span></span>  

 <span data-ttu-id="efb2d-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb2d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb2d-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="efb2d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efb2d-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb2d-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efb2d-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb2d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb2d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efb2d-120">See also</span></span>

- [<span data-ttu-id="efb2d-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efb2d-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="efb2d-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efb2d-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)

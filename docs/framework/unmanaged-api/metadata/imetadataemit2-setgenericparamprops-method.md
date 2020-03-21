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
ms.openlocfilehash: fd7f149e806727d849cdceb3ffbc5dc7392fcf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177415"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="75a97-102">IMetaDataEmit2::SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="75a97-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="75a97-103">지정된 토큰에서 참조하는 제네릭 매개 변수 정의에 대한 속성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="75a97-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a97-104">구문</span><span class="sxs-lookup"><span data-stu-id="75a97-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75a97-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75a97-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="75a97-106">【인】 값을 설정할 제네릭 매개 변수 정의에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="75a97-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="75a97-107">【인】 제네릭 매개 변수에 대한 형식을 설명하는 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="75a97-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="75a97-108">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="75a97-108">[in] Optional.</span></span> <span data-ttu-id="75a97-109">값을 설정할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75a97-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="75a97-110">【인】 향후 확장성을 위해 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75a97-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="75a97-111">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="75a97-111">[in] Optional.</span></span> <span data-ttu-id="75a97-112">형식 제약 조건의 0-종단 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="75a97-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="75a97-113">배열 멤버는 `mdTypeDef`. `mdTypeRef` `mdTypeSpec`</span><span class="sxs-lookup"><span data-stu-id="75a97-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75a97-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75a97-114">Requirements</span></span>  
 <span data-ttu-id="75a97-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75a97-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75a97-116">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="75a97-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75a97-117">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="75a97-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75a97-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75a97-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a97-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75a97-119">See also</span></span>

- [<span data-ttu-id="75a97-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75a97-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="75a97-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75a97-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

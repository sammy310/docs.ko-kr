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
ms.openlocfilehash: 7a93bbe0d7a9d9e6ff7505bbc215efa79176ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440443"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="3a9b2-102">IMetaDataEmit2::SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="3a9b2-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="3a9b2-103">Sets property values for the generic parameter definition referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a9b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a9b2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a9b2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a9b2-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="3a9b2-106">[in] The token for the generic parameter definition for which to set values.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="3a9b2-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="3a9b2-108">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="3a9b2-108">[in] Optional.</span></span> <span data-ttu-id="3a9b2-109">The name of the parameter for which to set values.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="3a9b2-110">[in] Reserved for future extensibility.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="3a9b2-111">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="3a9b2-111">[in] Optional.</span></span> <span data-ttu-id="3a9b2-112">A zero-terminated array of type constraints.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="3a9b2-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a9b2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a9b2-114">Requirements</span></span>  
 <span data-ttu-id="3a9b2-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a9b2-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a9b2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a9b2-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a9b2-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a9b2-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a9b2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9b2-119">참조</span><span class="sxs-lookup"><span data-stu-id="3a9b2-119">See also</span></span>

- [<span data-ttu-id="3a9b2-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a9b2-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3a9b2-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a9b2-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)

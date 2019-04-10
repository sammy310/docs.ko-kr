---
title: IMetaDataImport::EnumProperties 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 410fd7a702d3aa3812b4ea053c43fdaa507a474a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176038"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="65dc2-102">IMetaDataImport::EnumProperties 메서드</span><span class="sxs-lookup"><span data-stu-id="65dc2-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="65dc2-103">지정한 TypeDef 토큰이 참조하는 형식의 속성을 나타내는 PropertyDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65dc2-104">구문</span><span class="sxs-lookup"><span data-stu-id="65dc2-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65dc2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65dc2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="65dc2-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="65dc2-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="65dc2-108">[in] 열거 속성을 사용 하 여 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="65dc2-109">[out] PropertyDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="65dc2-110">[in] `rProperties` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="65dc2-111">[out] PropertyDef 토큰에서 반환 된 수가 `rProperties`합니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65dc2-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="65dc2-112">Return Value</span></span>  
  
|<span data-ttu-id="65dc2-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65dc2-113">HRESULT</span></span>|<span data-ttu-id="65dc2-114">설명</span><span class="sxs-lookup"><span data-stu-id="65dc2-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumProperties` <span data-ttu-id="65dc2-115">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="65dc2-116">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="65dc2-117">이런 경우 `pcProperties` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="65dc2-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65dc2-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65dc2-118">Requirements</span></span>  
 <span data-ttu-id="65dc2-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="65dc2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65dc2-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="65dc2-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65dc2-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="65dc2-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="65dc2-122">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="65dc2-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65dc2-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="65dc2-123">See also</span></span>

- [<span data-ttu-id="65dc2-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65dc2-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="65dc2-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65dc2-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

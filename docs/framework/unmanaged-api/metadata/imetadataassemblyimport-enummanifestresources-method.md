---
title: IMetaDataAssemblyImport::EnumManifestResources 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a13e750029fed2f2261064dd69d6c1d800d59989
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473905"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="73cdb-102">IMetaDataAssemblyImport::EnumManifestResources 메서드</span><span class="sxs-lookup"><span data-stu-id="73cdb-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="73cdb-103">현재 어셈블리 매니페스트에서 참조 하는 리소스에 대 한 열거자에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73cdb-104">구문</span><span class="sxs-lookup"><span data-stu-id="73cdb-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="73cdb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73cdb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="73cdb-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="73cdb-107">Null 이어야 합니다 경우이 값은 `EnumManifestResources` 처음으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="73cdb-108">[out] 배열을 저장 하는 데는 `mdManifestResource` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="73cdb-109">[in] 최대 `mdManifestResource` 에 배치할 수 있는 토큰 `rManifestResources`합니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="73cdb-110">[out] 수가 `mdManifestResource` 토큰에 실제로 배치 `rManifestResources`합니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73cdb-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="73cdb-111">Return Value</span></span>  
  
|<span data-ttu-id="73cdb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73cdb-112">HRESULT</span></span>|<span data-ttu-id="73cdb-113">설명</span><span class="sxs-lookup"><span data-stu-id="73cdb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="73cdb-114">`EnumManifestResources` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="73cdb-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="73cdb-116">이 경우 `pcTokens` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cdb-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73cdb-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73cdb-117">Requirements</span></span>  
 <span data-ttu-id="73cdb-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="73cdb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73cdb-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73cdb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73cdb-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="73cdb-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73cdb-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73cdb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73cdb-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="73cdb-122">See also</span></span>
- [<span data-ttu-id="73cdb-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73cdb-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

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
ms.openlocfilehash: 22141cf46a965c0624c076bd1d86d2624e5a09f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176021"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="cf252-102">IMetaDataAssemblyImport::EnumManifestResources 메서드</span><span class="sxs-lookup"><span data-stu-id="cf252-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="cf252-103">현재 어셈블리 매니페스트에서 참조되는 리소스에 대한 열거형에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf252-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf252-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="cf252-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf252-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cf252-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cf252-107">`EnumManifestResources` 메서드를 처음 호출할 때 null 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="cf252-108">【아웃】 메타데이터 토큰을 `mdManifestResource` 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cf252-109">【인】 에 `rManifestResources`배치할 `mdManifestResource` 수 있는 최대 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="cf252-110">【아웃】 실제로 에 `mdManifestResource` 배치된 토큰 `rManifestResources`수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf252-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="cf252-111">Return Value</span></span>  
  
|<span data-ttu-id="cf252-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf252-112">HRESULT</span></span>|<span data-ttu-id="cf252-113">Description</span><span class="sxs-lookup"><span data-stu-id="cf252-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cf252-114">`EnumManifestResources`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cf252-115">등록할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="cf252-116">이 경우 `pcTokens` 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf252-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf252-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf252-117">Requirements</span></span>  
 <span data-ttu-id="cf252-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf252-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf252-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="cf252-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf252-120">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="cf252-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf252-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf252-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf252-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf252-122">See also</span></span>

- [<span data-ttu-id="cf252-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf252-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

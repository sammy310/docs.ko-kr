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
ms.openlocfilehash: 560a6adf85fab7f421b86cba52224d5b1bfe1089
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006261"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="af735-102">IMetaDataAssemblyImport::EnumManifestResources 메서드</span><span class="sxs-lookup"><span data-stu-id="af735-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="af735-103">현재 어셈블리 매니페스트에서 참조 하는 리소스의 열거자에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af735-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af735-104">구문</span><span class="sxs-lookup"><span data-stu-id="af735-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="af735-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af735-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="af735-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="af735-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="af735-107">이 값은 메서드가 처음 호출 될 때 null 값 이어야 합니다 `EnumManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="af735-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="af735-108">제한이 메타 데이터 토큰을 저장 하는 데 사용 되는 배열 `mdManifestResource` 입니다.</span><span class="sxs-lookup"><span data-stu-id="af735-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="af735-109">진행 `mdManifestResource`에 배치할 수 있는 최대 토큰 수입니다 `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="af735-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="af735-110">제한이 `mdManifestResource`에 실제로 배치 된 토큰의 수 `rManifestResources` 입니다.</span><span class="sxs-lookup"><span data-stu-id="af735-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af735-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="af735-111">Return Value</span></span>  
  
|<span data-ttu-id="af735-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af735-112">HRESULT</span></span>|<span data-ttu-id="af735-113">Description</span><span class="sxs-lookup"><span data-stu-id="af735-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="af735-114">`EnumManifestResources`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af735-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="af735-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af735-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="af735-116">이 경우 `pcTokens` 는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af735-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af735-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af735-117">Requirements</span></span>  
 <span data-ttu-id="af735-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af735-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af735-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="af735-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af735-120">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af735-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af735-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af735-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af735-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af735-122">See also</span></span>

- [<span data-ttu-id="af735-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af735-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

---
description: '자세히 알아보기: IMetaDataAssemblyImport:: EnumManifestResources 메서드'
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
ms.openlocfilehash: ff819ebb575626af6049558656637e7fabcbc322
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677982"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="479ab-103">IMetaDataAssemblyImport::EnumManifestResources 메서드</span><span class="sxs-lookup"><span data-stu-id="479ab-103">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>

<span data-ttu-id="479ab-104">현재 어셈블리 매니페스트에서 참조 하는 리소스의 열거자에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-104">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479ab-105">구문</span><span class="sxs-lookup"><span data-stu-id="479ab-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="479ab-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="479ab-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="479ab-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="479ab-108">이 값은 메서드가 처음 호출 될 때 null 값 이어야 합니다 `EnumManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="479ab-108">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="479ab-109">제한이 메타 데이터 토큰을 저장 하는 데 사용 되는 배열 `mdManifestResource` 입니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-109">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="479ab-110">진행 `mdManifestResource` 에 배치할 수 있는 최대 토큰 수입니다 `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="479ab-110">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="479ab-111">제한이 `mdManifestResource` 에 실제로 배치 된 토큰의 수 `rManifestResources` 입니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-111">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="479ab-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="479ab-112">Return Value</span></span>  
  
|<span data-ttu-id="479ab-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="479ab-113">HRESULT</span></span>|<span data-ttu-id="479ab-114">설명</span><span class="sxs-lookup"><span data-stu-id="479ab-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="479ab-115">`EnumManifestResources` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-115">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="479ab-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="479ab-117">이 경우 `pcTokens` 는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-117">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="479ab-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="479ab-118">Requirements</span></span>  

 <span data-ttu-id="479ab-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="479ab-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479ab-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="479ab-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="479ab-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="479ab-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="479ab-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479ab-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479ab-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="479ab-123">See also</span></span>

- [<span data-ttu-id="479ab-124">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="479ab-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

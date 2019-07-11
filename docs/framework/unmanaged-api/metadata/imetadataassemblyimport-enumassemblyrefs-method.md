---
title: IMetaDataAssemblyImport::EnumAssemblyRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c7b512de76b5ada882b1d81c2968b4ead5c8c20
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775938"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="43460-102">IMetaDataAssemblyImport::EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="43460-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="43460-103">열거는 `mdAssemblyRef` 어셈블리 매니페스트에 정의 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="43460-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43460-104">구문</span><span class="sxs-lookup"><span data-stu-id="43460-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43460-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43460-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="43460-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="43460-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="43460-107">Null 이어야 합니다 경우이 값은 `EnumAssemblyRefs` 처음으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43460-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="43460-108">[out] 열거형 `mdAssemblyRef` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="43460-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="43460-109">[in] 에 배치할 수 있는 토큰의 최대 수는 `rAssemblyRefs` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="43460-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="43460-110">[out] 토큰의 수에 실제로 배치 `rAssemblyRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="43460-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43460-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="43460-111">Return Value</span></span>  
  
|<span data-ttu-id="43460-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43460-112">HRESULT</span></span>|<span data-ttu-id="43460-113">Description</span><span class="sxs-lookup"><span data-stu-id="43460-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="43460-114">`EnumAssemblyRefs` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43460-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="43460-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43460-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="43460-116">이 경우 `pcTokens` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43460-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43460-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43460-117">Requirements</span></span>  
 <span data-ttu-id="43460-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43460-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43460-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="43460-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43460-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="43460-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43460-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43460-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43460-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="43460-122">See also</span></span>

- [<span data-ttu-id="43460-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43460-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

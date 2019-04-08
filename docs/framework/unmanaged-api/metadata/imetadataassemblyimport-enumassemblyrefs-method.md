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
ms.openlocfilehash: 91e253669b9f51e7c1d600ba11f13a9ce67fb58a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072482"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="37e99-102">IMetaDataAssemblyImport::EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="37e99-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="37e99-103">열거는 `mdAssemblyRef` 어셈블리 매니페스트에 정의 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="37e99-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37e99-104">구문</span><span class="sxs-lookup"><span data-stu-id="37e99-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37e99-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37e99-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="37e99-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="37e99-107">Null 이어야 합니다 경우이 값은 `EnumAssemblyRefs` 처음으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="37e99-108">[out] 열거형 `mdAssemblyRef` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="37e99-109">[in] 에 배치할 수 있는 토큰의 최대 수는 `rAssemblyRefs` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="37e99-110">[out] 토큰의 수에 실제로 배치 `rAssemblyRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37e99-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="37e99-111">Return Value</span></span>  
  
|<span data-ttu-id="37e99-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37e99-112">HRESULT</span></span>|<span data-ttu-id="37e99-113">설명</span><span class="sxs-lookup"><span data-stu-id="37e99-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` <span data-ttu-id="37e99-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="37e99-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="37e99-116">이 경우 `pcTokens` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37e99-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37e99-117">Requirements</span></span>  
 <span data-ttu-id="37e99-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37e99-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37e99-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37e99-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37e99-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="37e99-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="37e99-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="37e99-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37e99-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="37e99-122">See also</span></span>

- [<span data-ttu-id="37e99-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37e99-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

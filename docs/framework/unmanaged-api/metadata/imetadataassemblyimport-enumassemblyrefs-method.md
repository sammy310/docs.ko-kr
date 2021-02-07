---
description: '자세히 알아보기: IMetaDataAssemblyImport:: EnumAssemblyRefs 메서드'
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
ms.openlocfilehash: fc1d74d79edc21c6d3d13c80510440333d083801
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671063"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="e2529-103">IMetaDataAssemblyImport::EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="e2529-103">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>

<span data-ttu-id="e2529-104">`mdAssemblyRef`어셈블리 매니페스트에 정의 된 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-104">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2529-105">구문</span><span class="sxs-lookup"><span data-stu-id="e2529-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2529-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2529-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e2529-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e2529-108">이 값은 메서드가 처음 호출 될 때 null 값 이어야 합니다 `EnumAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="e2529-108">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="e2529-109">제한이 `mdAssemblyRef` 메타 데이터 토큰의 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-109">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e2529-110">진행 배열에 배치할 수 있는 최대 토큰 수입니다 `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="e2529-110">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e2529-111">제한이 에 실제로 배치 된 토큰의 수 `rAssemblyRefs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-111">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2529-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="e2529-112">Return Value</span></span>  
  
|<span data-ttu-id="e2529-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2529-113">HRESULT</span></span>|<span data-ttu-id="e2529-114">설명</span><span class="sxs-lookup"><span data-stu-id="e2529-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e2529-115">`EnumAssemblyRefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-115">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e2529-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="e2529-117">이 경우 `pcTokens` 는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-117">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2529-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2529-118">Requirements</span></span>  

 <span data-ttu-id="e2529-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2529-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2529-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e2529-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2529-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2529-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2529-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2529-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2529-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2529-123">See also</span></span>

- [<span data-ttu-id="e2529-124">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2529-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

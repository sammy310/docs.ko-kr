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
ms.openlocfilehash: 18cd9dd14e615a7e76bfff30c9ae584305bd1907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708942"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="911b5-102">IMetaDataAssemblyImport::EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="911b5-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>

<span data-ttu-id="911b5-103">`mdAssemblyRef`어셈블리 매니페스트에 정의 된 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911b5-104">구문</span><span class="sxs-lookup"><span data-stu-id="911b5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="911b5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="911b5-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="911b5-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="911b5-107">이 값은 메서드가 처음 호출 될 때 null 값 이어야 합니다 `EnumAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="911b5-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="911b5-108">제한이 `mdAssemblyRef` 메타 데이터 토큰의 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="911b5-109">진행 배열에 배치할 수 있는 최대 토큰 수입니다 `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="911b5-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="911b5-110">제한이 에 실제로 배치 된 토큰의 수 `rAssemblyRefs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="911b5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="911b5-111">Return Value</span></span>  
  
|<span data-ttu-id="911b5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="911b5-112">HRESULT</span></span>|<span data-ttu-id="911b5-113">설명</span><span class="sxs-lookup"><span data-stu-id="911b5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="911b5-114">`EnumAssemblyRefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="911b5-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="911b5-116">이 경우 `pcTokens` 는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="911b5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="911b5-117">Requirements</span></span>  

 <span data-ttu-id="911b5-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="911b5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="911b5-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="911b5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="911b5-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="911b5-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="911b5-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="911b5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911b5-122">참조</span><span class="sxs-lookup"><span data-stu-id="911b5-122">See also</span></span>

- [<span data-ttu-id="911b5-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="911b5-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

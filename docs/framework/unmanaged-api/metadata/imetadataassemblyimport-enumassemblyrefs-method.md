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
ms.openlocfilehash: 1b9700455da82fc7f4a39d4c208ac0b18ef79722
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009121"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="a03a3-102">IMetaDataAssemblyImport::EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="a03a3-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="a03a3-103">`mdAssemblyRef`어셈블리 매니페스트에 정의 된 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a03a3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a03a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a03a3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a03a3-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a03a3-107">이 값은 메서드가 처음 호출 될 때 null 값 이어야 합니다 `EnumAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="a03a3-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="a03a3-108">제한이 `mdAssemblyRef`메타 데이터 토큰의 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a03a3-109">진행 배열에 배치할 수 있는 최대 토큰 수입니다 `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="a03a3-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a03a3-110">제한이 에 실제로 배치 된 토큰의 수 `rAssemblyRefs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a03a3-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="a03a3-111">Return Value</span></span>  
  
|<span data-ttu-id="a03a3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a03a3-112">HRESULT</span></span>|<span data-ttu-id="a03a3-113">Description</span><span class="sxs-lookup"><span data-stu-id="a03a3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a03a3-114">`EnumAssemblyRefs`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a03a3-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a03a3-116">이 경우 `pcTokens` 는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a03a3-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a03a3-117">Requirements</span></span>  
 <span data-ttu-id="a03a3-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a03a3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a03a3-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a03a3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a03a3-120">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a03a3-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a03a3-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a03a3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a03a3-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a03a3-122">See also</span></span>

- [<span data-ttu-id="a03a3-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a03a3-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)

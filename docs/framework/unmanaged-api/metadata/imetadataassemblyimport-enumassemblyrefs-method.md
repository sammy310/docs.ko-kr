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
ms.openlocfilehash: 6a4489d094974eb872b39824ceb185b0cbe48625
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177824"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="cc014-102">IMetaDataAssemblyImport::EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="cc014-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="cc014-103">어셈블리 매니페스트에 `mdAssemblyRef` 정의된 인스턴스를 에게 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc014-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc014-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc014-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc014-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cc014-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cc014-107">`EnumAssemblyRefs` 메서드를 처음 호출할 때 null 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="cc014-108">【아웃】 메타데이터 토큰의 `mdAssemblyRef` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cc014-109">【인】 배열에 배치할 수 있는 최대 `rAssemblyRefs` 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="cc014-110">【아웃】 실제로 에 배치된 토큰 `rAssemblyRefs`수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc014-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="cc014-111">Return Value</span></span>  
  
|<span data-ttu-id="cc014-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc014-112">HRESULT</span></span>|<span data-ttu-id="cc014-113">Description</span><span class="sxs-lookup"><span data-stu-id="cc014-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cc014-114">`EnumAssemblyRefs`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cc014-115">등록할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="cc014-116">이 경우 `pcTokens` 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc014-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc014-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc014-117">Requirements</span></span>  
 <span data-ttu-id="cc014-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc014-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc014-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="cc014-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc014-120">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="cc014-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc014-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc014-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc014-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc014-122">See also</span></span>

- [<span data-ttu-id="cc014-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc014-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

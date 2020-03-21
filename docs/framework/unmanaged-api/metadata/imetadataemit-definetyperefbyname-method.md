---
title: IMetaDataEmit::DefineTypeRefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 23a6931b31ea2d7e4e8d1cb3dc8adf3a51216315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175748"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="3113d-102">IMetaDataEmit::DefineTypeRefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="3113d-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="3113d-103">현재 범위를 벗어난 지정된 범위에 정의된 형식에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3113d-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3113d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3113d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3113d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3113d-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="3113d-106">【인】 해결 범위를 지정하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3113d-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="3113d-107">다음 토큰 유형은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="3113d-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="3113d-108">`mdModuleRef`을 선택하면 호출이 정의된 동일한 어셈블리에서 형식이 정의된 경우</span><span class="sxs-lookup"><span data-stu-id="3113d-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="3113d-109">`mdAssemblyRef`에서는 호출자가 정의된 어셈블리가 아닌 어셈블리에 형식이 정의된 경우</span><span class="sxs-lookup"><span data-stu-id="3113d-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="3113d-110">`mdTypeRef`을 선택하면 형식이 중첩된 형식인 경우</span><span class="sxs-lookup"><span data-stu-id="3113d-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="3113d-111">`mdModule`을 선택하면 호출자는 정의된 동일한 모듈에서 형식이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3113d-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="3113d-112">Null, 형식이 전역적으로 정의된 경우.</span><span class="sxs-lookup"><span data-stu-id="3113d-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="3113d-113">【인】 유니코드의 대상 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3113d-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="3113d-114">【아웃】 형식에 할당된 `mdTypeRef` 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3113d-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3113d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3113d-115">Requirements</span></span>  
 <span data-ttu-id="3113d-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3113d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3113d-117">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="3113d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3113d-118">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3113d-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3113d-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3113d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3113d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3113d-120">See also</span></span>

- [<span data-ttu-id="3113d-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3113d-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3113d-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3113d-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

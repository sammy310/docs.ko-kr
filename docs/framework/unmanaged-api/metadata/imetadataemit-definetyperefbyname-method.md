---
description: IMetaDataEmit::D efineTypeRefByName 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 836516e06105bb8ebc7c9bacf7b7d3837bf89eec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784017"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="ce0dd-103">IMetaDataEmit::DefineTypeRefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="ce0dd-103">IMetaDataEmit::DefineTypeRefByName Method</span></span>

<span data-ttu-id="ce0dd-104">현재 범위를 벗어난 지정 된 범위에 정의 된 형식에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-104">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0dd-105">구문</span><span class="sxs-lookup"><span data-stu-id="ce0dd-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce0dd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ce0dd-106">Parameters</span></span>  

 `tkResolutionScope`  
 <span data-ttu-id="ce0dd-107">진행 확인 범위를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-107">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="ce0dd-108">유효한 토큰 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-108">The following token types are valid:</span></span>  
  
- <span data-ttu-id="ce0dd-109">`mdModuleRef`호출자가 정의 된 동일한 어셈블리에서 형식이 정의 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-109">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="ce0dd-110">`mdAssemblyRef`호출자가 정의 되어 있지 않은 어셈블리에서 형식이 정의 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-110">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="ce0dd-111">`mdTypeRef`형식이 중첩 형식이 면입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-111">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="ce0dd-112">`mdModule`호출자가 정의 된 동일한 모듈에서 형식이 정의 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-112">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="ce0dd-113">형식이 전역적으로 정의 된 경우 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-113">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="ce0dd-114">진행 유니코드로 된 대상 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-114">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="ce0dd-115">제한이 형식에 할당 된 토큰에 대 한 포인터 `mdTypeRef` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-115">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce0dd-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce0dd-116">Requirements</span></span>  

 <span data-ttu-id="ce0dd-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce0dd-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ce0dd-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce0dd-119">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce0dd-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce0dd-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce0dd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce0dd-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce0dd-121">See also</span></span>

- [<span data-ttu-id="ce0dd-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce0dd-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ce0dd-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce0dd-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

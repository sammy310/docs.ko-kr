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
ms.openlocfilehash: 3dfdd473b01bfe83def52f957c52e0f4d11375ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434389"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="c707a-102">IMetaDataEmit::DefineTypeRefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="c707a-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="c707a-103">현재 범위를 벗어난 지정 된 범위에 정의 된 형식에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c707a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c707a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c707a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c707a-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="c707a-106">진행 확인 범위를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="c707a-107">유효한 토큰 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="c707a-108">호출자가 정의 된 동일한 어셈블리에서 형식이 정의 된 경우에는 `mdModuleRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="c707a-109">호출자가 정의 된 어셈블리 이외의 어셈블리에서 형식이 정의 된 경우에는를 `mdAssemblyRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="c707a-110">형식이 중첩 형식이 면이 고, 그렇지 않으면 `mdTypeRef`입니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="c707a-111">호출자가 정의 된 동일한 모듈에서 형식이 정의 된 경우에는 `mdModule`합니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="c707a-112">형식이 전역적으로 정의 된 경우 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="c707a-113">진행 유니코드로 된 대상 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="c707a-114">제한이 형식에 할당 된 `mdTypeRef` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c707a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c707a-115">Requirements</span></span>  
 <span data-ttu-id="c707a-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c707a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c707a-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c707a-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c707a-118">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c707a-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c707a-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c707a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c707a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c707a-120">See also</span></span>

- [<span data-ttu-id="c707a-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c707a-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c707a-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c707a-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

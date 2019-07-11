---
title: IMetaDataImport::EnumMethodImpls 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8be30e8c3b6bc7c03ede5f897f176e04153003b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781971"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="1319a-102">IMetaDataImport::EnumMethodImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="1319a-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="1319a-103">지정한 형식의 메서드를 나타내는 MethodBody 및 MethodDeclaration 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1319a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1319a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdToken     rMethodBody[],   
   [out]     mdToken     rMethodDecl[],   
   [in]      ULONG       cMax,   
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1319a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1319a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1319a-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1319a-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="1319a-108">[in] 메서드 구현이 열거 하는 형식에 대 한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="1319a-109">[out] MethodBody 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="1319a-110">[out] MethodDeclaration 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1319a-111">[in] 최대 크기는 `rMethodBody` 고 `rMethodDecl` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1319a-112">[in] 반환 하는 방법의 실제 수 `rMethodBody` 고 `rMethodDecl`입니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1319a-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="1319a-113">Return Value</span></span>  
  
|<span data-ttu-id="1319a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1319a-114">HRESULT</span></span>|<span data-ttu-id="1319a-115">Description</span><span class="sxs-lookup"><span data-stu-id="1319a-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1319a-116">`EnumMethodImpls` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1319a-117">열거할 메서드 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="1319a-118">이런 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="1319a-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1319a-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1319a-119">Requirements</span></span>  
 <span data-ttu-id="1319a-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1319a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1319a-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1319a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1319a-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1319a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1319a-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1319a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1319a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="1319a-124">See also</span></span>

- [<span data-ttu-id="1319a-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1319a-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1319a-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1319a-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

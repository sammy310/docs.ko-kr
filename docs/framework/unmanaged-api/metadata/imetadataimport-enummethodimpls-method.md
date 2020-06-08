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
ms.openlocfilehash: b8fabea78f85448e39fc6d31f0a7969458343877
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492017"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="3170e-102">IMetaDataImport::EnumMethodImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="3170e-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="3170e-103">지정한 형식의 메서드를 나타내는 MethodBody 및 MethodDeclaration 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3170e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3170e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3170e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3170e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3170e-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3170e-107">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="3170e-108">진행 해당 메서드 구현이 열거 되는 형식에 대 한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="3170e-109">제한이 MethodBody 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="3170e-110">제한이 MethodDeclaration 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3170e-111">진행 `rMethodBody`및 배열의 최대 크기 `rMethodDecl` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3170e-112">진행 및에서 반환 된 실제 메서드 수 `rMethodBody` 입니다 `rMethodDecl` .</span><span class="sxs-lookup"><span data-stu-id="3170e-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3170e-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="3170e-113">Return Value</span></span>  
  
|<span data-ttu-id="3170e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3170e-114">HRESULT</span></span>|<span data-ttu-id="3170e-115">설명</span><span class="sxs-lookup"><span data-stu-id="3170e-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3170e-116">`EnumMethodImpls`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3170e-117">열거할 메서드 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="3170e-118">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3170e-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3170e-119">Requirements</span></span>  
 <span data-ttu-id="3170e-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3170e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3170e-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3170e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3170e-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3170e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3170e-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3170e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3170e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3170e-124">See also</span></span>

- [<span data-ttu-id="3170e-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3170e-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3170e-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3170e-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

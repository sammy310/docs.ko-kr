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
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175475"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="c7b35-102">IMetaDataImport::EnumMethodImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="c7b35-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="c7b35-103">지정한 형식의 메서드를 나타내는 MethodBody 및 MethodDeclaration 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7b35-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7b35-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c7b35-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7b35-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c7b35-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c7b35-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="c7b35-108">【인】 메서드를 개명하는 형식을 위한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="c7b35-109">【아웃】 MethodBody 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="c7b35-110">【아웃】 MethodDeclaration 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c7b35-111">【인】 `rMethodBody` 및 `rMethodDecl` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c7b35-112">【인】 반환된 메서드의 실제 `rMethodBody` `rMethodDecl`수및 .</span><span class="sxs-lookup"><span data-stu-id="c7b35-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7b35-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="c7b35-113">Return Value</span></span>  
  
|<span data-ttu-id="c7b35-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7b35-114">HRESULT</span></span>|<span data-ttu-id="c7b35-115">Description</span><span class="sxs-lookup"><span data-stu-id="c7b35-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c7b35-116">`EnumMethodImpls`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c7b35-117">등록할 메서드 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="c7b35-118">이 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c7b35-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7b35-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7b35-119">Requirements</span></span>  
 <span data-ttu-id="c7b35-120">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7b35-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7b35-121">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="c7b35-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7b35-122">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c7b35-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7b35-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7b35-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b35-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7b35-124">See also</span></span>

- [<span data-ttu-id="c7b35-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7b35-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c7b35-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7b35-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

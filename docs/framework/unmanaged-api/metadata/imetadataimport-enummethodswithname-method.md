---
title: IMetaDataImport::EnumMethodsWithName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 5b5345fc4819716dc6c2a00323f94546cfc67f32
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720934"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="4e885-102">IMetaDataImport::EnumMethodsWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="4e885-102">IMetaDataImport::EnumMethodsWithName Method</span></span>

<span data-ttu-id="4e885-103">지정한 TypeDef 토큰이 참조하는 형식으로 정의되고 지정한 이름을 가진 메서드를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e885-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e885-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e885-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e885-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="4e885-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4e885-107">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="4e885-108">진행 열거할 메서드를 포함 하는 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e885-109">진행 열거형의 범위를 제한 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="4e885-110">제한이 MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4e885-111">[in] `rMethods` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4e885-112">제한이 에서 반환 된 MethodDef 토큰의 수입니다 `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="4e885-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e885-113">설명</span><span class="sxs-lookup"><span data-stu-id="4e885-113">Remarks</span></span>  

 <span data-ttu-id="4e885-114">이 메서드는 필드 및 메서드를 열거 하지만 속성이 나 이벤트는 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="4e885-115">[IMetaDataImport:: EnumMethods](imetadataimport-enummethods-method.md)달리는 `EnumMethodsWithName` 지정 된 이름이 없는 메서드 토큰을 모두 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-115">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e885-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="4e885-116">Return Value</span></span>  
  
|<span data-ttu-id="4e885-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e885-117">HRESULT</span></span>|<span data-ttu-id="4e885-118">설명</span><span class="sxs-lookup"><span data-stu-id="4e885-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4e885-119">`EnumMethodsWithName` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4e885-120">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="4e885-121">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e885-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e885-122">Requirements</span></span>  

 <span data-ttu-id="4e885-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e885-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e885-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4e885-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e885-125">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e885-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e885-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e885-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e885-127">참조</span><span class="sxs-lookup"><span data-stu-id="4e885-127">See also</span></span>

- [<span data-ttu-id="4e885-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e885-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4e885-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e885-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

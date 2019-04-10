---
title: IMetaDataImport::EnumTypeSpecs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01151dc2fe6aa995285a34076527609816b2f3e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205162"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="f42c1-102">IMetaDataImport::EnumTypeSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="f42c1-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="f42c1-103">현재 메타데이터 범위에서 정의된 TypeSpec 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f42c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="f42c1-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f42c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f42c1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f42c1-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f42c1-107">이 값이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="f42c1-108">[out] TypeSpec 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f42c1-109">[in] `rTypeSpecs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="f42c1-110">[out] TypeSpec 토큰에서 반환 된 수가 `rTypeSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f42c1-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="f42c1-111">Return Value</span></span>  
  
|<span data-ttu-id="f42c1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f42c1-112">HRESULT</span></span>|<span data-ttu-id="f42c1-113">설명</span><span class="sxs-lookup"><span data-stu-id="f42c1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeSpecs` <span data-ttu-id="f42c1-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f42c1-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f42c1-116">이런 경우 `pcTypeSpecs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f42c1-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f42c1-117">설명</span><span class="sxs-lookup"><span data-stu-id="f42c1-117">Remarks</span></span>  
 <span data-ttu-id="f42c1-118">TypeSpec 토큰은 만든 합니다 [imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f42c1-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f42c1-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f42c1-119">Requirements</span></span>  
 <span data-ttu-id="f42c1-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f42c1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f42c1-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f42c1-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f42c1-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f42c1-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f42c1-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f42c1-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f42c1-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="f42c1-124">See also</span></span>

- [<span data-ttu-id="f42c1-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f42c1-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f42c1-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f42c1-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

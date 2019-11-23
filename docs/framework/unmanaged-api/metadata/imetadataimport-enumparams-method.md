---
title: IMetaDataImport::EnumParams 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
ms.openlocfilehash: e5fa3647c86d97730e7ad6a2576dd34af75251d6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433952"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="0c277-102">IMetaDataImport::EnumParams 메서드</span><span class="sxs-lookup"><span data-stu-id="0c277-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="0c277-103">지정한 MethodDef 토큰이 참조하는 메서드의 매개 변수를 나타내는 ParamDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c277-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c277-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c277-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c277-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c277-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0c277-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="0c277-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0c277-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="0c277-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="0c277-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span><span class="sxs-lookup"><span data-stu-id="0c277-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="0c277-109">[out] The array used to store the ParamDef tokens.</span><span class="sxs-lookup"><span data-stu-id="0c277-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0c277-110">[in] `rParams` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0c277-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0c277-111">[out] The number of ParamDef tokens returned in `rParams`.</span><span class="sxs-lookup"><span data-stu-id="0c277-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c277-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="0c277-112">Return Value</span></span>  
  
|<span data-ttu-id="0c277-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c277-113">HRESULT</span></span>|<span data-ttu-id="0c277-114">설명</span><span class="sxs-lookup"><span data-stu-id="0c277-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0c277-115">`EnumParams` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="0c277-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0c277-116">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="0c277-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="0c277-117">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="0c277-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c277-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c277-118">Requirements</span></span>  
 <span data-ttu-id="0c277-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c277-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c277-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c277-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c277-121">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c277-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c277-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c277-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c277-123">참조</span><span class="sxs-lookup"><span data-stu-id="0c277-123">See also</span></span>

- [<span data-ttu-id="0c277-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c277-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0c277-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c277-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

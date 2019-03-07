---
title: IMetaDataImport::EnumMethods 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6237951b7fab013a32a7e717215cacdbe1125b1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493708"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="d3034-102">IMetaDataImport::EnumMethods 메서드</span><span class="sxs-lookup"><span data-stu-id="d3034-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="d3034-103">지정한 형식의 메서드를 나타내는 MethodDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3034-104">구문</span><span class="sxs-lookup"><span data-stu-id="d3034-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3034-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3034-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d3034-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d3034-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="d3034-108">[in] 열거 하는 메서드를 사용 하 여 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="d3034-109">[out] MethodDef 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d3034-110">[in] 최대 크기인 MethodDef `rMethods` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d3034-111">[out] MethodDef 토큰에서 반환 된 수가 `rMethods`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3034-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="d3034-112">Return Value</span></span>  
  
|<span data-ttu-id="d3034-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3034-113">HRESULT</span></span>|<span data-ttu-id="d3034-114">설명</span><span class="sxs-lookup"><span data-stu-id="d3034-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d3034-115">`EnumMethods` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d3034-116">열거할 MethodDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="d3034-117">이런 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d3034-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3034-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3034-118">Requirements</span></span>  
 <span data-ttu-id="d3034-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3034-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3034-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3034-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3034-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d3034-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3034-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3034-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3034-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3034-123">See also</span></span>
- [<span data-ttu-id="d3034-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3034-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d3034-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3034-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

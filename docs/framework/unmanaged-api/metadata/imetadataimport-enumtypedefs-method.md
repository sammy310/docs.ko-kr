---
title: IMetaDataImport::EnumTypeDefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a285543571c843a982b6615fdc4b5f1325ed066
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466962"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="e2c0c-102">IMetaDataImport::EnumTypeDefs 메서드</span><span class="sxs-lookup"><span data-stu-id="e2c0c-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="e2c0c-103">현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c0c-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2c0c-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2c0c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2c0c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e2c0c-106">[out] 새 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="e2c0c-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="e2c0c-108">[in] TypeDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e2c0c-109">[in] `rTypeDefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="e2c0c-110">[out] TypeDef 토큰에서 반환 된 수가 `rTypeDefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2c0c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="e2c0c-111">Return Value</span></span>  
  
|<span data-ttu-id="e2c0c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2c0c-112">HRESULT</span></span>|<span data-ttu-id="e2c0c-113">설명</span><span class="sxs-lookup"><span data-stu-id="e2c0c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e2c0c-114">`EnumTypeDefs` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e2c0c-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e2c0c-116">이런 경우 `pcTypeDefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2c0c-117">설명</span><span class="sxs-lookup"><span data-stu-id="e2c0c-117">Remarks</span></span>  
 <span data-ttu-id="e2c0c-118">TypeDef 토큰에는 확장성 메커니즘을 통해 추가 된 모든 형식 뿐만 아니라 클래스 또는 인터페이스를 같은 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2c0c-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2c0c-119">Requirements</span></span>  
 <span data-ttu-id="e2c0c-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2c0c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2c0c-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e2c0c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2c0c-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e2c0c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2c0c-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2c0c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c0c-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="e2c0c-124">See also</span></span>
- [<span data-ttu-id="e2c0c-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2c0c-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e2c0c-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2c0c-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

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
ms.openlocfilehash: 3854cb4aa3d229c87466c0a35a72447ceb235624
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449999"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="da8a2-102">IMetaDataImport::EnumTypeDefs 메서드</span><span class="sxs-lookup"><span data-stu-id="da8a2-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="da8a2-103">현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da8a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="da8a2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da8a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da8a2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="da8a2-106">제한이 새 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="da8a2-107">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="da8a2-108">진행 TypeDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="da8a2-109">[in] `rTypeDefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="da8a2-110">제한이 `rTypeDefs`에서 반환 된 TypeDef 토큰의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da8a2-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="da8a2-111">Return Value</span></span>  
  
|<span data-ttu-id="da8a2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da8a2-112">HRESULT</span></span>|<span data-ttu-id="da8a2-113">설명</span><span class="sxs-lookup"><span data-stu-id="da8a2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="da8a2-114">`EnumTypeDefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="da8a2-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="da8a2-116">이 경우 `pcTypeDefs`은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da8a2-117">주의</span><span class="sxs-lookup"><span data-stu-id="da8a2-117">Remarks</span></span>  
 <span data-ttu-id="da8a2-118">TypeDef 토큰은 클래스 또는 인터페이스와 같은 형식 뿐만 아니라 확장성 메커니즘을 통해 추가 된 모든 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da8a2-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da8a2-119">Requirements</span></span>  
 <span data-ttu-id="da8a2-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da8a2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da8a2-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="da8a2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da8a2-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da8a2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da8a2-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da8a2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8a2-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da8a2-124">See also</span></span>

- [<span data-ttu-id="da8a2-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da8a2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="da8a2-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da8a2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

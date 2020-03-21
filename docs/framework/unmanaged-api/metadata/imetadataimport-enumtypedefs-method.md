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
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177292"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="4ad19-102">IMetaDataImport::EnumTypeDefs 메서드</span><span class="sxs-lookup"><span data-stu-id="4ad19-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="4ad19-103">현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad19-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ad19-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ad19-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ad19-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4ad19-106">【아웃】 새 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="4ad19-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="4ad19-108">【인】 TypeDef 토큰을 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4ad19-109">[in] `rTypeDefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="4ad19-110">【아웃】 에서 반환되는 TypeDef 토큰 `rTypeDefs`의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ad19-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="4ad19-111">Return Value</span></span>  
  
|<span data-ttu-id="4ad19-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ad19-112">HRESULT</span></span>|<span data-ttu-id="4ad19-113">Description</span><span class="sxs-lookup"><span data-stu-id="4ad19-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4ad19-114">`EnumTypeDefs`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4ad19-115">등록할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4ad19-116">이 경우 `pcTypeDefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ad19-117">설명</span><span class="sxs-lookup"><span data-stu-id="4ad19-117">Remarks</span></span>  
 <span data-ttu-id="4ad19-118">TypeDef 토큰은 클래스 또는 인터페이스와 같은 형식과 확장성 메커니즘을 통해 추가된 모든 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ad19-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad19-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ad19-119">Requirements</span></span>  
 <span data-ttu-id="4ad19-120">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ad19-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad19-121">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="4ad19-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ad19-122">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4ad19-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ad19-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad19-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad19-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ad19-124">See also</span></span>

- [<span data-ttu-id="4ad19-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ad19-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4ad19-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ad19-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

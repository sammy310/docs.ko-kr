---
title: IMetaDataImport::EnumTypeRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175436"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="38800-102">IMetaDataImport::EnumTypeRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="38800-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="38800-103">현재 메타데이터 범위에서 정의된 TypeRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="38800-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38800-104">구문</span><span class="sxs-lookup"><span data-stu-id="38800-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38800-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38800-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="38800-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38800-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="38800-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.</span><span class="sxs-lookup"><span data-stu-id="38800-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="38800-108">【아웃】 TypeRef 토큰을 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="38800-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="38800-109">[in] `rTypeRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="38800-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="38800-110">【아웃】 에서 반환되는 TypeRef 토큰 수에 `rTypeRefs`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38800-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38800-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="38800-111">Return Value</span></span>  
  
|<span data-ttu-id="38800-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38800-112">HRESULT</span></span>|<span data-ttu-id="38800-113">Description</span><span class="sxs-lookup"><span data-stu-id="38800-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="38800-114">`EnumTypeRefs`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="38800-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="38800-115">등록할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38800-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="38800-116">이 경우 `pcTypeRefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="38800-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38800-117">설명</span><span class="sxs-lookup"><span data-stu-id="38800-117">Remarks</span></span>  
 <span data-ttu-id="38800-118">TypeRef 토큰은 형식에 대한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38800-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38800-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38800-119">Requirements</span></span>  
 <span data-ttu-id="38800-120">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38800-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38800-121">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="38800-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38800-122">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="38800-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38800-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38800-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38800-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38800-124">See also</span></span>

- [<span data-ttu-id="38800-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38800-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="38800-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38800-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

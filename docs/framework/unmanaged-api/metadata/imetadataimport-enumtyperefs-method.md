---
description: '자세히 알아보기: IMetaDataImport:: EnumTypeRefs 메서드'
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
ms.openlocfilehash: 1155357e82c08660a852225f0b1a54629cbee0ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670621"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="c56ef-103">IMetaDataImport::EnumTypeRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="c56ef-103">IMetaDataImport::EnumTypeRefs Method</span></span>

<span data-ttu-id="c56ef-104">현재 메타데이터 범위에서 정의된 TypeRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-104">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c56ef-105">구문</span><span class="sxs-lookup"><span data-stu-id="c56ef-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c56ef-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c56ef-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="c56ef-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c56ef-108">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-108">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="c56ef-109">제한이 TypeRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-109">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c56ef-110">[in] `rTypeRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-110">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="c56ef-111">제한이 에서 반환 된 TypeRef 토큰 수에 대 한 포인터입니다 `rTypeRefs` .</span><span class="sxs-lookup"><span data-stu-id="c56ef-111">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c56ef-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="c56ef-112">Return Value</span></span>  
  
|<span data-ttu-id="c56ef-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c56ef-113">HRESULT</span></span>|<span data-ttu-id="c56ef-114">설명</span><span class="sxs-lookup"><span data-stu-id="c56ef-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c56ef-115">`EnumTypeRefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-115">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c56ef-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="c56ef-117">이 경우는 `pcTypeRefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-117">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c56ef-118">설명</span><span class="sxs-lookup"><span data-stu-id="c56ef-118">Remarks</span></span>  

 <span data-ttu-id="c56ef-119">TypeRef 토큰은 형식에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-119">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c56ef-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c56ef-120">Requirements</span></span>  

 <span data-ttu-id="c56ef-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c56ef-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c56ef-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c56ef-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c56ef-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c56ef-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c56ef-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c56ef-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c56ef-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c56ef-125">See also</span></span>

- [<span data-ttu-id="c56ef-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c56ef-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c56ef-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c56ef-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

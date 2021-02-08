---
description: '자세히 알아보기: IMetaDataImport:: EnumTypeSpecs 메서드'
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
ms.openlocfilehash: 7446bbf3296ffb6cfa3a20f594b4a7da22acff5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799345"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="3c368-103">IMetaDataImport::EnumTypeSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="3c368-103">IMetaDataImport::EnumTypeSpecs Method</span></span>

<span data-ttu-id="3c368-104">현재 메타데이터 범위에서 정의된 TypeSpec 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-104">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c368-105">구문</span><span class="sxs-lookup"><span data-stu-id="3c368-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c368-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c368-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="3c368-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3c368-108">이 메서드의 첫 번째 호출에서이 값은 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-108">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="3c368-109">제한이 TypeSpec 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-109">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c368-110">[in] `rTypeSpecs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-110">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="3c368-111">제한이 에서 반환 되는 TypeSpec 토큰의 수입니다 `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="3c368-111">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c368-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="3c368-112">Return Value</span></span>  
  
|<span data-ttu-id="3c368-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c368-113">HRESULT</span></span>|<span data-ttu-id="3c368-114">설명</span><span class="sxs-lookup"><span data-stu-id="3c368-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c368-115">`EnumTypeSpecs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-115">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c368-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="3c368-117">이 경우는 `pcTypeSpecs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-117">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c368-118">설명</span><span class="sxs-lookup"><span data-stu-id="3c368-118">Remarks</span></span>  

 <span data-ttu-id="3c368-119">TypeSpec 토큰은 [IMetaDataEmit:: GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) 메서드를 통해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-119">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c368-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c368-120">Requirements</span></span>  

 <span data-ttu-id="3c368-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c368-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c368-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3c368-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c368-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c368-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c368-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c368-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c368-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c368-125">See also</span></span>

- [<span data-ttu-id="3c368-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c368-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3c368-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c368-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

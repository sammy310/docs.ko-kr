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
ms.openlocfilehash: 94b4c3935c949c0c4008e41244713b6bfa4dba84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503720"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="227a5-102">IMetaDataImport::EnumTypeSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="227a5-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="227a5-103">현재 메타데이터 범위에서 정의된 TypeSpec 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="227a5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="227a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="227a5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="227a5-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="227a5-107">이 메서드의 첫 번째 호출에서이 값은 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="227a5-108">제한이 TypeSpec 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="227a5-109">[in] `rTypeSpecs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="227a5-110">제한이 에서 반환 되는 TypeSpec 토큰의 수입니다 `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="227a5-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="227a5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="227a5-111">Return Value</span></span>  
  
|<span data-ttu-id="227a5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="227a5-112">HRESULT</span></span>|<span data-ttu-id="227a5-113">설명</span><span class="sxs-lookup"><span data-stu-id="227a5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="227a5-114">`EnumTypeSpecs`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="227a5-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="227a5-116">이 경우는 `pcTypeSpecs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="227a5-117">설명</span><span class="sxs-lookup"><span data-stu-id="227a5-117">Remarks</span></span>  
 <span data-ttu-id="227a5-118">TypeSpec 토큰은 [IMetaDataEmit:: GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) 메서드를 통해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="227a5-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="227a5-119">Requirements</span></span>  
 <span data-ttu-id="227a5-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="227a5-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="227a5-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="227a5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="227a5-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="227a5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="227a5-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="227a5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227a5-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="227a5-124">See also</span></span>

- [<span data-ttu-id="227a5-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="227a5-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="227a5-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="227a5-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

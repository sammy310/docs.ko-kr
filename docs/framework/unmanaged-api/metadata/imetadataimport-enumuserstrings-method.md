---
title: IMetaDataImport::EnumUserStrings 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea144784f82c192f41f68394eb2ccdf443db54c2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782550"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="0c14c-102">IMetaDataImport::EnumUserStrings 메서드</span><span class="sxs-lookup"><span data-stu-id="0c14c-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="0c14c-103">현재 메타데이터 범위에서 하드 코드된 문자열을 나타내는 String 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c14c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c14c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c14c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c14c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0c14c-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0c14c-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="0c14c-108">[out] 문자열 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0c14c-109">[in] `rStrings` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="0c14c-110">[out] 반환 하는 문자열 토큰 수 `rStrings`입니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c14c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="0c14c-111">Return Value</span></span>  
  
|<span data-ttu-id="0c14c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c14c-112">HRESULT</span></span>|<span data-ttu-id="0c14c-113">설명</span><span class="sxs-lookup"><span data-stu-id="0c14c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0c14c-114">`EnumUserStrings` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0c14c-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0c14c-116">이런 경우 `pcStrings` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c14c-117">설명</span><span class="sxs-lookup"><span data-stu-id="0c14c-117">Remarks</span></span>  
 <span data-ttu-id="0c14c-118">문자열 토큰은 만든 합니다 [imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="0c14c-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="0c14c-119">이 메서드는 메타 데이터 브라우저에서 대신 컴파일러에 의해 사용 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c14c-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c14c-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c14c-120">Requirements</span></span>  
 <span data-ttu-id="0c14c-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c14c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c14c-122">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c14c-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c14c-123">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0c14c-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c14c-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c14c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c14c-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c14c-125">See also</span></span>

- [<span data-ttu-id="0c14c-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c14c-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0c14c-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c14c-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

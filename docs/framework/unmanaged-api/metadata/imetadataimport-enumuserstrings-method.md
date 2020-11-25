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
ms.openlocfilehash: c7dcc740dcf9b228713693a57dc8ef96d215ebad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716566"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="89bb0-102">IMetaDataImport::EnumUserStrings 메서드</span><span class="sxs-lookup"><span data-stu-id="89bb0-102">IMetaDataImport::EnumUserStrings Method</span></span>

<span data-ttu-id="89bb0-103">현재 메타데이터 범위에서 하드 코드된 문자열을 나타내는 String 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89bb0-104">구문</span><span class="sxs-lookup"><span data-stu-id="89bb0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89bb0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89bb0-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="89bb0-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="89bb0-107">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="89bb0-108">제한이 문자열 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="89bb0-109">[in] `rStrings` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="89bb0-110">제한이 에서 반환 된 문자열 토큰의 수입니다 `rStrings` .</span><span class="sxs-lookup"><span data-stu-id="89bb0-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89bb0-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="89bb0-111">Return Value</span></span>  
  
|<span data-ttu-id="89bb0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89bb0-112">HRESULT</span></span>|<span data-ttu-id="89bb0-113">설명</span><span class="sxs-lookup"><span data-stu-id="89bb0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="89bb0-114">`EnumUserStrings` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="89bb0-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="89bb0-116">이 경우는 `pcStrings` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89bb0-117">설명</span><span class="sxs-lookup"><span data-stu-id="89bb0-117">Remarks</span></span>  

 <span data-ttu-id="89bb0-118">[IMetaDataEmit::D efineUserString](imetadataemit-defineuserstring-method.md) 메서드는 문자열 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="89bb0-119">이 메서드는 컴파일러가 아니라 메타 데이터 브라우저에서 사용 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89bb0-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89bb0-120">Requirements</span></span>  

 <span data-ttu-id="89bb0-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89bb0-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89bb0-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="89bb0-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89bb0-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89bb0-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89bb0-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89bb0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89bb0-125">참조</span><span class="sxs-lookup"><span data-stu-id="89bb0-125">See also</span></span>

- [<span data-ttu-id="89bb0-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89bb0-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="89bb0-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89bb0-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

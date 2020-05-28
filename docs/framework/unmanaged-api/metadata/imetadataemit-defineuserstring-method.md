---
title: IMetaDataEmit::DefineUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: def77bb64e21b1421983cf263d488ecc1ddb9452
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009324"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="d71c5-102">IMetaDataEmit::DefineUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="d71c5-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="d71c5-103">지정 된 리터럴 문자열에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d71c5-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d71c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="d71c5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d71c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d71c5-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="d71c5-106">진행 저장할 사용자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d71c5-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="d71c5-107">진행 의 와이드 문자 수입니다 `szString` .</span><span class="sxs-lookup"><span data-stu-id="d71c5-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="d71c5-108">제한이 할당 된 문자열 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d71c5-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d71c5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d71c5-109">Requirements</span></span>  
 <span data-ttu-id="d71c5-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d71c5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d71c5-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d71c5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d71c5-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d71c5-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d71c5-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d71c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71c5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d71c5-114">See also</span></span>

- [<span data-ttu-id="d71c5-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d71c5-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d71c5-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d71c5-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

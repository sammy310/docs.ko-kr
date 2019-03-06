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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 820b0c464f591ca71072d35886a910f5409f654e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478299"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="03049-102">IMetaDataEmit::DefineUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="03049-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="03049-103">지정된 된 리터럴 문자열에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03049-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03049-104">구문</span><span class="sxs-lookup"><span data-stu-id="03049-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03049-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03049-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="03049-106">[in] 사용자 문자열 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="03049-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="03049-107">[in] 와이드 문자 수가 `szString`합니다.</span><span class="sxs-lookup"><span data-stu-id="03049-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="03049-108">[out] 할당 된 문자열 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="03049-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03049-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03049-109">Requirements</span></span>  
 <span data-ttu-id="03049-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03049-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03049-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="03049-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03049-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="03049-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03049-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03049-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03049-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="03049-114">See also</span></span>
- [<span data-ttu-id="03049-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03049-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="03049-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03049-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

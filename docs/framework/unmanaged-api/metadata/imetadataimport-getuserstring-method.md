---
title: IMetaDataImport::GetUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
ms.openlocfilehash: 690abec6104f6eed1ad5a0eae9a6b6bb18d35b0d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436681"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="bdea2-102">IMetaDataImport::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="bdea2-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="bdea2-103">지정한 메타데이터 토큰이 나타내는 리터럴 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bdea2-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdea2-104">구문</span><span class="sxs-lookup"><span data-stu-id="bdea2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdea2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bdea2-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="bdea2-106">[in] The String token to return the associated string for.</span><span class="sxs-lookup"><span data-stu-id="bdea2-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="bdea2-107">[out] A copy of the requested string.</span><span class="sxs-lookup"><span data-stu-id="bdea2-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="bdea2-108">[in] The maximum size in wide characters of the requested `szString`.</span><span class="sxs-lookup"><span data-stu-id="bdea2-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="bdea2-109">[out] The size in wide characters of the returned `szString`.</span><span class="sxs-lookup"><span data-stu-id="bdea2-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdea2-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bdea2-110">Requirements</span></span>  
 <span data-ttu-id="bdea2-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdea2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdea2-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bdea2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdea2-113">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bdea2-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bdea2-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdea2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdea2-115">참조</span><span class="sxs-lookup"><span data-stu-id="bdea2-115">See also</span></span>

- [<span data-ttu-id="bdea2-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdea2-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bdea2-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdea2-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

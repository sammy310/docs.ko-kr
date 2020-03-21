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
ms.openlocfilehash: a71d8694ec8c5bd35ecd3e98ed32e05bc7b382fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177613"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="b5877-102">IMetaDataEmit::DefineUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="b5877-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="b5877-103">지정된 리터럴 문자열에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5877-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5877-104">구문</span><span class="sxs-lookup"><span data-stu-id="b5877-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5877-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5877-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="b5877-106">【인】 저장할 사용자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b5877-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="b5877-107">【인】 에서 와이드 문자의 `szString`수입니다.</span><span class="sxs-lookup"><span data-stu-id="b5877-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="b5877-108">【아웃】 할당된 문자열 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b5877-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5877-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5877-109">Requirements</span></span>  
 <span data-ttu-id="b5877-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5877-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5877-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="b5877-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5877-112">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b5877-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5877-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5877-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5877-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5877-114">See also</span></span>

- [<span data-ttu-id="b5877-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5877-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b5877-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5877-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

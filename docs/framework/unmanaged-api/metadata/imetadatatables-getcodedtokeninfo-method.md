---
title: IMetaDataTables::GetCodedTokenInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: 64c70fe0b657047ae35dccb763fa57120403deef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177146"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="db5a1-102">IMetaDataTables::GetCodedTokenInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="db5a1-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="db5a1-103">지정된 행 인덱스와 연결된 토큰 배열에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="db5a1-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db5a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="db5a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db5a1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db5a1-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="db5a1-106">【인】 반환할 코딩된 토큰의 종류입니다.</span><span class="sxs-lookup"><span data-stu-id="db5a1-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="db5a1-107">【아웃】 `ppTokens`의 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="db5a1-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="db5a1-108">【아웃】 반환된 토큰 목록을 포함하는 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="db5a1-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="db5a1-109">【아웃】 에서 `ixCdTkn`토큰 이름에 대한 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="db5a1-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db5a1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db5a1-110">Requirements</span></span>  
 <span data-ttu-id="db5a1-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db5a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db5a1-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="db5a1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db5a1-113">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="db5a1-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db5a1-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db5a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db5a1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db5a1-115">See also</span></span>

- [<span data-ttu-id="db5a1-116">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db5a1-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="db5a1-117">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db5a1-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

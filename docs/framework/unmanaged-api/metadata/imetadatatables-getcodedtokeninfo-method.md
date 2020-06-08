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
ms.openlocfilehash: 8ab16ad5b2b2838125e07511ef47be737f40671c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501211"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="477a1-102">IMetaDataTables::GetCodedTokenInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="477a1-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="477a1-103">지정 된 행 인덱스와 연결 된 토큰의 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="477a1-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="477a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="477a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="477a1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="477a1-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="477a1-106">진행 반환할 코딩 된 토큰의 종류입니다.</span><span class="sxs-lookup"><span data-stu-id="477a1-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="477a1-107">제한이 의 길이에 대 한 포인터입니다 `ppTokens` .</span><span class="sxs-lookup"><span data-stu-id="477a1-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="477a1-108">제한이 반환 된 토큰의 목록이 포함 된 배열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="477a1-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="477a1-109">제한이 에서 토큰의 이름에 대 한 포인터에 대 한 포인터입니다 `ixCdTkn` .</span><span class="sxs-lookup"><span data-stu-id="477a1-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="477a1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="477a1-110">Requirements</span></span>  
 <span data-ttu-id="477a1-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="477a1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="477a1-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="477a1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="477a1-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="477a1-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="477a1-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="477a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477a1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="477a1-115">See also</span></span>

- [<span data-ttu-id="477a1-116">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="477a1-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="477a1-117">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="477a1-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

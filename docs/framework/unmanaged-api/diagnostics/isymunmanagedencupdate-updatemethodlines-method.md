---
title: ISymUnmanagedENCUpdate::UpdateMethodLines 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 226d9aa75d0a9e4d6cef92e2d2edacb6e98cf34e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473059"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="0a596-102">ISymUnmanagedENCUpdate::UpdateMethodLines 메서드</span><span class="sxs-lookup"><span data-stu-id="0a596-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="0a596-103">컴파일되지 않은, 하지만 해당 줄 독립적으로 이동 하는 방법에 대 한 줄 정보를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a596-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="0a596-104">각 문에 대 한 델타 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a596-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a596-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a596-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a596-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a596-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="0a596-107">[in] 메타 데이터 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0a596-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="0a596-108">[in] 배열을 `INT32` 메서드에서 각 시퀀스 요소에 대 한 델타를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0a596-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="0a596-109">[in] A `ULONG` 크기를 포함 하는 `pDeltas` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a596-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a596-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="0a596-110">Return Value</span></span>  
 <span data-ttu-id="0a596-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0a596-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a596-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a596-112">Requirements</span></span>  
 <span data-ttu-id="0a596-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0a596-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a596-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a596-114">See also</span></span>
- [<span data-ttu-id="0a596-115">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a596-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

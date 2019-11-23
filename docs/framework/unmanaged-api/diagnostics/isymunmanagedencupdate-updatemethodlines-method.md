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
ms.openlocfilehash: 9aace77c4b3549c033433d4c305b07daa1f7a8c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449001"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="d0653-102">ISymUnmanagedENCUpdate::UpdateMethodLines 메서드</span><span class="sxs-lookup"><span data-stu-id="d0653-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="d0653-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span><span class="sxs-lookup"><span data-stu-id="d0653-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="d0653-104">A delta for each statement is allowed.</span><span class="sxs-lookup"><span data-stu-id="d0653-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0653-105">구문</span><span class="sxs-lookup"><span data-stu-id="d0653-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0653-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0653-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="d0653-107">[in] The metadata of the method token.</span><span class="sxs-lookup"><span data-stu-id="d0653-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="d0653-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span><span class="sxs-lookup"><span data-stu-id="d0653-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="d0653-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span><span class="sxs-lookup"><span data-stu-id="d0653-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0653-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="d0653-110">Return Value</span></span>  
 <span data-ttu-id="d0653-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="d0653-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0653-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0653-112">Requirements</span></span>  
 <span data-ttu-id="d0653-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d0653-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0653-114">참조</span><span class="sxs-lookup"><span data-stu-id="d0653-114">See also</span></span>

- [<span data-ttu-id="d0653-115">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0653-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

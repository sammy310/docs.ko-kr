---
description: '자세히 알아보기: ISymUnmanagedENCUpdate:: UpdateMethodLines 메서드'
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
ms.openlocfilehash: 6174f3aa980ccf2cdc07720e3aa90b7bb74a77af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710064"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="96f48-103">ISymUnmanagedENCUpdate::UpdateMethodLines 메서드</span><span class="sxs-lookup"><span data-stu-id="96f48-103">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>

<span data-ttu-id="96f48-104">다시 컴파일되지 않았지만 해당 줄이 독립적으로 이동 된 메서드에 대 한 줄 정보를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f48-104">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="96f48-105">각 문에 대 한 델타를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96f48-105">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f48-106">구문</span><span class="sxs-lookup"><span data-stu-id="96f48-106">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96f48-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96f48-107">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="96f48-108">진행 메서드 토큰의 메타 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="96f48-108">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="96f48-109">진행 `INT32` 메서드의 각 시퀀스 위치에 대 한 델타를 나타내는 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="96f48-109">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="96f48-110">진행 `ULONG` 매개 변수의 크기를 포함 하는 `pDeltas` 입니다.</span><span class="sxs-lookup"><span data-stu-id="96f48-110">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96f48-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="96f48-111">Return Value</span></span>  

 <span data-ttu-id="96f48-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="96f48-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96f48-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96f48-113">Requirements</span></span>  

 <span data-ttu-id="96f48-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="96f48-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f48-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96f48-115">See also</span></span>

- [<span data-ttu-id="96f48-116">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96f48-116">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)

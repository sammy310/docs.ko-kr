---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 053727604c795bf43a9b1658d5841fe85f53090a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614632"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="a0c05-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="a0c05-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="a0c05-103">토큰-소스 범위 매핑 정보에 대 한 특수 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c05-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="a0c05-104">닫힌 후에는 더 이상 매핑 정보를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c05-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c05-105">구문</span><span class="sxs-lookup"><span data-stu-id="a0c05-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a0c05-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="a0c05-106">Return Value</span></span>  
 <span data-ttu-id="a0c05-107">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c05-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c05-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0c05-108">Requirements</span></span>  
 <span data-ttu-id="a0c05-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a0c05-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c05-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0c05-110">See also</span></span>

- [<span data-ttu-id="a0c05-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0c05-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)

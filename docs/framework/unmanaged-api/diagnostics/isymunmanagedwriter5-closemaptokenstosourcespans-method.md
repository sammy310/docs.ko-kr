---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: b57174f9f76b174927b8f1997beac3dd1482583a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725913"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="0f4c8-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="0f4c8-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="0f4c8-103">토큰-소스 범위 매핑 정보에 대 한 특수 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="0f4c8-104">닫힌 후에는 더 이상 매핑 정보를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f4c8-105">구문</span><span class="sxs-lookup"><span data-stu-id="0f4c8-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0f4c8-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="0f4c8-106">Return Value</span></span>  

 <span data-ttu-id="0f4c8-107">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4c8-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f4c8-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f4c8-108">Requirements</span></span>  

 <span data-ttu-id="0f4c8-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="0f4c8-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4c8-110">참조</span><span class="sxs-lookup"><span data-stu-id="0f4c8-110">See also</span></span>

- [<span data-ttu-id="0f4c8-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f4c8-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)

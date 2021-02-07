---
description: '자세히 알아보기: ISymUnmanagedWriter5:: CloseMapTokensToSourceSpans 메서드'
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 687a853441a4406c2eb0a9c4b3d5d59df3575e1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761657"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="a6bd5-103">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="a6bd5-103">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="a6bd5-104">토큰-소스 범위 매핑 정보에 대 한 특수 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a6bd5-104">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="a6bd5-105">닫힌 후에는 더 이상 매핑 정보를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6bd5-105">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6bd5-106">구문</span><span class="sxs-lookup"><span data-stu-id="a6bd5-106">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a6bd5-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="a6bd5-107">Return Value</span></span>  

 <span data-ttu-id="a6bd5-108">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6bd5-108">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6bd5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6bd5-109">Requirements</span></span>  

 <span data-ttu-id="a6bd5-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a6bd5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6bd5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6bd5-111">See also</span></span>

- [<span data-ttu-id="a6bd5-112">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6bd5-112">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)

---
description: '자세히 알아보기: ISymUnmanagedWriter5:: OpenMapTokensToSourceSpans 메서드'
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 1feeecaf943e3eed228ced2b0c968f3fe4b49f62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761514"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="fd968-103">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="fd968-103">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="fd968-104">특수 한 사용자 지정 데이터 섹션을 열어 토큰 대 소스 범위 매핑 정보를로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd968-104">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="fd968-105">메서드가 이미 열려 있거나 그 반대의 경우에는이 섹션을 열 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd968-105">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd968-106">구문</span><span class="sxs-lookup"><span data-stu-id="fd968-106">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fd968-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="fd968-107">Return Value</span></span>  

 <span data-ttu-id="fd968-108">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd968-108">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd968-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd968-109">Requirements</span></span>  

 <span data-ttu-id="fd968-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="fd968-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd968-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd968-111">See also</span></span>

- [<span data-ttu-id="fd968-112">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd968-112">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)

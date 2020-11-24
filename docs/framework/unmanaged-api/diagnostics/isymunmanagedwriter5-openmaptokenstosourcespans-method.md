---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 95976e2f331252c88eab717e184abc284842e3b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683266"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="9c3bb-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="9c3bb-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="9c3bb-103">특수 한 사용자 지정 데이터 섹션을 열어 토큰 대 소스 범위 매핑 정보를로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c3bb-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="9c3bb-104">메서드가 이미 열려 있거나 그 반대의 경우에는이 섹션을 열 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3bb-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c3bb-105">구문</span><span class="sxs-lookup"><span data-stu-id="9c3bb-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9c3bb-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="9c3bb-106">Return Value</span></span>  

 <span data-ttu-id="9c3bb-107">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9c3bb-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c3bb-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c3bb-108">Requirements</span></span>  

 <span data-ttu-id="9c3bb-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9c3bb-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c3bb-110">참조</span><span class="sxs-lookup"><span data-stu-id="9c3bb-110">See also</span></span>

- [<span data-ttu-id="9c3bb-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c3bb-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)

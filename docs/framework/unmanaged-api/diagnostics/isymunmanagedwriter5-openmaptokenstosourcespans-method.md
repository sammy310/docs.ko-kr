---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 004e1ddae8a6c0262846422a2eeb4314a4c82f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121616"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="43b3a-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="43b3a-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="43b3a-103">특수 한 사용자 지정 데이터 섹션을 열어 토큰 대 소스 범위 매핑 정보를로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="43b3a-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="43b3a-104">메서드가 이미 열려 있거나 그 반대의 경우에는이 섹션을 열 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="43b3a-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b3a-105">구문</span><span class="sxs-lookup"><span data-stu-id="43b3a-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="43b3a-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="43b3a-106">Return Value</span></span>  
 <span data-ttu-id="43b3a-107">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="43b3a-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b3a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43b3a-108">Requirements</span></span>  
 <span data-ttu-id="43b3a-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="43b3a-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b3a-110">참조</span><span class="sxs-lookup"><span data-stu-id="43b3a-110">See also</span></span>

- [<span data-ttu-id="43b3a-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43b3a-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)

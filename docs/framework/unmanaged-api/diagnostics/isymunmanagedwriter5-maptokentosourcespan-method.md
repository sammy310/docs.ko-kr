---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 0f00dd34ffbdd58a46260132d8d7ace74ec2f294
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501679"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="8eac0-102">ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="8eac0-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="8eac0-103">지정 된 소스 파일의 지정 된 소스 줄 범위에 지정 된 메타 데이터 토큰을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8eac0-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="8eac0-104">[OpenMapTokensToSourceSpans method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 및 [CloseMapTokensToSourceSpans 메서드에](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)대 한 호출 사이에 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eac0-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eac0-105">구문</span><span class="sxs-lookup"><span data-stu-id="8eac0-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eac0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8eac0-106">Parameters</span></span>  
  
|<span data-ttu-id="8eac0-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8eac0-107">Parameter</span></span>|<span data-ttu-id="8eac0-108">설명</span><span class="sxs-lookup"><span data-stu-id="8eac0-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="8eac0-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="8eac0-109">Return Value</span></span>  
 <span data-ttu-id="8eac0-110">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8eac0-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eac0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8eac0-111">Requirements</span></span>  
 <span data-ttu-id="8eac0-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8eac0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eac0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8eac0-113">See also</span></span>

- [<span data-ttu-id="8eac0-114">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eac0-114">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)

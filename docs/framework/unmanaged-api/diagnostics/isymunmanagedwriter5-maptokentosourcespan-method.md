---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 876804e7b825443116b1f44a02a685a73153915c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121621"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="52ddf-102">ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="52ddf-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="52ddf-103">지정 된 소스 파일의 지정 된 소스 줄 범위에 지정 된 메타 데이터 토큰을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="52ddf-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="52ddf-104">[OpenMapTokensToSourceSpans method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 및 [CloseMapTokensToSourceSpans 메서드에](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)대 한 호출 사이에 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ddf-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ddf-105">구문</span><span class="sxs-lookup"><span data-stu-id="52ddf-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52ddf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52ddf-106">Parameters</span></span>  
  
|<span data-ttu-id="52ddf-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52ddf-107">Parameter</span></span>|<span data-ttu-id="52ddf-108">설명</span><span class="sxs-lookup"><span data-stu-id="52ddf-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="52ddf-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="52ddf-109">Return Value</span></span>  
 <span data-ttu-id="52ddf-110">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="52ddf-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52ddf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52ddf-111">Requirements</span></span>  
 <span data-ttu-id="52ddf-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="52ddf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ddf-113">참조</span><span class="sxs-lookup"><span data-stu-id="52ddf-113">See also</span></span>

- [<span data-ttu-id="52ddf-114">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52ddf-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)

---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08c219dd033b39fc07159875b184cdf70e3aa3ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937867"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="2bcd8-102">ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="2bcd8-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="2bcd8-103">맵을 지정 된 소스 줄에 지정 된 메타 데이터 토큰이 지정 된 소스 파일의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="2bcd8-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="2bcd8-104">호출 사이 호출 해야 합니다 [OpenMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 하 고 [CloseMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2bcd8-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bcd8-105">구문</span><span class="sxs-lookup"><span data-stu-id="2bcd8-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bcd8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2bcd8-106">Parameters</span></span>  
  
|<span data-ttu-id="2bcd8-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2bcd8-107">Parameter</span></span>|<span data-ttu-id="2bcd8-108">설명</span><span class="sxs-lookup"><span data-stu-id="2bcd8-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="2bcd8-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="2bcd8-109">Return Value</span></span>  
 <span data-ttu-id="2bcd8-110">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2bcd8-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bcd8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bcd8-111">Requirements</span></span>  
 <span data-ttu-id="2bcd8-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2bcd8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bcd8-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="2bcd8-113">See also</span></span>

- [<span data-ttu-id="2bcd8-114">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2bcd8-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)

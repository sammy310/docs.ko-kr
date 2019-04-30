---
title: ISymUnmanagedWriter5 인터페이스
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6ed8c6e61c558a4bc9e3f92d559615ac93ecff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962346"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="1a843-102">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a843-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="1a843-103">ISymUnmanagedWriter5 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a843-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a843-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="1a843-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1a843-105">Methods</span></span>  
 <span data-ttu-id="1a843-106">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="1a843-107">메서드</span><span class="sxs-lookup"><span data-stu-id="1a843-107">Method</span></span>|<span data-ttu-id="1a843-108">설명</span><span class="sxs-lookup"><span data-stu-id="1a843-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a843-109">CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="1a843-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="1a843-110">매핑 정보 토큰-소스 범위에 대 한 특별 한 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="1a843-111">이 닫힌 후에 매핑 정보가 더 이상 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="1a843-112">MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="1a843-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="1a843-113">맵을 지정 된 소스 줄에 지정 된 메타 데이터 토큰이 지정 된 소스 파일의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="1a843-114">호출 사이 호출 해야 합니다 [OpenMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 하 고 [CloseMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="1a843-115">OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="1a843-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="1a843-116">토큰에서 소스로 범위 매핑 정보를 내보내는 데 특별 한 사용자 지정 데이터 섹션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="1a843-117">가 이미 열려 메서드나 그 반대의 경우 오류가 발생 하는 경우이 섹션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a843-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a843-118">Requirements</span></span>  
 <span data-ttu-id="1a843-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a843-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a843-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a843-120">See also</span></span>

- [<span data-ttu-id="1a843-121">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a843-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="1a843-122">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a843-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)

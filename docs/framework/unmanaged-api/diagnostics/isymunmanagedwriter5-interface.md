---
description: '자세히 알아보기: ISymUnmanagedWriter5 인터페이스'
title: ISymUnmanagedWriter5 인터페이스
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 0902385576e1eed17cea672b04858c7e3ef7add8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761631"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="2ee87-103">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ee87-103">ISymUnmanagedWriter5 Interface</span></span>

<span data-ttu-id="2ee87-104">ISymUnmanagedWriter5 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-104">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ee87-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ee87-105">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="2ee87-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2ee87-106">Methods</span></span>  

 <span data-ttu-id="2ee87-107">이 인터페이스에는 다음과 같은 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="2ee87-108">메서드</span><span class="sxs-lookup"><span data-stu-id="2ee87-108">Method</span></span>|<span data-ttu-id="2ee87-109">설명</span><span class="sxs-lookup"><span data-stu-id="2ee87-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ee87-110">CloseMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="2ee87-110">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="2ee87-111">토큰-소스 범위 매핑 정보에 대 한 특수 사용자 지정 데이터 섹션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-111">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="2ee87-112">닫힌 후에는 더 이상 매핑 정보를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-112">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="2ee87-113">MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="2ee87-113">MapTokenToSourceSpan Method</span></span>](isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="2ee87-114">지정 된 소스 파일의 지정 된 소스 줄 범위에 지정 된 메타 데이터 토큰을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-114">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="2ee87-115">[OpenMapTokensToSourceSpans method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 및 [CloseMapTokensToSourceSpans 메서드에](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)대 한 호출 사이에 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-115">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="2ee87-116">OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="2ee87-116">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="2ee87-117">특수 한 사용자 지정 데이터 섹션을 열어 토큰 대 소스 범위 매핑 정보를로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-117">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="2ee87-118">메서드가 이미 열려 있거나 그 반대의 경우에는이 섹션을 열 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee87-118">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ee87-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ee87-119">Requirements</span></span>  

 <span data-ttu-id="2ee87-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2ee87-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee87-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ee87-121">See also</span></span>

- [<span data-ttu-id="2ee87-122">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ee87-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="2ee87-123">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ee87-123">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)

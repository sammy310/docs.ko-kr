---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dc2ced988f7277c994eb9449e7c26efa5450b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968586"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="75b4d-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 메서드</span><span class="sxs-lookup"><span data-stu-id="75b4d-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="75b4d-103">토큰에서 소스로 범위 매핑 정보를 내보내는 데 특별 한 사용자 지정 데이터 섹션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="75b4d-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="75b4d-104">가 이미 열려 메서드나 그 반대의 경우 오류가 발생 하는 경우이 섹션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="75b4d-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b4d-105">구문</span><span class="sxs-lookup"><span data-stu-id="75b4d-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="75b4d-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="75b4d-106">Return Value</span></span>  
 <span data-ttu-id="75b4d-107">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="75b4d-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75b4d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75b4d-108">Requirements</span></span>  
 <span data-ttu-id="75b4d-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="75b4d-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b4d-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="75b4d-110">See also</span></span>

- [<span data-ttu-id="75b4d-111">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75b4d-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)

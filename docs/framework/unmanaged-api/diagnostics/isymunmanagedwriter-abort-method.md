---
title: ISymUnmanagedWriter::Abort 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 090183cad17aff6faf5e79639eadff086c1a26ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119537"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="e983b-102">ISymUnmanagedWriter::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="e983b-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="e983b-103">기호 저장소에 기호를 커밋하지 않고 기호 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e983b-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="e983b-104">이 호출 후 기호 작성기를 추가로 업데이트할 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e983b-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="e983b-105">기호 작성기를 닫고 기호를 커밋를 사용 합니다 [isymunmanagedwriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e983b-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e983b-106">구문</span><span class="sxs-lookup"><span data-stu-id="e983b-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e983b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e983b-107">Return Value</span></span>  
 <span data-ttu-id="e983b-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e983b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e983b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e983b-109">Requirements</span></span>  
 <span data-ttu-id="e983b-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e983b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e983b-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="e983b-111">See also</span></span>

- [<span data-ttu-id="e983b-112">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e983b-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

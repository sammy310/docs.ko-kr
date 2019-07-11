---
title: ISymUnmanagedWriter::CloseMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f77f30b84622dffd8c76bb9302ad564f40ed41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778182"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="82fbd-102">ISymUnmanagedWriter::CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="82fbd-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="82fbd-103">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="82fbd-103">Closes the current method.</span></span> <span data-ttu-id="82fbd-104">메서드 종료 되 면 그 없습니다 자세한 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82fbd-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82fbd-105">구문</span><span class="sxs-lookup"><span data-stu-id="82fbd-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="82fbd-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="82fbd-106">Return Value</span></span>  
 <span data-ttu-id="82fbd-107">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="82fbd-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82fbd-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82fbd-108">Requirements</span></span>  
 <span data-ttu-id="82fbd-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="82fbd-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82fbd-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="82fbd-110">See also</span></span>

- [<span data-ttu-id="82fbd-111">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82fbd-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="82fbd-112">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="82fbd-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

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
ms.openlocfilehash: 591279a80b7d6a770127fb98eb71c056c48bdffd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231216"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="d6d22-102">ISymUnmanagedWriter::CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="d6d22-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="d6d22-103">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d22-103">Closes the current method.</span></span> <span data-ttu-id="d6d22-104">메서드 종료 되 면 그 없습니다 자세한 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d22-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6d22-105">구문</span><span class="sxs-lookup"><span data-stu-id="d6d22-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d6d22-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="d6d22-106">Return Value</span></span>  
 <span data-ttu-id="d6d22-107">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d22-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6d22-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6d22-108">Requirements</span></span>  
 <span data-ttu-id="d6d22-109">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d6d22-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d22-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="d6d22-110">See also</span></span>

- [<span data-ttu-id="d6d22-111">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6d22-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d6d22-112">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="d6d22-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

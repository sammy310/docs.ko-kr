---
title: ISymUnmanagedDispose::Destroy 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d2f0aedffdd88974a8184954ecbb9a231b70c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939947"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="cd155-102">ISymUnmanagedDispose::Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="cd155-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="cd155-103">이 인해 기본 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd155-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd155-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd155-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cd155-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="cd155-105">Return Value</span></span>  
 <span data-ttu-id="cd155-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cd155-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd155-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd155-107">Requirements</span></span>  
 <span data-ttu-id="cd155-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cd155-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd155-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="cd155-109">See also</span></span>

- [<span data-ttu-id="cd155-110">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd155-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)

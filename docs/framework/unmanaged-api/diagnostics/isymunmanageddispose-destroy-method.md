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
ms.openlocfilehash: 6a31026f5b1669c0c29762048dc2c5c1c7bbb6a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732829"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="4b545-102">ISymUnmanagedDispose::Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="4b545-102">ISymUnmanagedDispose::Destroy Method</span></span>

<span data-ttu-id="4b545-103">내부 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 실패를 반환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b545-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b545-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b545-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4b545-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="4b545-105">Return Value</span></span>  

 <span data-ttu-id="4b545-106">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b545-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b545-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b545-107">Requirements</span></span>  

 <span data-ttu-id="4b545-108">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4b545-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b545-109">참조</span><span class="sxs-lookup"><span data-stu-id="4b545-109">See also</span></span>

- [<span data-ttu-id="4b545-110">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b545-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)

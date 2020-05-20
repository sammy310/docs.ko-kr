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
ms.openlocfilehash: 5bd94cb851d4bb044d4ce03b97d6342a2c9652e4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441320"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="af1a5-102">ISymUnmanagedDispose::Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="af1a5-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="af1a5-103">내부 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 실패를 반환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1a5-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af1a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="af1a5-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="af1a5-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="af1a5-105">Return Value</span></span>  
 <span data-ttu-id="af1a5-106">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="af1a5-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af1a5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af1a5-107">Requirements</span></span>  
 <span data-ttu-id="af1a5-108">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="af1a5-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1a5-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af1a5-109">See also</span></span>

- [<span data-ttu-id="af1a5-110">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af1a5-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)

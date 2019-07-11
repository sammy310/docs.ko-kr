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
ms.openlocfilehash: 23228c1414f5f6327cfb326c95a3224ae231a033
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776779"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="45eda-102">ISymUnmanagedDispose::Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="45eda-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="45eda-103">이 인해 기본 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eda-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45eda-104">구문</span><span class="sxs-lookup"><span data-stu-id="45eda-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="45eda-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="45eda-105">Return Value</span></span>  
 <span data-ttu-id="45eda-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="45eda-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45eda-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45eda-107">Requirements</span></span>  
 <span data-ttu-id="45eda-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="45eda-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45eda-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="45eda-109">See also</span></span>

- [<span data-ttu-id="45eda-110">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45eda-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)

---
description: ISymUnmanagedDispose::D estroy 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 3c13f90e08f2ba0dd7c70acc3321913b14195f1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790206"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="2aff9-103">ISymUnmanagedDispose::Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="2aff9-103">ISymUnmanagedDispose::Destroy Method</span></span>

<span data-ttu-id="2aff9-104">내부 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 실패를 반환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aff9-104">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aff9-105">구문</span><span class="sxs-lookup"><span data-stu-id="2aff9-105">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2aff9-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="2aff9-106">Return Value</span></span>  

 <span data-ttu-id="2aff9-107">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2aff9-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aff9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2aff9-108">Requirements</span></span>  

 <span data-ttu-id="2aff9-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2aff9-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aff9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2aff9-110">See also</span></span>

- [<span data-ttu-id="2aff9-111">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2aff9-111">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)

---
title: ISymUnmanagedWriter3::Commit 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
ms.openlocfilehash: 5985257a186839a297c245b23f093f0b18a798fe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438276"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="c7a81-102">ISymUnmanagedWriter3::Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="c7a81-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="c7a81-103">지금까지 작성 된 변경 내용을 스트림에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="c7a81-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a81-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7a81-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c7a81-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7a81-105">Return Value</span></span>  
 <span data-ttu-id="c7a81-106">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c7a81-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a81-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7a81-107">Requirements</span></span>  
 <span data-ttu-id="c7a81-108">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c7a81-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a81-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7a81-109">See also</span></span>

- [<span data-ttu-id="c7a81-110">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7a81-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

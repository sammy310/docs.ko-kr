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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f531b96211a1dd6072d62937b9f93fc17f105d4d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149047"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="21980-102">ISymUnmanagedWriter3::Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="21980-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="21980-103">지금까지 작성 된 스트림에 변경 내용을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="21980-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21980-104">구문</span><span class="sxs-lookup"><span data-stu-id="21980-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="21980-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="21980-105">Return Value</span></span>  
 <span data-ttu-id="21980-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="21980-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21980-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21980-107">Requirements</span></span>  
 <span data-ttu-id="21980-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="21980-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21980-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="21980-109">See also</span></span>

- [<span data-ttu-id="21980-110">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21980-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

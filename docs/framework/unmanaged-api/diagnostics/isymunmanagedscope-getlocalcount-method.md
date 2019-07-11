---
title: ISymUnmanagedScope::GetLocalCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c41c05d40187aaed8a4f3cce181c84460503d1f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751279"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="84268-102">ISymUnmanagedScope::GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="84268-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="84268-103">이 범위 내에 정의 된 로컬 변수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="84268-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84268-104">구문</span><span class="sxs-lookup"><span data-stu-id="84268-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84268-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84268-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="84268-106">[out] 에 대 한 포인터를 `ULONG32` 로컬 변수 수를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="84268-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84268-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="84268-107">Return Value</span></span>  
 <span data-ttu-id="84268-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="84268-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84268-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84268-109">Requirements</span></span>  
 <span data-ttu-id="84268-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="84268-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84268-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="84268-111">See also</span></span>

- [<span data-ttu-id="84268-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84268-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

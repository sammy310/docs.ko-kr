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
ms.openlocfilehash: 3b5dbe875b47f48c24c5e955abddb2c6f778bcdd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446343"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="07d76-102">ISymUnmanagedScope::GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="07d76-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="07d76-103">이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07d76-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d76-104">구문</span><span class="sxs-lookup"><span data-stu-id="07d76-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07d76-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07d76-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="07d76-106">제한이 지역 변수의 개수를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07d76-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07d76-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="07d76-107">Return Value</span></span>  
 <span data-ttu-id="07d76-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="07d76-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07d76-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07d76-109">Requirements</span></span>  
 <span data-ttu-id="07d76-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="07d76-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d76-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07d76-111">See also</span></span>

- [<span data-ttu-id="07d76-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07d76-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

---
title: ISymUnmanagedMethod::GetRootScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: c956f5d68c992f1b08988e59038e8667b391f734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448919"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="2ac71-102">ISymUnmanagedMethod::GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="2ac71-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="2ac71-103">Gets the root lexical scope within this method.</span><span class="sxs-lookup"><span data-stu-id="2ac71-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="2ac71-104">This scope encloses the entire method.</span><span class="sxs-lookup"><span data-stu-id="2ac71-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac71-105">구문</span><span class="sxs-lookup"><span data-stu-id="2ac71-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ac71-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ac71-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2ac71-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="2ac71-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ac71-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="2ac71-108">Return Value</span></span>  
 <span data-ttu-id="2ac71-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="2ac71-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac71-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ac71-110">Requirements</span></span>  
 <span data-ttu-id="2ac71-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2ac71-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac71-112">참조</span><span class="sxs-lookup"><span data-stu-id="2ac71-112">See also</span></span>

- [<span data-ttu-id="2ac71-113">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ac71-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

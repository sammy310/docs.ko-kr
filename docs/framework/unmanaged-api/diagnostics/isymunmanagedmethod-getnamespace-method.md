---
title: ISymUnmanagedMethod::GetNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: b8bbedb4c60a2df6070373f2b6a104fff094869a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448973"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="546df-102">ISymUnmanagedMethod::GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="546df-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="546df-103">Gets the namespace within which this method is defined.</span><span class="sxs-lookup"><span data-stu-id="546df-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="546df-104">구문</span><span class="sxs-lookup"><span data-stu-id="546df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="546df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="546df-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="546df-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="546df-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="546df-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="546df-107">Return Value</span></span>  
 <span data-ttu-id="546df-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="546df-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="546df-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="546df-109">Requirements</span></span>  
 <span data-ttu-id="546df-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="546df-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546df-111">참조</span><span class="sxs-lookup"><span data-stu-id="546df-111">See also</span></span>

- [<span data-ttu-id="546df-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="546df-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

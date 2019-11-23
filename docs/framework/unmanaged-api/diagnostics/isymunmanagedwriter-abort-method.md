---
title: ISymUnmanagedWriter::Abort 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 6074ec5248d27b1405d2367349904f6630df951b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445988"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="6f8e5-102">ISymUnmanagedWriter::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="6f8e5-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="6f8e5-103">Closes the symbol writer without committing the symbols to the symbol store.</span><span class="sxs-lookup"><span data-stu-id="6f8e5-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="6f8e5-104">After this call, the symbol writer becomes invalid for further updates.</span><span class="sxs-lookup"><span data-stu-id="6f8e5-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="6f8e5-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span><span class="sxs-lookup"><span data-stu-id="6f8e5-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f8e5-106">구문</span><span class="sxs-lookup"><span data-stu-id="6f8e5-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6f8e5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6f8e5-107">Return Value</span></span>  
 <span data-ttu-id="6f8e5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="6f8e5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f8e5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f8e5-109">Requirements</span></span>  
 <span data-ttu-id="6f8e5-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6f8e5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f8e5-111">참조</span><span class="sxs-lookup"><span data-stu-id="6f8e5-111">See also</span></span>

- [<span data-ttu-id="6f8e5-112">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f8e5-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

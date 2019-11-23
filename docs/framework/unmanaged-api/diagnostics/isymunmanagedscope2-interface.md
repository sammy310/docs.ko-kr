---
title: ISymUnmanagedScope2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 3374097c8d343fed6badf046742ca556d2a92f3e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446222"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="2a5dd-102">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a5dd-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="2a5dd-103">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="2a5dd-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="2a5dd-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span><span class="sxs-lookup"><span data-stu-id="2a5dd-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a5dd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2a5dd-105">Methods</span></span>  
  
|<span data-ttu-id="2a5dd-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2a5dd-106">Method</span></span>|<span data-ttu-id="2a5dd-107">설명</span><span class="sxs-lookup"><span data-stu-id="2a5dd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a5dd-108">GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="2a5dd-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="2a5dd-109">Gets a count of the constants defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="2a5dd-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="2a5dd-110">GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="2a5dd-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="2a5dd-111">Gets the local constants defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="2a5dd-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a5dd-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a5dd-112">Requirements</span></span>  
 <span data-ttu-id="2a5dd-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2a5dd-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a5dd-114">참조</span><span class="sxs-lookup"><span data-stu-id="2a5dd-114">See also</span></span>

- [<span data-ttu-id="2a5dd-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a5dd-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="2a5dd-116">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a5dd-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

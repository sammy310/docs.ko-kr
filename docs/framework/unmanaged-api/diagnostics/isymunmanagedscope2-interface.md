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
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="23c0c-102">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23c0c-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="23c0c-103">메서드 내의 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23c0c-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="23c0c-104">이 인터페이스는 범위 내에 정의 된 상수에 대 한 정보를 가져오는 메서드로 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c0c-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23c0c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="23c0c-105">Methods</span></span>  
  
|<span data-ttu-id="23c0c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="23c0c-106">Method</span></span>|<span data-ttu-id="23c0c-107">설명</span><span class="sxs-lookup"><span data-stu-id="23c0c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23c0c-108">GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="23c0c-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="23c0c-109">이 범위 내에 정의 된 상수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23c0c-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="23c0c-110">GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="23c0c-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="23c0c-111">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23c0c-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23c0c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23c0c-112">Requirements</span></span>  
 <span data-ttu-id="23c0c-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="23c0c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c0c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23c0c-114">See also</span></span>

- [<span data-ttu-id="23c0c-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23c0c-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="23c0c-116">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23c0c-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

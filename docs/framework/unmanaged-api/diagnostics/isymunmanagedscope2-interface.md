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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0109b25b1cdc42204fc4873577e495641c4ec4fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131458"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="d366e-102">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d366e-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="d366e-103">메서드 내에서 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d366e-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="d366e-104">이 인터페이스를 확장 합니다 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 범위 내에서 정의 된 상수에 대 한 정보를 가져오는 메서드를 사용 하 여 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d366e-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d366e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d366e-105">Methods</span></span>  
  
|<span data-ttu-id="d366e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d366e-106">Method</span></span>|<span data-ttu-id="d366e-107">설명</span><span class="sxs-lookup"><span data-stu-id="d366e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d366e-108">GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="d366e-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="d366e-109">이 범위 내에 정의 된 상수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d366e-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="d366e-110">GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="d366e-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="d366e-111">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d366e-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d366e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d366e-112">Requirements</span></span>  
 <span data-ttu-id="d366e-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d366e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d366e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="d366e-114">See also</span></span>

- [<span data-ttu-id="d366e-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d366e-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d366e-116">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d366e-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)

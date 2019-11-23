---
title: ISymUnmanagedScope 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 8da4da38d23ed65a0fdc44a0f919ee8cad2fe18e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446271"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="e9ff4-102">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ff4-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="e9ff4-103">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9ff4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-104">Methods</span></span>  
  
|<span data-ttu-id="e9ff4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-105">Method</span></span>|<span data-ttu-id="e9ff4-106">설명</span><span class="sxs-lookup"><span data-stu-id="e9ff4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9ff4-107">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="e9ff4-108">Gets the children of this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="e9ff4-109">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="e9ff4-110">Gets the end offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="e9ff4-111">GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="e9ff4-112">Gets a count of the local variables defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="e9ff4-113">GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="e9ff4-114">Gets the local variables defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="e9ff4-115">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="e9ff4-116">Gets the method that contains this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="e9ff4-117">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="e9ff4-118">Gets the namespaces that are being used within this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="e9ff4-119">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="e9ff4-120">Gets the parent scope of this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="e9ff4-121">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="e9ff4-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="e9ff4-122">Gets the start offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="e9ff4-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9ff4-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9ff4-123">Requirements</span></span>  
 <span data-ttu-id="e9ff4-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e9ff4-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ff4-125">참조</span><span class="sxs-lookup"><span data-stu-id="e9ff4-125">See also</span></span>

- [<span data-ttu-id="e9ff4-126">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ff4-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e9ff4-127">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9ff4-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)

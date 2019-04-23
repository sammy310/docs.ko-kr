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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809368ea19528a7ce00d4fcada06ef5724eb79a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228161"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="8bc45-102">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bc45-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="8bc45-103">메서드 내에서 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8bc45-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-104">Methods</span></span>  
  
|<span data-ttu-id="8bc45-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-105">Method</span></span>|<span data-ttu-id="8bc45-106">설명</span><span class="sxs-lookup"><span data-stu-id="8bc45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bc45-107">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="8bc45-108">이 범위의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="8bc45-109">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="8bc45-110">이 범위의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="8bc45-111">GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="8bc45-112">이 범위 내에 정의 된 로컬 변수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="8bc45-113">GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="8bc45-114">이 범위 내에 정의 된 로컬 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="8bc45-115">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="8bc45-116">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="8bc45-117">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="8bc45-118">이 범위 내에서 사용 되 고 있는 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="8bc45-119">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="8bc45-120">이 범위의 상위 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="8bc45-121">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="8bc45-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="8bc45-122">이 범위에 대 한 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bc45-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8bc45-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bc45-123">Requirements</span></span>  
 <span data-ttu-id="8bc45-124">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8bc45-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc45-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="8bc45-125">See also</span></span>

- [<span data-ttu-id="8bc45-126">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bc45-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="8bc45-127">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bc45-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)

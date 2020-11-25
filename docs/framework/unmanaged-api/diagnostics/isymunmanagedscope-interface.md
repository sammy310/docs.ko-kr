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
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725887"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="2178d-102">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2178d-102">ISymUnmanagedScope Interface</span></span>

<span data-ttu-id="2178d-103">메서드 내의 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2178d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-104">Methods</span></span>  
  
|<span data-ttu-id="2178d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-105">Method</span></span>|<span data-ttu-id="2178d-106">설명</span><span class="sxs-lookup"><span data-stu-id="2178d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2178d-107">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="2178d-108">이 범위의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="2178d-109">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="2178d-110">이 범위에 대 한 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="2178d-111">GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="2178d-112">이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="2178d-113">GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="2178d-114">이 범위 내에 정의 된 지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="2178d-115">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="2178d-116">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="2178d-117">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="2178d-118">이 범위 내에서 사용 되는 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="2178d-119">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="2178d-120">이 범위의 부모 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="2178d-121">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="2178d-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="2178d-122">이 범위의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2178d-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2178d-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2178d-123">Requirements</span></span>  

 <span data-ttu-id="2178d-124">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2178d-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2178d-125">참조</span><span class="sxs-lookup"><span data-stu-id="2178d-125">See also</span></span>

- [<span data-ttu-id="2178d-126">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2178d-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="2178d-127">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2178d-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)

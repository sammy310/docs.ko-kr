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
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615347"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="6a229-102">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a229-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="6a229-103">메서드 내의 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a229-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-104">Methods</span></span>  
  
|<span data-ttu-id="6a229-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-105">Method</span></span>|<span data-ttu-id="6a229-106">설명</span><span class="sxs-lookup"><span data-stu-id="6a229-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a229-107">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="6a229-108">이 범위의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="6a229-109">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="6a229-110">이 범위에 대 한 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="6a229-111">GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="6a229-112">이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="6a229-113">GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="6a229-114">이 범위 내에 정의 된 지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="6a229-115">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="6a229-116">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="6a229-117">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="6a229-118">이 범위 내에서 사용 되는 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="6a229-119">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="6a229-120">이 범위의 부모 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="6a229-121">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6a229-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="6a229-122">이 범위의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a229-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a229-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a229-123">Requirements</span></span>  
 <span data-ttu-id="6a229-124">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6a229-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a229-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a229-125">See also</span></span>

- [<span data-ttu-id="6a229-126">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a229-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="6a229-127">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a229-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)

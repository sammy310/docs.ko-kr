---
description: '자세히 알아보기: ISymUnmanagedScope 인터페이스'
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
ms.openlocfilehash: f1175656fb49ee16fd1cd676d08f6ebb76f40c6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763269"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="31f3d-103">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31f3d-103">ISymUnmanagedScope Interface</span></span>

<span data-ttu-id="31f3d-104">메서드 내의 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-104">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31f3d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-105">Methods</span></span>  
  
|<span data-ttu-id="31f3d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-106">Method</span></span>|<span data-ttu-id="31f3d-107">설명</span><span class="sxs-lookup"><span data-stu-id="31f3d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31f3d-108">GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-108">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="31f3d-109">이 범위의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-109">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="31f3d-110">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-110">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="31f3d-111">이 범위에 대 한 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-111">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="31f3d-112">GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-112">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="31f3d-113">이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-113">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="31f3d-114">GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-114">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="31f3d-115">이 범위 내에 정의 된 지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-115">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="31f3d-116">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-116">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="31f3d-117">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-117">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="31f3d-118">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-118">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="31f3d-119">이 범위 내에서 사용 되는 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-119">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="31f3d-120">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-120">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="31f3d-121">이 범위의 부모 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-121">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="31f3d-122">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="31f3d-122">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="31f3d-123">이 범위의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31f3d-123">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31f3d-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31f3d-124">Requirements</span></span>  

 <span data-ttu-id="31f3d-125">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="31f3d-125">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f3d-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31f3d-126">See also</span></span>

- [<span data-ttu-id="31f3d-127">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31f3d-127">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="31f3d-128">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31f3d-128">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)

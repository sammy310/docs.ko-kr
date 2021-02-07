---
description: '자세히 알아보기: ISymUnmanagedWriter2 인터페이스'
title: ISymUnmanagedWriter2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 228bae40e12376b3b5e8ca3bbd3463ba70a6d67b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761780"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="13ad8-103">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13ad8-103">ISymUnmanagedWriter2 Interface</span></span>

<span data-ttu-id="13ad8-104">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13ad8-104">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="13ad8-105">이 인터페이스는 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ad8-105">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13ad8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="13ad8-106">Methods</span></span>  
  
|<span data-ttu-id="13ad8-107">메서드</span><span class="sxs-lookup"><span data-stu-id="13ad8-107">Method</span></span>|<span data-ttu-id="13ad8-108">설명</span><span class="sxs-lookup"><span data-stu-id="13ad8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13ad8-109">DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="13ad8-109">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="13ad8-110">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ad8-110">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="13ad8-111">DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="13ad8-111">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="13ad8-112">단일 전역 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13ad8-112">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="13ad8-113">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="13ad8-113">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="13ad8-114">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13ad8-114">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13ad8-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13ad8-115">Requirements</span></span>  

 <span data-ttu-id="13ad8-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="13ad8-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ad8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13ad8-117">See also</span></span>

- [<span data-ttu-id="13ad8-118">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13ad8-118">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="13ad8-119">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13ad8-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="13ad8-120">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13ad8-120">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)

---
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
ms.openlocfilehash: 6feb48b7c78dda64ba372e470b83ffb14f21f2f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683331"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="c0108-102">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0108-102">ISymUnmanagedWriter2 Interface</span></span>

<span data-ttu-id="c0108-103">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0108-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="c0108-104">이 인터페이스는 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0108-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0108-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c0108-105">Methods</span></span>  
  
|<span data-ttu-id="c0108-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c0108-106">Method</span></span>|<span data-ttu-id="c0108-107">설명</span><span class="sxs-lookup"><span data-stu-id="c0108-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0108-108">DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="c0108-108">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="c0108-109">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0108-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="c0108-110">DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="c0108-110">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="c0108-111">단일 전역 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0108-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="c0108-112">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="c0108-112">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="c0108-113">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0108-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0108-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0108-114">Requirements</span></span>  

 <span data-ttu-id="c0108-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c0108-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0108-116">참조</span><span class="sxs-lookup"><span data-stu-id="c0108-116">See also</span></span>

- [<span data-ttu-id="c0108-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0108-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c0108-118">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0108-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c0108-119">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0108-119">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)

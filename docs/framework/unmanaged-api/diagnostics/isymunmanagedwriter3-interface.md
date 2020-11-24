---
title: ISymUnmanagedWriter3 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: dfc2e39a6a39e7386bd7358d422d5c6978ec42ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683292"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="135a6-102">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="135a6-102">ISymUnmanagedWriter3 Interface</span></span>

<span data-ttu-id="135a6-103">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="135a6-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="135a6-104">이 인터페이스는 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="135a6-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="135a6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="135a6-105">Methods</span></span>  
  
|<span data-ttu-id="135a6-106">메서드</span><span class="sxs-lookup"><span data-stu-id="135a6-106">Method</span></span>|<span data-ttu-id="135a6-107">설명</span><span class="sxs-lookup"><span data-stu-id="135a6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="135a6-108">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="135a6-108">Commit Method</span></span>](isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="135a6-109">지금까지 작성 된 변경 내용을 스트림에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="135a6-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="135a6-110">OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="135a6-110">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="135a6-111">메서드를 열고 이미지의 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="135a6-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="135a6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="135a6-112">Requirements</span></span>  

 <span data-ttu-id="135a6-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="135a6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="135a6-114">참조</span><span class="sxs-lookup"><span data-stu-id="135a6-114">See also</span></span>

- [<span data-ttu-id="135a6-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="135a6-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="135a6-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="135a6-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="135a6-117">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="135a6-117">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)

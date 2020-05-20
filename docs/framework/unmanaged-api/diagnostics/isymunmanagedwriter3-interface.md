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
ms.openlocfilehash: 006045ce101884119f676e4f6324815eb21a10a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614658"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="bad75-102">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bad75-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="bad75-103">기호 작성기를 나타내며 문서, 시퀀스 위치, 어휘 범위 및 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad75-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="bad75-104">이 인터페이스는 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad75-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bad75-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bad75-105">Methods</span></span>  
  
|<span data-ttu-id="bad75-106">메서드</span><span class="sxs-lookup"><span data-stu-id="bad75-106">Method</span></span>|<span data-ttu-id="bad75-107">설명</span><span class="sxs-lookup"><span data-stu-id="bad75-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bad75-108">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="bad75-108">Commit Method</span></span>](isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="bad75-109">지금까지 작성 된 변경 내용을 스트림에 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="bad75-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="bad75-110">OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="bad75-110">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="bad75-111">메서드를 열고 이미지의 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad75-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bad75-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bad75-112">Requirements</span></span>  
 <span data-ttu-id="bad75-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="bad75-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad75-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bad75-114">See also</span></span>

- [<span data-ttu-id="bad75-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bad75-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="bad75-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bad75-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="bad75-117">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bad75-117">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)

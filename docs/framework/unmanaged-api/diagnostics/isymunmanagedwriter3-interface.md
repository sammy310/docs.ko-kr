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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e26d79a5b597b8585f2fffd7f3945f00832ca134
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138458"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="86452-102">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86452-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="86452-103">기호 작성기를 나타내며 문서 "," 시퀀스 위치 "," 어휘 범위 "및" 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86452-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="86452-104">이 인터페이스를 확장 합니다 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="86452-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86452-105">메서드</span><span class="sxs-lookup"><span data-stu-id="86452-105">Methods</span></span>  
  
|<span data-ttu-id="86452-106">메서드</span><span class="sxs-lookup"><span data-stu-id="86452-106">Method</span></span>|<span data-ttu-id="86452-107">설명</span><span class="sxs-lookup"><span data-stu-id="86452-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86452-108">Commit 메서드</span><span class="sxs-lookup"><span data-stu-id="86452-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="86452-109">지금까지 작성 된 스트림에 변경 내용을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="86452-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="86452-110">OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="86452-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="86452-111">메서드를 열고 하 고 이미지의 해당 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86452-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86452-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86452-112">Requirements</span></span>  
 <span data-ttu-id="86452-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="86452-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86452-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="86452-114">See also</span></span>

- [<span data-ttu-id="86452-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86452-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="86452-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86452-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="86452-117">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86452-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)

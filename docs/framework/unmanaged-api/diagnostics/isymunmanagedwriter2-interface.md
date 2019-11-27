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
ms.openlocfilehash: c7f0235aa7096a790a0fd956081e330c8fdad9fe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438261"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="b344d-102">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b344d-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="b344d-103">기호 작성기를 나타내며 문서, 시퀀스 위치, 어휘 범위 및 변수를 정의 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b344d-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="b344d-104">이 인터페이스는 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b344d-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b344d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b344d-105">Methods</span></span>  
  
|<span data-ttu-id="b344d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b344d-106">Method</span></span>|<span data-ttu-id="b344d-107">설명</span><span class="sxs-lookup"><span data-stu-id="b344d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b344d-108">DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="b344d-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="b344d-109">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b344d-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="b344d-110">DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="b344d-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="b344d-111">단일 전역 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b344d-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="b344d-112">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="b344d-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="b344d-113">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b344d-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b344d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b344d-114">Requirements</span></span>  
 <span data-ttu-id="b344d-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="b344d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b344d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="b344d-116">See also</span></span>

- [<span data-ttu-id="b344d-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b344d-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="b344d-118">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b344d-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b344d-119">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b344d-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

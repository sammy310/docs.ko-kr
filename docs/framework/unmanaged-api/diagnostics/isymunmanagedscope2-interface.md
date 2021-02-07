---
description: '자세히 알아보기: ISymUnmanagedScope2 인터페이스'
title: ISymUnmanagedScope2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: a15094da68b00dbec454b2f6a642ac333f9a34ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763152"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="c701f-103">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c701f-103">ISymUnmanagedScope2 Interface</span></span>

<span data-ttu-id="c701f-104">메서드 내의 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c701f-104">Represents a lexical scope within a method.</span></span> <span data-ttu-id="c701f-105">이 인터페이스는 범위 내에 정의 된 상수에 대 한 정보를 가져오는 메서드로 [ISymUnmanagedScope](isymunmanagedscope-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c701f-105">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c701f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c701f-106">Methods</span></span>  
  
|<span data-ttu-id="c701f-107">메서드</span><span class="sxs-lookup"><span data-stu-id="c701f-107">Method</span></span>|<span data-ttu-id="c701f-108">설명</span><span class="sxs-lookup"><span data-stu-id="c701f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c701f-109">GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c701f-109">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="c701f-110">이 범위 내에 정의 된 상수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c701f-110">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="c701f-111">GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="c701f-111">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="c701f-112">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c701f-112">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c701f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c701f-113">Requirements</span></span>  

 <span data-ttu-id="c701f-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c701f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c701f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c701f-115">See also</span></span>

- [<span data-ttu-id="c701f-116">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c701f-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c701f-117">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c701f-117">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)

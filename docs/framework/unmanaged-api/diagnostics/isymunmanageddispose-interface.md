---
description: '자세히 알아보기: ISymUnmanagedDispose 인터페이스'
title: ISymUnmanagedDispose 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
ms.openlocfilehash: a94a8e8e462b5031cac3f0a8702a5685f993910d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790180"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="a202d-103">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a202d-103">ISymUnmanagedDispose Interface</span></span>

<span data-ttu-id="a202d-104">관리 되지 않는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a202d-104">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a202d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a202d-105">Methods</span></span>  
  
|<span data-ttu-id="a202d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a202d-106">Method</span></span>|<span data-ttu-id="a202d-107">설명</span><span class="sxs-lookup"><span data-stu-id="a202d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a202d-108">Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="a202d-108">Destroy Method</span></span>](isymunmanageddispose-destroy-method.md)|<span data-ttu-id="a202d-109">내부 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 실패를 반환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a202d-109">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a202d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a202d-110">Requirements</span></span>  

 <span data-ttu-id="a202d-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a202d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a202d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a202d-112">See also</span></span>

- [<span data-ttu-id="a202d-113">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a202d-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

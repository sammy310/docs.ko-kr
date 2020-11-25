---
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
ms.openlocfilehash: 932e76e73d5d40b36abcb17d8a53e6745927d873
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719608"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="cfa59-102">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cfa59-102">ISymUnmanagedDispose Interface</span></span>

<span data-ttu-id="cfa59-103">관리 되지 않는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa59-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfa59-104">메서드</span><span class="sxs-lookup"><span data-stu-id="cfa59-104">Methods</span></span>  
  
|<span data-ttu-id="cfa59-105">메서드</span><span class="sxs-lookup"><span data-stu-id="cfa59-105">Method</span></span>|<span data-ttu-id="cfa59-106">설명</span><span class="sxs-lookup"><span data-stu-id="cfa59-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfa59-107">Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="cfa59-107">Destroy Method</span></span>](isymunmanageddispose-destroy-method.md)|<span data-ttu-id="cfa59-108">내부 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 실패를 반환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa59-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfa59-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfa59-109">Requirements</span></span>  

 <span data-ttu-id="cfa59-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="cfa59-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa59-111">참조</span><span class="sxs-lookup"><span data-stu-id="cfa59-111">See also</span></span>

- [<span data-ttu-id="cfa59-112">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cfa59-112">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

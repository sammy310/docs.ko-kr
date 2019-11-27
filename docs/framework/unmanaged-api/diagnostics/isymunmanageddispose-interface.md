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
ms.openlocfilehash: 08d9ba8f8c9a251bd0db0ffe256af7db0164ba2f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449235"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="66281-102">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66281-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="66281-103">관리 되지 않는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="66281-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66281-104">메서드</span><span class="sxs-lookup"><span data-stu-id="66281-104">Methods</span></span>  
  
|<span data-ttu-id="66281-105">메서드</span><span class="sxs-lookup"><span data-stu-id="66281-105">Method</span></span>|<span data-ttu-id="66281-106">설명</span><span class="sxs-lookup"><span data-stu-id="66281-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66281-107">Destroy 메서드</span><span class="sxs-lookup"><span data-stu-id="66281-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="66281-108">내부 개체가 모든 내부 참조를 해제 하 고 모든 후속 메서드 호출에서 실패를 반환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="66281-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66281-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66281-109">Requirements</span></span>  
 <span data-ttu-id="66281-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="66281-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66281-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66281-111">See also</span></span>

- [<span data-ttu-id="66281-112">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66281-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

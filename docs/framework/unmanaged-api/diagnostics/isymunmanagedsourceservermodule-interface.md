---
title: ISymUnmanagedSourceServerModule 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ba81c208c4b49342c6a055e09ba898871db1851
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157614"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="52c6d-102">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52c6d-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="52c6d-103">모듈에 대 한 원본 서버 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52c6d-103">Provides source server data for a module.</span></span> <span data-ttu-id="52c6d-104">호출 하 여이 인터페이스를 가져올 `QueryInterface` 구현 하는 개체에는 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="52c6d-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52c6d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="52c6d-105">Methods</span></span>  
  
|<span data-ttu-id="52c6d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="52c6d-106">Method</span></span>|<span data-ttu-id="52c6d-107">설명</span><span class="sxs-lookup"><span data-stu-id="52c6d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52c6d-108">GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="52c6d-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="52c6d-109">모듈에 대 한 원본 서버 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="52c6d-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52c6d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52c6d-110">Requirements</span></span>  
 <span data-ttu-id="52c6d-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52c6d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c6d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="52c6d-112">See also</span></span>

- [<span data-ttu-id="52c6d-113">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52c6d-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

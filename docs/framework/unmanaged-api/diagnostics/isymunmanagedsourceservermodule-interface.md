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
ms.openlocfilehash: 9eac87d7627f502b13d805b8c5656e01ac578e7f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446202"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="bfa9c-102">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfa9c-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="bfa9c-103">모듈에 대 한 소스 서버 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-103">Provides source server data for a module.</span></span> <span data-ttu-id="bfa9c-104">[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서 `QueryInterface`를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bfa9c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bfa9c-105">Methods</span></span>  
  
|<span data-ttu-id="bfa9c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="bfa9c-106">Method</span></span>|<span data-ttu-id="bfa9c-107">설명</span><span class="sxs-lookup"><span data-stu-id="bfa9c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bfa9c-108">GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="bfa9c-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="bfa9c-109">모듈에 대 한 원본 서버 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa9c-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfa9c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfa9c-110">Requirements</span></span>  
 <span data-ttu-id="bfa9c-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="bfa9c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa9c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfa9c-112">See also</span></span>

- [<span data-ttu-id="bfa9c-113">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfa9c-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

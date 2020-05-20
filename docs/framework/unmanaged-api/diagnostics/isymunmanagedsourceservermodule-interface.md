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
ms.openlocfilehash: d90a55b53ba00540137e44fc190790c4710903e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610797"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="5b430-102">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b430-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="5b430-103">모듈에 대 한 소스 서버 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-103">Provides source server data for a module.</span></span> <span data-ttu-id="5b430-104">`QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b430-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5b430-105">Methods</span></span>  
  
|<span data-ttu-id="5b430-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5b430-106">Method</span></span>|<span data-ttu-id="5b430-107">설명</span><span class="sxs-lookup"><span data-stu-id="5b430-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b430-108">GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="5b430-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="5b430-109">모듈에 대 한 원본 서버 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b430-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b430-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b430-110">Requirements</span></span>  
 <span data-ttu-id="5b430-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5b430-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b430-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b430-112">See also</span></span>

- [<span data-ttu-id="5b430-113">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b430-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

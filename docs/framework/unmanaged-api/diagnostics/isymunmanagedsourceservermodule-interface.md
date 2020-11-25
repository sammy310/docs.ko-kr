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
ms.openlocfilehash: 5e438c75a29984e9200dc240f389f079a4eecfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733956"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="9955f-102">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9955f-102">ISymUnmanagedSourceServerModule Interface</span></span>

<span data-ttu-id="9955f-103">모듈에 대 한 소스 서버 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9955f-103">Provides source server data for a module.</span></span> <span data-ttu-id="9955f-104">`QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9955f-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9955f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9955f-105">Methods</span></span>  
  
|<span data-ttu-id="9955f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9955f-106">Method</span></span>|<span data-ttu-id="9955f-107">설명</span><span class="sxs-lookup"><span data-stu-id="9955f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9955f-108">GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="9955f-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="9955f-109">모듈에 대 한 원본 서버 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9955f-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9955f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9955f-110">Requirements</span></span>  

 <span data-ttu-id="9955f-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9955f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9955f-112">참조</span><span class="sxs-lookup"><span data-stu-id="9955f-112">See also</span></span>

- [<span data-ttu-id="9955f-113">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9955f-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

---
description: '자세히 알아보기: ISymUnmanagedSourceServerModule 인터페이스'
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
ms.openlocfilehash: c837af4cda443ec93bfbaa2d73feeb2b8f8a2803
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763126"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="dd600-103">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd600-103">ISymUnmanagedSourceServerModule Interface</span></span>

<span data-ttu-id="dd600-104">모듈에 대 한 소스 서버 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd600-104">Provides source server data for a module.</span></span> <span data-ttu-id="dd600-105">`QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd600-105">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd600-106">메서드</span><span class="sxs-lookup"><span data-stu-id="dd600-106">Methods</span></span>  
  
|<span data-ttu-id="dd600-107">메서드</span><span class="sxs-lookup"><span data-stu-id="dd600-107">Method</span></span>|<span data-ttu-id="dd600-108">설명</span><span class="sxs-lookup"><span data-stu-id="dd600-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd600-109">GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="dd600-109">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="dd600-110">모듈에 대 한 원본 서버 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd600-110">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd600-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd600-111">Requirements</span></span>  

 <span data-ttu-id="dd600-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="dd600-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd600-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd600-113">See also</span></span>

- [<span data-ttu-id="dd600-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd600-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

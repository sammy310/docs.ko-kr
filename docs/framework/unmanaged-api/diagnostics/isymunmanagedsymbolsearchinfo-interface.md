---
title: ISymUnmanagedSymbolSearchInfo 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: d7371361b074454e8aa359c49b964193c12f3034
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446154"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="ae364-102">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae364-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="ae364-103">검색 경로에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae364-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="ae364-104">[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서 `QueryInterface`를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae364-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae364-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae364-105">Methods</span></span>  
  
|<span data-ttu-id="ae364-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ae364-106">Method</span></span>|<span data-ttu-id="ae364-107">설명</span><span class="sxs-lookup"><span data-stu-id="ae364-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae364-108">GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="ae364-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="ae364-109">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae364-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="ae364-110">GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="ae364-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="ae364-111">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae364-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="ae364-112">GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="ae364-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="ae364-113">검색 경로 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae364-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae364-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae364-114">Requirements</span></span>  
 <span data-ttu-id="ae364-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ae364-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae364-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae364-116">See also</span></span>

- [<span data-ttu-id="ae364-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae364-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

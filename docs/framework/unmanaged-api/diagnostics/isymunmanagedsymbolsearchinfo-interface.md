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
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610667"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="86f92-102">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86f92-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="86f92-103">검색 경로에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86f92-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="86f92-104">`QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="86f92-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86f92-105">메서드</span><span class="sxs-lookup"><span data-stu-id="86f92-105">Methods</span></span>  
  
|<span data-ttu-id="86f92-106">메서드</span><span class="sxs-lookup"><span data-stu-id="86f92-106">Method</span></span>|<span data-ttu-id="86f92-107">설명</span><span class="sxs-lookup"><span data-stu-id="86f92-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86f92-108">GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="86f92-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="86f92-109">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="86f92-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="86f92-110">GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="86f92-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="86f92-111">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="86f92-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="86f92-112">GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="86f92-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="86f92-113">검색 경로 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="86f92-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86f92-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86f92-114">Requirements</span></span>  
 <span data-ttu-id="86f92-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="86f92-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f92-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86f92-116">See also</span></span>

- [<span data-ttu-id="86f92-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86f92-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

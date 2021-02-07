---
description: '자세히 알아보기: ISymUnmanagedSymbolSearchInfo 인터페이스'
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
ms.openlocfilehash: 2f2ab198d2c54a9fcc5fa2e24b9196a38c583f81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762983"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="2b246-103">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b246-103">ISymUnmanagedSymbolSearchInfo Interface</span></span>

<span data-ttu-id="2b246-104">검색 경로에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b246-104">Provides methods that get information about the search path.</span></span> <span data-ttu-id="2b246-105">`QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b246-105">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b246-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2b246-106">Methods</span></span>  
  
|<span data-ttu-id="2b246-107">메서드</span><span class="sxs-lookup"><span data-stu-id="2b246-107">Method</span></span>|<span data-ttu-id="2b246-108">설명</span><span class="sxs-lookup"><span data-stu-id="2b246-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b246-109">GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="2b246-109">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="2b246-110">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b246-110">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="2b246-111">GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="2b246-111">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="2b246-112">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b246-112">Gets the search path.</span></span>|  
|[<span data-ttu-id="2b246-113">GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="2b246-113">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="2b246-114">검색 경로 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b246-114">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b246-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b246-115">Requirements</span></span>  

 <span data-ttu-id="2b246-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2b246-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b246-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b246-117">See also</span></span>

- [<span data-ttu-id="2b246-118">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b246-118">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

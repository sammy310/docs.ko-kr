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
ms.openlocfilehash: 95ad3cbea4269173f22e662d15772ff97f7ee900
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705451"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="93433-102">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93433-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>

<span data-ttu-id="93433-103">검색 경로에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93433-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="93433-104">`QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93433-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93433-105">메서드</span><span class="sxs-lookup"><span data-stu-id="93433-105">Methods</span></span>  
  
|<span data-ttu-id="93433-106">메서드</span><span class="sxs-lookup"><span data-stu-id="93433-106">Method</span></span>|<span data-ttu-id="93433-107">설명</span><span class="sxs-lookup"><span data-stu-id="93433-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93433-108">GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="93433-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="93433-109">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93433-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="93433-110">GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="93433-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="93433-111">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93433-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="93433-112">GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="93433-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="93433-113">검색 경로 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93433-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93433-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93433-114">Requirements</span></span>  

 <span data-ttu-id="93433-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="93433-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93433-116">참조</span><span class="sxs-lookup"><span data-stu-id="93433-116">See also</span></span>

- [<span data-ttu-id="93433-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93433-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

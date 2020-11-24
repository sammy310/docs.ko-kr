---
title: ISymUnmanagedReaderSymbolSearchInfo 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
ms.openlocfilehash: af4124aed823a0a2475a181efe3fa68e1fae0bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678391"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="52e25-102">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52e25-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>

<span data-ttu-id="52e25-103">기호 검색 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e25-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="52e25-104">`QueryInterface` [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52e25-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52e25-105">메서드</span><span class="sxs-lookup"><span data-stu-id="52e25-105">Methods</span></span>  
  
|<span data-ttu-id="52e25-106">메서드</span><span class="sxs-lookup"><span data-stu-id="52e25-106">Method</span></span>|<span data-ttu-id="52e25-107">설명</span><span class="sxs-lookup"><span data-stu-id="52e25-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52e25-108">GetSymbolSearchInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="52e25-108">GetSymbolSearchInfo Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="52e25-109">기호 검색 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52e25-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="52e25-110">GetSymbolSearchInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="52e25-110">GetSymbolSearchInfoCount Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="52e25-111">기호 검색 정보의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52e25-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52e25-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52e25-112">Requirements</span></span>  

 <span data-ttu-id="52e25-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="52e25-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e25-114">참조</span><span class="sxs-lookup"><span data-stu-id="52e25-114">See also</span></span>

- [<span data-ttu-id="52e25-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52e25-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)

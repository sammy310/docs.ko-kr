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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a872774b1c4510c8d0325c59ae7678c867c1aff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986235"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="f37c7-102">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f37c7-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="f37c7-103">기호 검색 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f37c7-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="f37c7-104">호출 하 여이 인터페이스를 가져올 `QueryInterface` 구현 하는 개체에는 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f37c7-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f37c7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f37c7-105">Methods</span></span>  
  
|<span data-ttu-id="f37c7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f37c7-106">Method</span></span>|<span data-ttu-id="f37c7-107">설명</span><span class="sxs-lookup"><span data-stu-id="f37c7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f37c7-108">GetSymbolSearchInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="f37c7-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="f37c7-109">기호 검색 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f37c7-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="f37c7-110">GetSymbolSearchInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="f37c7-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="f37c7-111">정보를 검색 하는 기호 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f37c7-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f37c7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f37c7-112">Requirements</span></span>  
 <span data-ttu-id="f37c7-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f37c7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f37c7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="f37c7-114">See also</span></span>

- [<span data-ttu-id="f37c7-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f37c7-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

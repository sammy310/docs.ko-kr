---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 0be7297fbb71302035e71fbbf2c8b5e2a7faa2da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615295"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="7bdba-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="7bdba-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="7bdba-103">검색 경로 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bdba-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bdba-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bdba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bdba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bdba-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="7bdba-106">제한이 `ULONG32`검색 경로 길이를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdba-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bdba-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="7bdba-107">Return Value</span></span>  
 <span data-ttu-id="7bdba-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdba-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bdba-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bdba-109">Requirements</span></span>  
 <span data-ttu-id="7bdba-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="7bdba-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bdba-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bdba-111">See also</span></span>

- [<span data-ttu-id="7bdba-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bdba-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)

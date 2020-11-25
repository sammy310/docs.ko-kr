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
ms.openlocfilehash: 9803094753dee27318af9981bd2e2ad196d434e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729072"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="2f165-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="2f165-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>

<span data-ttu-id="2f165-103">검색 경로 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f165-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f165-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f165-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f165-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f165-105">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="2f165-106">제한이 `ULONG32` 검색 경로 길이를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f165-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f165-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="2f165-107">Return Value</span></span>  

 <span data-ttu-id="2f165-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2f165-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f165-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f165-109">Requirements</span></span>  

 <span data-ttu-id="2f165-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2f165-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f165-111">참조</span><span class="sxs-lookup"><span data-stu-id="2f165-111">See also</span></span>

- [<span data-ttu-id="2f165-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f165-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)

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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37e9926c8f9677e3b38202c5fb3c43f7b1159edf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170614"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="700df-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="700df-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="700df-103">검색 경로 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="700df-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="700df-104">구문</span><span class="sxs-lookup"><span data-stu-id="700df-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="700df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="700df-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="700df-106">[out] 에 대 한 포인터를 `ULONG32` 문자는 검색 경로 길이 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="700df-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="700df-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="700df-107">Return Value</span></span>  
 <span data-ttu-id="700df-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="700df-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="700df-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="700df-109">Requirements</span></span>  
 <span data-ttu-id="700df-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="700df-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700df-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="700df-111">See also</span></span>

- [<span data-ttu-id="700df-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="700df-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

---
description: '자세히 알아보기: ISymUnmanagedSymbolSearchInfo:: GetSearchPathLength 메서드'
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
ms.openlocfilehash: 3d5faf9d972881ff9c1eaf71bcaa6f68da46dae6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763022"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="bab5a-103">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="bab5a-103">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>

<span data-ttu-id="bab5a-104">검색 경로 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bab5a-104">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bab5a-105">구문</span><span class="sxs-lookup"><span data-stu-id="bab5a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bab5a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bab5a-106">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="bab5a-107">제한이 `ULONG32` 검색 경로 길이를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bab5a-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bab5a-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="bab5a-108">Return Value</span></span>  

 <span data-ttu-id="bab5a-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bab5a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bab5a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bab5a-110">Requirements</span></span>  

 <span data-ttu-id="bab5a-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="bab5a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab5a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bab5a-112">See also</span></span>

- [<span data-ttu-id="bab5a-113">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bab5a-113">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)

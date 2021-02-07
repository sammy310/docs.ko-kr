---
description: '자세히 알아보기: ISymUnmanagedSymbolSearchInfo:: GetSearchPath 메서드'
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
ms.openlocfilehash: 2ae85733ccca8ac63fbca5d2556026221e5681bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763035"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="9efe4-103">ISymUnmanagedSymbolSearchInfo::GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="9efe4-103">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>

<span data-ttu-id="9efe4-104">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9efe4-104">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efe4-105">구문</span><span class="sxs-lookup"><span data-stu-id="9efe4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9efe4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9efe4-106">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="9efe4-107">제한이 `ULONG32` 검색 경로를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 받는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9efe4-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9efe4-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="9efe4-108">Return Value</span></span>  

 <span data-ttu-id="9efe4-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9efe4-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efe4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9efe4-110">Requirements</span></span>  

 <span data-ttu-id="9efe4-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9efe4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efe4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9efe4-112">See also</span></span>

- [<span data-ttu-id="9efe4-113">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9efe4-113">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)

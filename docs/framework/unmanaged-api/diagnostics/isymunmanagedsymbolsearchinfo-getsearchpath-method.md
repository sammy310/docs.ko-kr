---
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
ms.openlocfilehash: eda8a7ff1d8b3031173bf5f73a8b8a8355e6a62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705529"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="70359-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="70359-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>

<span data-ttu-id="70359-103">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70359-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70359-104">구문</span><span class="sxs-lookup"><span data-stu-id="70359-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70359-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70359-105">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="70359-106">제한이 `ULONG32` 검색 경로를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 받는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70359-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70359-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="70359-107">Return Value</span></span>  

 <span data-ttu-id="70359-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="70359-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70359-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70359-109">Requirements</span></span>  

 <span data-ttu-id="70359-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="70359-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70359-111">참조</span><span class="sxs-lookup"><span data-stu-id="70359-111">See also</span></span>

- [<span data-ttu-id="70359-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70359-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)

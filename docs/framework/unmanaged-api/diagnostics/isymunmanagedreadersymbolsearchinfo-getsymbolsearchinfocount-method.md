---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
ms.openlocfilehash: 5883b35bb3f1fec24ec108c9839501f0e81881fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708870"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="cbfbd-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="cbfbd-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>

<span data-ttu-id="cbfbd-103">기호 검색 정보의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cbfbd-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbfbd-104">구문</span><span class="sxs-lookup"><span data-stu-id="cbfbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbfbd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cbfbd-105">Parameters</span></span>  

 `pcSearchInfo`  
 <span data-ttu-id="cbfbd-106">] out] `ULONG32` 검색 정보를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cbfbd-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbfbd-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="cbfbd-107">Return Value</span></span>  

 <span data-ttu-id="cbfbd-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cbfbd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbfbd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cbfbd-109">Requirements</span></span>  

 <span data-ttu-id="cbfbd-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="cbfbd-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfbd-111">참조</span><span class="sxs-lookup"><span data-stu-id="cbfbd-111">See also</span></span>

- [<span data-ttu-id="cbfbd-112">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbfbd-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)

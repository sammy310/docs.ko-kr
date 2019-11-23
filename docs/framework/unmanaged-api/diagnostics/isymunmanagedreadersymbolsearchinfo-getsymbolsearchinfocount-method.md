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
ms.openlocfilehash: a193c4e9e87616217efc90286032944d05d766c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446391"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="780e5-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="780e5-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="780e5-103">Gets a count of symbol search information.</span><span class="sxs-lookup"><span data-stu-id="780e5-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="780e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="780e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="780e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="780e5-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="780e5-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span><span class="sxs-lookup"><span data-stu-id="780e5-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="780e5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="780e5-107">Return Value</span></span>  
 <span data-ttu-id="780e5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="780e5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780e5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="780e5-109">Requirements</span></span>  
 <span data-ttu-id="780e5-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="780e5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780e5-111">참조</span><span class="sxs-lookup"><span data-stu-id="780e5-111">See also</span></span>

- [<span data-ttu-id="780e5-112">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="780e5-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)

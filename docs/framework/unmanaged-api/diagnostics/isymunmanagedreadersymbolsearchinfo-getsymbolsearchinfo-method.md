---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 519fa1b2c2866a6906d833251e18d86b7b43d525
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153727"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="ad47d-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="ad47d-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="ad47d-103">기호 검색 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad47d-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad47d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad47d-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad47d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad47d-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="ad47d-106">[in] A `ULONG32` 의 크기를 나타내는 `rgpSearchInfo`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad47d-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="ad47d-107">[out] 에 대 한 포인터를 `ULONG32` 검색 정보를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad47d-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="ad47d-108">[out] 설정 된 포인터를 반환 [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad47d-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad47d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ad47d-109">Return Value</span></span>  
 <span data-ttu-id="ad47d-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ad47d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad47d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad47d-111">Requirements</span></span>  
 <span data-ttu-id="ad47d-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ad47d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad47d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad47d-113">See also</span></span>

- [<span data-ttu-id="ad47d-114">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad47d-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)

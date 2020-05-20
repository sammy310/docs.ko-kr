---
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: 9dcd8282adf200932e86c950bee0b073780ce02d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615308"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="897ce-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="897ce-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="897ce-103">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="897ce-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="897ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="897ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="897ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="897ce-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="897ce-106">제한이 HRESULT에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="897ce-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="897ce-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="897ce-107">Return Value</span></span>  
 <span data-ttu-id="897ce-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="897ce-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="897ce-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="897ce-109">Requirements</span></span>  
 <span data-ttu-id="897ce-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="897ce-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="897ce-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="897ce-111">See also</span></span>

- [<span data-ttu-id="897ce-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="897ce-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)

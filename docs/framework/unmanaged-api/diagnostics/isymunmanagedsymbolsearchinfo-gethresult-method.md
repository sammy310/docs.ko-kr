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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b32865e0ac9d8a4a049db5d7ed6179879342c10a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778112"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="7b641-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="7b641-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="7b641-103">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b641-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b641-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b641-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b641-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b641-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="7b641-106">[out] HRESULT에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b641-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b641-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7b641-107">Return Value</span></span>  
 <span data-ttu-id="7b641-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7b641-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b641-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b641-109">Requirements</span></span>  
 <span data-ttu-id="7b641-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b641-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b641-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b641-111">See also</span></span>

- [<span data-ttu-id="7b641-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b641-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

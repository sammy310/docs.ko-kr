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
ms.openlocfilehash: 21f6cf18ee7d883e1792b597e08724946f53eda9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446190"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="d04ce-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="d04ce-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="d04ce-103">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d04ce-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d04ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="d04ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d04ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d04ce-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="d04ce-106">제한이 HRESULT에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d04ce-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d04ce-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d04ce-107">Return Value</span></span>  
 <span data-ttu-id="d04ce-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d04ce-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d04ce-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d04ce-109">Requirements</span></span>  
 <span data-ttu-id="d04ce-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d04ce-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d04ce-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d04ce-111">See also</span></span>

- [<span data-ttu-id="d04ce-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d04ce-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

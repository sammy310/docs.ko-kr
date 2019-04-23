---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 442584cffe4b4ae44702892587e261d41abf4e8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150425"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="72000-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="72000-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="72000-103">최소 가져옵니다 특정 문서에서 줄 및 메서드에 대 한 가장 큰 끝 줄을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="72000-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72000-104">구문</span><span class="sxs-lookup"><span data-stu-id="72000-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72000-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72000-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="72000-106">[in] 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="72000-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="72000-107">[out] 에 대 한 포인터를 `ULONG32` 시작 줄을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="72000-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="72000-108">[out] 에 대 한 포인터를 `ULONG32` 줄 끝을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="72000-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72000-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="72000-109">Return Value</span></span>  
 <span data-ttu-id="72000-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="72000-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72000-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72000-111">Requirements</span></span>  
 <span data-ttu-id="72000-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72000-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72000-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="72000-113">See also</span></span>

- [<span data-ttu-id="72000-114">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72000-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

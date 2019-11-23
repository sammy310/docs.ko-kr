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
ms.openlocfilehash: b8e72745eff09c6707afe5a5f20a1ddf38b239ae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448623"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="227b1-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="227b1-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="227b1-103">Gets the smallest start line and largest end line for the method in a specific document.</span><span class="sxs-lookup"><span data-stu-id="227b1-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="227b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="227b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="227b1-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="227b1-106">[in] A pointer to the document.</span><span class="sxs-lookup"><span data-stu-id="227b1-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="227b1-107">[out] A pointer to a `ULONG32` that receives the start line.</span><span class="sxs-lookup"><span data-stu-id="227b1-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="227b1-108">[out] A pointer to a `ULONG32` that receives the end line.</span><span class="sxs-lookup"><span data-stu-id="227b1-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="227b1-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="227b1-109">Return Value</span></span>  
 <span data-ttu-id="227b1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="227b1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="227b1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="227b1-111">Requirements</span></span>  
 <span data-ttu-id="227b1-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="227b1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227b1-113">참조</span><span class="sxs-lookup"><span data-stu-id="227b1-113">See also</span></span>

- [<span data-ttu-id="227b1-114">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="227b1-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

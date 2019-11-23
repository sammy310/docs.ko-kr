---
title: ISymUnmanagedConstant::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 00be35e9a15349b8bca5f76b948b8477dd240888
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449246"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="57142-102">ISymUnmanagedConstant::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="57142-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="57142-103">Gets the value of the constant.</span><span class="sxs-lookup"><span data-stu-id="57142-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57142-104">구문</span><span class="sxs-lookup"><span data-stu-id="57142-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57142-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57142-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="57142-106">[out] A pointer to a variable that receives the value.</span><span class="sxs-lookup"><span data-stu-id="57142-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57142-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="57142-107">Return Value</span></span>  
 <span data-ttu-id="57142-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="57142-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57142-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57142-109">Requirements</span></span>  
 <span data-ttu-id="57142-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="57142-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57142-111">참조</span><span class="sxs-lookup"><span data-stu-id="57142-111">See also</span></span>

- [<span data-ttu-id="57142-112">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57142-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="57142-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="57142-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="57142-114">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="57142-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)

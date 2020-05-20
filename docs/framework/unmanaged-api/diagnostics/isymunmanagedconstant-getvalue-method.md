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
ms.openlocfilehash: 8e20d2e0f3d5cb6dc7444c8e78665b6c8b82d2de
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441476"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="369f0-102">ISymUnmanagedConstant::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="369f0-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="369f0-103"> 상수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="369f0-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="369f0-104">구문</span><span class="sxs-lookup"><span data-stu-id="369f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="369f0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="369f0-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="369f0-106">제한이 값을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="369f0-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="369f0-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="369f0-107">Return Value</span></span>  
 <span data-ttu-id="369f0-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="369f0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="369f0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="369f0-109">Requirements</span></span>  
 <span data-ttu-id="369f0-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="369f0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369f0-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="369f0-111">See also</span></span>

- [<span data-ttu-id="369f0-112">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="369f0-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="369f0-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="369f0-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="369f0-114">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="369f0-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)

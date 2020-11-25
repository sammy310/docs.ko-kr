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
ms.openlocfilehash: 7a1c795f4a162699078e91bcaa274253169234e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732842"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="427c5-102">ISymUnmanagedConstant::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="427c5-102">ISymUnmanagedConstant::GetValue Method</span></span>

<span data-ttu-id="427c5-103"> 상수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="427c5-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="427c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="427c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="427c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="427c5-105">Parameters</span></span>  

 `pValue`  
 <span data-ttu-id="427c5-106">제한이 값을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="427c5-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="427c5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="427c5-107">Return Value</span></span>  

 <span data-ttu-id="427c5-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="427c5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="427c5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="427c5-109">Requirements</span></span>  

 <span data-ttu-id="427c5-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="427c5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427c5-111">참조</span><span class="sxs-lookup"><span data-stu-id="427c5-111">See also</span></span>

- [<span data-ttu-id="427c5-112">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="427c5-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="427c5-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="427c5-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="427c5-114">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="427c5-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
